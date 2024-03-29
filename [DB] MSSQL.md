## WITH (NOLOCK)
```
    SELECT * FROM table_01 WITH (NOLOCK)
```
- With (Nolock)을 사용하는 이유: 테이블의 데이터를 업데이트할 경우, 기본적으로 해당 테이블은 잠겨있고 이를 Lock 상태라 함
- Lock이 걸리는 이유: MSSQL의 기본 격리수준이 Read Committed 이기 때문 즉, 완전히 commit이 된 데이터만 읽으라는 뜻
- lock이 걸려있는 동안 테이블 조회(select)를 진행하게 되면, select 작업이 후순위로 밀리고 DB성능이 떨어질 수 있음
- 장점: 데드락* 현상을 방지하기 위해 사용하는 것이 WITH (NOLOCK) 으로 사용자 입장에서 SELECT 작업이 후순위로 밀리는 것을 방지하는 것이 목적
- 단점: 테이블에 업데이트 한 데이터가 롤백(rollback)될 경우, 조회한 데이터의 정합성 문제가 야기될 수 있음
*락이 풀리는 것이 아니라 교착상태로 서로의 락이 풀리길 무한정 기다면서, 오히려 락이 계속 풀리지 못하는 상태


## ON DUPLICATE KEY UP
https://bamdule.tistory.com/112
