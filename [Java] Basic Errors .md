# Java

## [Error] 객체 import 에러
- IntelliJ IDE에서 import가 안 될 경우 캐시삭제
- 해결방안: File > Invalidate Cashes Restart > Invalidate and Restart

## [Error] apr100Store has private access
Java: apr100Store has private access in com.posco.pes.s65e04.domain.logic.flow.S65e040111Logic
- 해결방안: apr100Store 를 SpringLogic 클래스의 생성자로 선언하여 DI 주입

## [Error] No identifier specified for entity
- 해결방안: DB 에서 PK 2개 항목 추가 후 JPA 기본 키 매핑과 JpoId 클래스 선언

## [Error] Could not read JOSN: java.lang.NumberFormatException;
- 원인: json 요청을 보내고 @RequestBody에 매핑할 경우 해당 에러가 발생
- 해결방안: front 에서 보내는 parameter 문제로 서버의 자료형과 프론트 자료형이 불일치
- 상세: react(front)에서 보내는 _registParams = { seq: "", … } 해당 컬럼은 BigDecimal, 프론트에서는 전송하는 ""는 서버에서 String형으로 인식

## [Tips] 조회 구문에서 호출할 때, 값들이 유실될 경우
- VO 에 컬럼 매핑확인

## [Error] class 패키지명 declares multiple JSON fields named 변수명
- class com.posco.pes.s65rq1.domain.S65e040111VO declares multiple JSON fields named createdObjectId
- VO에 중복된 멤버필드가 존재
- 또는 상속(extends)받은 VO나 entity 객체에 동일한 멤버필드가 존재