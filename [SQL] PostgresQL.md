# SQL

## MyBatisSystemException
- [ERROR] org.mybatis.spring.MyBatisSystemException: nested exception is org.apache.ibatis.type.TypeException: Could not
  set parameters for mappint: ParameterMapping{property='vendorName', mode = IN, javaType = class Java.lang.Object, jdbc
  Type=null, numericScale=null, resultMapId='null', jdbcTypeName='null', expression='null'}. Cause: org.apache.ibatis.ty
  pe.TypeException: Error setting null for parameter # with jdbcType OTHER. Try setting a different JdbcType for this pa
  rameter or a different jdbcTypeForNull configuration property. Cause: org.postgresql.util.PSQLException: The column in
  dex is out of range: 3, number of columns: 2.
- 해결방법: SQL 문법 에러, MyBatis 메서드 파라미터가 2개로 설정되어 있지만, 실제로 실행되는 구문은 3개 설정되어 있는 구문을 실행시킴
```yml
  …생략
  AND car123.pass_cars_index = {passCarsIndex}
  AND men456.pass_user_index = {passUserIndex}
  --AND cmp123.company_name = {companyName}
```
- 주석처리 했다고 생각한 내용이 그대로 SQL문에 반영하여 3개가 설정되어 있는 실정이었음