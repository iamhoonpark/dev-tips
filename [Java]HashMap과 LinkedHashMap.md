수정하기
- 같은 item이라고 판단할 경우 고유의 key를 만들어서 재그룹화 후에 client에 전송
- HashMap으로 그룹화를 진행했을 경우 문제점 DB에서 order by 후 데이터를 집합하는 과정에서 데이터가 섞여서 order by가 무시됨
- LinkedHashMap으로 진행할 경우 객체에 특성에 따라 정렬이 가능

- 차이점
