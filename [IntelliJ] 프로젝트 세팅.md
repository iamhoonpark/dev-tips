## 작업세팅
- Windows 에서는 대소문자를 구분 안 하지만, 인텔리제이에서는 영문 소문자로 인식함
- 따라서 프로젝트 상위 폴더는 전부 소문자
- ex) workplace/sample, workplaceexample

## IntelliJ Setting
- 모든 알람은 우측 메뉴탭의 Notification 에서 확인
- 최초 설치 후 Node.js, (plugins) less, styless, ignore, lombok 필수 설치
- 인텔리제이에서는 프로젝트 별 폴더를 Open
- 상위폴더(ex: workplace)를 Open 할 경우 단을 프로젝트로 인식(.idea 폴더 생성)

## Maven Setting
- Settings(Ctrl + Alt + S) → Build, Execution, Deployment → Build Tools → Maven
- Maven home path 를 bundled 된 메이븐이 아닌 apach-maven 으로 설정
- 우측 Maven 탭에서 LifeCycle → clean → install
- error) parent.relativePath : pom.xml <parent> root element 내부에 <relativePath/>

## Run Server
- Run Server 후 주소가 localhost:8080 이 아닌 s65-z01-config:8080 으로 서버가 생성되면
- application-local.yml 파일의 uri 를 localhost 로 수정

## IntelliJ List of Controllers
- 프로젝트 클릭 후 하단 Spring Tab → MVC Tap → s65eq1-boot → 컨트롤러 목록 확인 가능

## Connect DB
1) (DBeaver)DB Connection settings 참조하여 2) 번과 연결
2) (IntelliJ) Data Sources and Drivers
- 우측 Tab → + → Data Source → PostreSQL
- name : 
- database : 
- username/password : 
- 만약 download DBfile 이라고 될 경우 설치 진행
- Test Connection