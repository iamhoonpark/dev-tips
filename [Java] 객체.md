# 객체를 복사하는 자료형

## ModelMapper, BeansUtils
- 기능 : 객체 A를 B로 복사한다.
- ModelMapper 자료형은 List, Set, Map 등 JaVA에서 정의해 놓은 구조체를 지원해준다.
- BeanUtils는 Bean 규격이 완전한 객체만 기능을 제공한다. (즉, HashMap을 컨버팅하지 못함)

## Bean 규격이란
- VO를 뜻한다.
- Bean 규격 : Getter와 Setter를 선언하면 Bean이 된다.
- BeanUtils는 Getter와 Setter가 정의되어 있어야 사용이 가능하다.
- BeanUtils를 쓰려면 Setter가 반드시 있어야 하는데, HashMap은 Setter가 없고 push를 사용하기 때문에 매핑을 못 시킨다.
- ModelMapper는 List, Set, Map 등 Java에서 정의해 놓은 구조체를 지원해준다.

```yml
public HelloJava toDomain() {
    HelloJava retVal = new HelloJava();
    BeanUtils.copyProperties(this, retVal);
    return retVal;
}
```

# HttpServletReqeust
- 기능 : 넘어오는 객체를 확인하고 싶을 때 사용
```yml
@PostMapping(path = "/register")
public HelloJava register(HttpServletRequest request,
                          @RequestBody CarDTO carDTO) {
  // 넘어오는 객체를 확인하고 싶다면 해당 객체를 인자로 선언
  // log 기록 확인
  System.out.println(request.getParameterMap());
  return this.service.register(carDTO);
}
```
- 실행결과 : org.apache.catalina.util.ParameterMap@3651c9de
- HashMap으로 형태 확인 가능