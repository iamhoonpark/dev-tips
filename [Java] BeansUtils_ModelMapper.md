# ModelMapper
- 객체 A를 B로 복사
- BeanUtils 와 차이점 HashMap을 컨버팅하지 못 한다.

# VO
- Bean 규격 : Getter와 Setter를 선언하면 Bean이 된다.
- BeanUtils는 Getter와 Setter가 정의되어 있어야 사용이 가능하다.
- BeanUtils를 쓰려면 Setter가 반드시 있어야 하는데, HashMap은 Setter가 없고 push를 사용하기 때문에 매핑을 못시킨다.
- ModelMapper는 List, Set, Map 등 Java에서 정의해 놓은 구조체를 지원해준다.

```yml
public HelloJava toDomain() {
    HelloJava retVal = new HelloJava();
    BeanUtils.copyProperties(this, retVal);
    return retVal;
}
```