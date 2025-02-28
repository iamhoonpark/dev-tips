1. 테이블 복제 방법
CREATE TABLE <계정명>.<새 테이블명> AS SELECT * FROM <계정명>.<원본 테이블명> WHERE 1 = 1; // 데이터까지 복제 WHERE 1 = 0; 스키마만 복제

ex.
```
CREATE TABLE TOBEADM.USER_INFO AS SELECT * FROM ASISADM.USER_INFO WHERE 1 = 1;
```
