# JPA

### BeanCreationException

DB 테이블 tb_men110 을 객체와 Jpa 1:1로 매핑 후 실행했으나, 아래와 같은 에러가 발생
```yml
org.spring.framework.beans.factory.BeanCreationException: Error creating bean with name 'entityManagerFacotry' defined in class path resource
[org/springframework/boot/autoconfigure/orm/jpa/HibernateJpa/Configuration.class]: Invocation of init method failed; nested exception is
javax.persistence.PersistenceException: [PersistenceUnit: default] Unable to build Hibernate SessionFactory; nested exception is org.hibernate.MappintException: Could not instantiate id generator [entity-name=com.posco.pes.s65e04.store.jpa.Men110jpo]
```
해당 DB 컬럼을 확인 해보니, 해당 테이블 PK에 대한 시퀀스의 값이 아래와 같이 설정되어 있어서 다른 테이블의 시퀀스값과 비교 후 DB increment와 Jpo의 allogation 사이즈를 1으로 수정 후 매핑
```yml
tb_s65e04_men110_seq_seq : Properties Increment By : -76
```
