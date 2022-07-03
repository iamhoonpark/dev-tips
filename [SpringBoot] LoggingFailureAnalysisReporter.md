# SpringBoot
## 에러 제목 : LoggingFailureAnalysisReporter
Resource 부터 MyBatisStor 를 매핑할 때, 발생하는 문제
```yml
[ERROR] [1] 2022-06-03 14:16:20.212 |||| LoggingFailureAnalysisReporter - 
Parameter 0 of constructor in com.package.package.service.logic.s65e040110SpringLogic required a single bean, but 2 were foudn:
```
- SpringLogic 부터 쫓아서 내려가다보면 implements 즉 MybatisStore 쪽에서 다른 객체를 implements로 구현하고 있어서 발생한 문제
