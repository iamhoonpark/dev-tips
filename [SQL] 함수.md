## trim

### 속성
- prfix : 해당 키워드를 실행될 쿼리의 <trim> 문 안에 가장 앞에 붙임
- prefixOverrides : 해당 키워드를 쿼리문 앞에 해당하는 값들이 존재할 경우 제거
- suffix : 해당 키워드를 실행될 쿼리 가장 뒤에 붙임

```yml

<trim prefix="AND (" prefixOverrides="OR" suffix=")">
    <if test="checkFirst.equals('true')>
      OR user100.user_level = 'A'
    <if/>
    <if test="checkSecond.equals('true')>
      OR user100.user_level = 'B'
    <if/>
    <if test="checkThird.equals('true')>
      OR user100.user_level = 'C'
    <if/>
    <if test="checkFourth.equals('true')>
      OR user100.user_level = 'D'
    <if/>
</trim>

```
### 실행결과
```yml
AND (
  OR user100.user_level = 'A'
  OR user100.user_level = 'B'
)
```