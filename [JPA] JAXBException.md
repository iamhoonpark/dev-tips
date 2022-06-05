# JPA 
## 에러 제목 : java.lang.NoClassDefFoundError: javax/xml/bind/JAXBException
2022-06-05
- 프로젝트 환경 : Java11, hibernate
- JPA 프로젝트 생성 후 간단한 로직 선언 후에 실행 시 발생한 에러
```yml
6월 05, 2022 4:31:50 오후 org.hibernate.cfg.Environment <clinit>
INFO: HHH000206: hibernate.properties not found
Exception in thread "main" java.lang.NoClassDefFoundError: javax/xml/bind/JAXBException
	at org.hibernate.boot.spi.XmlMappingBinderAccess.<init>(XmlMappingBinderAccess.java:43)
	at org.hibernate.boot.MetadataSources.<init>(MetadataSources.java:86)
	at org.hibernate.jpa.boot.internal.EntityManagerFactoryBuilderImpl.<init>(EntityManagerFactoryBuilderImpl.java:212)
	at org.hibernate.jpa.boot.internal.EntityManagerFactoryBuilderImpl.<init>(EntityManagerFactoryBuilderImpl.java:174)
	at org.hibernate.jpa.boot.spi.Bootstrap.getEntityManagerFactoryBuilder(Bootstrap.java:76)
	at org.hibernate.jpa.HibernatePersistenceProvider.getEntityManagerFactoryBuilder(HibernatePersistenceProvider.java:171)
	at org.hibernate.jpa.HibernatePersistenceProvider.getEntityManagerFactoryBuilderOrNull(HibernatePersistenceProvider.java:119)
	at org.hibernate.jpa.HibernatePersistenceProvider.getEntityManagerFactoryBuilderOrNull(HibernatePersistenceProvider.java:61)
	at org.hibernate.jpa.HibernatePersistenceProvider.createEntityManagerFactory(HibernatePersistenceProvider.java:50)
	at javax.persistence.Persistence.createEntityManagerFactory(Persistence.java:79)
	at javax.persistence.Persistence.createEntityManagerFactory(Persistence.java:54)
	at entitymapping.JpaMain.main(JpaMain.java:13)
Caused by: java.lang.ClassNotFoundException: javax.xml.bind.JAXBException
	at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:581)
	at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:178)
	at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:521)
	... 12 more

Process finished with exit code 1
```
JAXB는 Java6 에서 2.0으로 내장되어 있었고 Java9 에서 모듈화 방식을 사용하면서 vm 옵션을 통해 추가해서 사용할 수 있었으나
Java 11 버전부턴 삭제가 됨에 따라 아래의 코드를 Maven dependencies root element에 추가하여 해결
```yml
<dependency>
            <groupId>javax.xml.bind</groupId>
            <artifactId>jaxb-api</artifactId>
            <version>2.3.0</version>
        </dependency>
```
`maven update`, `maven clean`

---
