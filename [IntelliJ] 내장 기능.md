- 인텔리제이를 쓰는 이유 : 인텔리제이가 메모리 관리를 잘 해서 이클립스 등 다른 IDE 보다 성능이 보다 최적화
- import가 안 될 경우 캐시삭제 : File > Invalidate Cashes Restart > Invalidate and Restart

# .http 사용법

## POST 방식
```yml
POST http://localhost:8080/service-readonly/s56e030210/findList
Content-type: application/json

  {"companyName": "", "fullName": "", "dateOfBirth":""}

```