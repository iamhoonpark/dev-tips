# Java 예외처리(Exception 처리)

- java 개발을 처음 시작할 때는 크게 신경 쓰지 않고 넘어갔지만, 점점 고민이 많아지는 부분이 예외처리와 트랜잭션 처리에 대한 부분이다.
- 특히, 트랜잭션은 잘못 처리할 경우 데이터가 꼬여 치명적인 결함을 발생시킬 수 있기 때문에 신경써야 하는 작업이다.

#### 오늘 개발하면서 처음 작업해본 트랜잭션과 예외처리에 대한 방황과 기록
```yml

    @Override
    @Transactional
    public Object registerUser(List<Usr100> entities) {
      
      try {
        for (Usr100 entity : entities) {
          Usr100 usr100 = modelMapper.map(entity, Usr100.class);
          Usr100 resultInsert100 = this.usr100Store.create(usr100);
          this.userStore.InsertToUsNativeQuery(resultInsert100.getSeq());
        }
      } catch(Exception e) {
        log.info("[registerUser] occur error : {}", e);
        throw new Exception("유저를 등록할 수 없습니다.");
      }
        
      return SUCCESS;
        
    }

```
1) 처음엔 for문 안에 return SUCCESS; 를 두어서, entities 가 몇개의 객체를 배열로 가지고 있던, 딱 한 개의 entity 에 대해서만 Insert 되어 당황했다. return 을 for 문에서 꺼내어 메서드 최하단에 선언하니 2개 이상에 대한 객체도 전부 INSERT 가 실행되었다.
2) 중간에 값이 잘못 세팅되어 실행 될 경우 에러가 발생하지만, 에러가 발생하는 지점 전까지는 INSERT 가 실행되는 점 때문에 데이터가 꼬이는 문제가 발생하여 트랜잭션 어노테이션을 선언
3) 그러나, 롤백은 되지만, return SUCCESS 가 그대로 실행되어 클라이언트에서는 성공으로 인식해서 alert("완료되었습니다."); 가 실행되는 문제가 발생
4) 예외 처리를 사용하여, 롤백과 클라이언트에 해당 Exception 메세지를 그대로 전송할 수 있게 되었다.