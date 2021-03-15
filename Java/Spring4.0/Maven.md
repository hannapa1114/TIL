### Maven이란

- 자바를 이용해서 어플리케이션을 개발할 때 Maven 혹은 Gradle이라는 빌드 도구를 사용한다.
- 주요 특징 중 하나는 의존 모듈(jar 파일) 관리에 있다.
- 중앙 Repository라고 불리는 서버로부터 필요한 jar파일을 다운로드 받아 의존묘듈을 관리한다.

#### 기본 설정
1. (메이븐 다운로드)[https://maven.apache.org/download.cgi]
2. zip 파일을 적당한 경로에 압축해제 한다.
3. 환경변수 설정
   - 시스템 환경 변수에 maven path를 만든다 
   - 이름과 경로를 설정'C:\apache-maven-3.6.3\bin'
4. cmd에 mvn -version으로 환경 변수 설정이 정상적으로 됐는지 확인한다.

#### 의존성 주입
```
<dependencies>
  <dependency>
    <groupId>org.springframework</springId>
    <artifactId>spring-context</artifactId>
    <version>4.0.4.RELEASE</version>
  </dependency>
</dependencies>
```
스프링 컨텍스트 모듈의 4.0.4.RELEASE를 사용하겠다는 뜻, 스프링 컨텍스트 모듈이 **의존하고 있는 모듈들을 같이 다운로드** 해준다!

출처
1) 최범균, 웹 개발자를 위한 Spring 4.0 프로그래밍