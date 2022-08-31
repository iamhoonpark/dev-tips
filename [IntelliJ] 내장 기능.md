- 인텔리제이를 쓰는 이유 : 인텔리제이가 메모리 관리를 잘 해서 이클립스 등 다른 IDE 보다 성능이 보다 최적화
- import가 안 될 경우 캐시삭제 : File > Invalidate Cashes Restart > Invalidate and Restart



# 1. SQL Dialects 설정
- Settings > Languages & Frameworks > SQL Dialects
- Project SQL Dialect > PostgreSQL
- xml DB 매핑이 틀렸을 경우, 빨간색 글씨로 에러 확인 가능

# 2. Http Client

### 1) POST 방식
```yml
POST http://localhost:8080/service-readonly/s56e030210/findList
Content-type: application/json

  {"companyName": "", "fullName": "", "dateOfBirth":""}

```

# 3. 작업창 설정
- 작업창에서 오픈된 파일이 많을 때, 파일 보기 창을 한 줄로 보여줄 것인지 또는 많다면 여러줄로 나누어 보여줄 것인지 설정
- Settings → Editor → General → Editor Tabs → Appearance → Show tabs in one row