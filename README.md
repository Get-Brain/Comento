# 윈도우 환경에서 스프링 개발환경 셋팅

1. JDK 설치
  - 1.8u_221 버전
    http://www.oracle.com/technetwork/java/javase/downloads/index.html 접속 후 위 버전 설치
    ![1](https://user-images.githubusercontent.com/79196972/109784861-d9e6b180-7c4e-11eb-96f7-bd8f97ef3b60.PNG)
    
    
  - 환경변수 셋팅
    - 제어판 -> 시스템 -> 고급 시스템 설정 -> 고급 탭 -> 환경 변수

    환경변수
    새로만들기 클릭 후 변수 이름을 JAVA_HOME, 변수 값에 JDK 위치 디렉터리로 설정
    ![2](https://user-images.githubusercontent.com/79196972/109786262-54fc9780-7c50-11eb-9f83-5ddda64bb9e3.PNG)
    
    Path 변수를 편집
    %JAVA_HOME%\bin 으로 경로를 추가(path에 바로 경로\bin을 추가해도 됨)
    ![3](https://user-images.githubusercontent.com/79196972/109786816-e9ff9080-7c50-11eb-9819-27ceff37f3f2.PNG)
    
    
    잘 동작하는 지 테스트 : cmd에서 javac 명령어 입력
    ![4](https://user-images.githubusercontent.com/79196972/109787343-79a53f00-7c51-11eb-89a4-e771ced85a5c.PNG)

   
2. Eclipse 설치
  -  https://www.eclipse.org/downloads 에서 다운로드
  -  Eclipse IDE for Java EE developers로 설치해야 함
  ![5](https://user-images.githubusercontent.com/79196972/109787897-0ea83800-7c52-11eb-8765-e373ca975162.PNG)
  
  - 설치 후 기본 셋팅
    설치 완료 후 Eclipse.ini(이클립스 설치 경로에 존재) -> -vm C:\Program Files\Java\jdk1.8.0_221\bin\javaw.exe 추가
    
    Windows -> Preferences -> workspace, Windows -> Web -> jsp, html, css 로 이동
    ![6](https://user-images.githubusercontent.com/79196972/109790779-17e6d400-7c55-11eb-9d5b-5ab933456926.PNG)
    ![7](https://user-images.githubusercontent.com/79196972/109790786-19b09780-7c55-11eb-9052-82b1f03cb5f3.PNG)
    

3. Spring 설치
  - 1번째 방법 : 이클립스 안에서 STS플러그인을 설치하는 방법
  - 2번째 방법 : 이클립스 기반으로 된 STS를 Spring 프레임워크 사이트에서 설치(저는 이 방법으로 할 예정)
  
    이클립스에서 Help -> Eclipse MarketPlace에 STS를 검색하여 설치
    ![8](https://user-images.githubusercontent.com/79196972/109791216-87f55a00-7c55-11eb-8b9f-38e169be93c5.PNG)
    
    정상 설치 되었다면 우측 상단의 상자를 클릭하여 Spring이 추가 된 것을 확인!
    
    ![9](https://user-images.githubusercontent.com/79196972/109791927-529d3c00-7c56-11eb-8792-a3cf24be5dab.PNG)


4. 톰캣 다운로드
  - https://tomcat.apache.org 로 접속해 톰캣 설치
  - 버전은 9 버전 사용
  - 이번 세팅에서는 톰캣 경로를 이클립스와 동일하게 설정

  Eclipse, Tomcat 설정
  - Windows -> Preferences -> Server 에서 해당 톰캣을 Add
  
  ![10](https://user-images.githubusercontent.com/79196972/109793782-706ba080-7c58-11eb-9f78-c27d63837616.PNG)
  
  Eclipse 창에 Server 표시하기
  - Windows -> Show View -> Servers 클릭
  - 그러면 하단에 Server 탭이 생성된 것을 확인 할 수 있다.
  
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  
1. 스프링 프로젝트 생성
  - File -> New -> Other
  - Spring -> Spring Legacy Project 선택
  - 프로젝트 이름 작성 및 Spring MVC Project를 설정 후 Next 버튼 클릭
  - 패키지명을 설정 후 Finish를 클릭하면 Progress 탭에서 스프링 프로젝트 개발에 필요한 라이브러리를 Maven을 이용해 다운로드하는 것을 확인 할 수 있음.
  - 다운로드 받은 라이브러리는 사용자 폴더 내 .m2 안의 repository 폴더 안에 생성됩니다.
    
2. 스프링 버전 변경
  - mvnrepository.com에서 Spring을 검색하여 현재 버전을 검색합니다.
  ![12](https://user-images.githubusercontent.com/79196972/109796013-00124e80-7c5b-11eb-8e99-3003f1ee43cd.PNG)
  
  5.3.4가 최신 버전임을 확인 할 수 있음.
  
  Eclipse 프로젝트에서 최하단의 pom.xml에서 스프링 버전/JDk 버전을 수정
  ![13](https://user-images.githubusercontent.com/79196972/109796423-7ca52d00-7c5b-11eb-9847-edc9150a71d8.PNG)
  ![14](https://user-images.githubusercontent.com/79196972/109796565-a9594480-7c5b-11eb-9cd7-99b321ad3112.PNG)
  
  maven-compiler 수정
  mavenrepository.com에서 버전을 확인 후 수정
  여기에서는 스프링은 5.1.8, maven-compiler는 3.7.0으로 수정
  maven-compiler 기준도 source, target 을 1.8로 수정
  위와 같이 한 후에는 pom.xml을 저장하면 자동으로 해당 버전의 라이브러리가 다운됨.
  
3. 서버 셋팅
  - 기존에 셋팅한 좌측 하단의 Servers에서 마우스 우클릭 -> New -> Server를 클릭
  ![15](https://user-images.githubusercontent.com/79196972/109797152-69df2800-7c5c-11eb-86e1-46d7d8cccb89.PNG)
  
  tomcat 9.0 버전 선택 후 Server name을 본인 임의대로 수정 한 후 Next 클릭
  
  ![16](https://user-images.githubusercontent.com/79196972/109797155-6b105500-7c5c-11eb-8d44-59d4ce740828.PNG)
  
  해당 서버로 구동할 프로젝트를 우측 configured로 추가한 후 Finish를 클릭해 설정
  
  ![17](https://user-images.githubusercontent.com/79196972/109798832-9300b800-7c5e-11eb-83e7-e1b0b5657d31.PNG)
  
  Server 영역 우측의 실행버튼 클릭 -> localhost:8080/프로젝트명/으로 접속하면 위와 같은 화면을 확인할 수 있음.
  
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. mariaDB, sql_developer 다운로드
  - https://downloads.mariadb.org/mariadb/ 로 접속 후 mariaDB 다운로드
  ![18](https://user-images.githubusercontent.com/79196972/109799272-2e922880-7c5f-11eb-9ac8-9a9594b2c33a.PNG)
  
  ![19](https://user-images.githubusercontent.com/79196972/109799555-8335a380-7c5f-11eb-851b-f1305bf9ca93.PNG)
  ![20](https://user-images.githubusercontent.com/79196972/109799560-8466d080-7c5f-11eb-88f7-5a94e3908a97.PNG)
  
  위 두 화면의 설정이 제일 중요하다!!
  Modify password for database user 'root'
  root 계정에 대한 패스워드를 설정
  자신이 실제 사용할 패스워드이기 때문에 잊어버리면 안된다.
  
  Enable access from remote machines for 'root' user
  외부에서 root계정에 대한 원격접속을 허용
  로컬이 아닌 원격지(다른 컴퓨터)에서 DB접속이 필요한 경우 체크
  
  Use UTF8 as default server's character set
  UTF8를 기본 캐릭터셋으로 지정
  한국어를 포함한 다국어 표현을 위해서 UTF8사용을 선택하는게 좋다.
  
  Install as service, Service Name
  윈도우 서비스로 등록하여 부팅시 자동으로 마리아DB가 시작
  윈도우에 등록할 서비스명 입력
  
  Enable networking, TCP port
  TCP 리스너 활성화 여부
  TCP 접속에 사용될 포트지정
  
  mariaDB 접속확인
  시작 -> 프로그램 -> MariaDB 10.2(x64) -> MySQL Client를 실행
  ![21](https://user-images.githubusercontent.com/79196972/109799888-e58ea400-7c5f-11eb-8efb-07c8fc8104b3.PNG)
  
  본인이 설정한 root 비밀번호를 입력한 후 엔터를 입력했을 때 위 화면이 뜨면 성공!
  
2. MySQL workbench 설치
  - 구글에 검색해 다운로드
  
  workbench를 실행하면 local instance가 자동으로 잡힘을 확인 할 수 있음 -> 해당 Connections를 클릭하고 설정한 패스워드 입력한 후 OK 클릭
  ![22](https://user-images.githubusercontent.com/79196972/109800654-cfcdae80-7c60-11eb-885b-ea48140b9328.PNG)
  
  
3. 스키마 생성
  - 좌측 Navigator의 하단에 Schemas 선택 후 현재 상태를 보면 test만 존재하는 것을 확인 할 수 있음.
  - 이번에는 Theater라는 스키마를 생성
  - 상단에 Create Schema 아이콘 클릭 후 나온 Schema 내용을 설정
    Name : Theater
    charset/Collation : utf8, utf8_bin으로 설정 후 apply를 클릭하여 Schema 생성
    ![23](https://user-images.githubusercontent.com/79196972/109801072-54203180-7c61-11eb-90a5-f0f747812241.PNG)

4. 테이블 생성
  theater 스키마 밑의 Tables 우측을 클릭하여 Create Table을 클릭 -> Movie라는 테이블을 만듬
  ![24](https://user-images.githubusercontent.com/79196972/109801384-bb3de600-7c61-11eb-92d5-54f1e977fecf.PNG)
  
  위와 같이 colum과 설정(설정 관련해 DB 지식을 알고 있다고 간주)
  
5. 데이터 넣기 및 조회
  - 좌측 상단 메뉴에 SQL Script 메뉴를 클릭 후 데이터를 넣는 INSERT SQL 문을 작성해 실행
  ![25](https://user-images.githubusercontent.com/79196972/109802307-fa206b80-7c62-11eb-9833-4d4f5b7a6267.PNG)
  
  데이터가 정상 INSERT 됐다면, 조회 또한 가능함.
  
6. 스프링 , MariaDB, MyBatis 연동, 데이터 조회
  - pom.xml 수정
  ```xml
<!-- DB -->
        <!-- Maria DB -->
        <dependency>
            <groupId>org.mariadb.jdbc</groupId>
            <artifactId>mariadb-java-client</artifactId>
            <version>2.0.3</version>
        </dependency>
 
        <!-- DBCP 데이터베이스 풀 커넥션 -->
        <dependency>
            <groupId>commons-dbcp</groupId>
            <artifactId>commons-dbcp</artifactId>
            <version>1.4</version>
        </dependency>
 
        <!-- Spring JDBC -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jdbc</artifactId>
            <version>4.3.9.RELEASE</version>
        </dependency>
 
        <!-- Mybatis -->
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis</artifactId>
            <version>3.4.4</version>
        </dependency>
 
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis-spring</artifactId>
            <version>1.3.1</version>
        </dependency>
        
                <!-- Mybatis log -->
        <!-- https://mvnrepository.com/artifact/org.bgee.log4jdbc-log4j2/log4jdbc-log4j2-jdbc4.1 -->
        <dependency>
            <groupId>org.bgee.log4jdbc-log4j2</groupId>
            <artifactId>log4jdbc-log4j2-jdbc4.1</artifactId>
            <version>1.16</version>
        </dependency>
```
  - mariadb, mybatis 관련 dependency를 추가
  - 마지막 dependency인 log4jdbc-log4j2-jdbc4.1은 로그를 남기기 위한 라이브러리

  - root-context.xml 수정
  ```xml
<bean id="dataSource"
        class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName"
            value="net.sf.log4jdbc.sql.jdbcapi.DriverSpy"></property>
        <property name="url"
            value="jdbc:log4jdbc:mariadb://127.0.0.1:3306/theater" />
        <property name="username" value="root" />
        <property name="password" value="설정한비밀번호" />
    </bean>
 
 
    <bean id="sqlSessionFactory"
        class="org.mybatis.spring.SqlSessionFactoryBean">
        <property name="dataSource" ref="dataSource"></property>
        <property name="configLocation"
            value="classpath:/mybatis/mybatis-config.xml"></property>
        <property name="mapperLocations"
            value="classpath*:/mybatis/sql/*.xml"></property>
    </bean>
 
    <bean id="sqlSession"
        class="org.mybatis.spring.SqlSessionTemplate">
        <constructor-arg name="sqlSessionFactory"
            ref="sqlSessionFactory"></constructor-arg>
    </bean>
 
    <!-- <mybatis-spring:scan base-package="com.devfun.dao" /> -->
    <context:component-scan
        base-package="com.devfun.dao"></context:component-scan>
    <context:component-scan
        base-package="com.devfun.service"></context:component-scan>
```
 - root-context.xml은 웹 이외의 부분을 셋팅하기 위해 존재

  Datasource는 DB 연결 정보로 "로컬주소/스키마"로 이루어져 있고, ID와 PW를 입력. ex) mybatis, mariadb
  
  - 로그를 확인하기 위해 log4jdb를 property에 추가
  - sqlsessionfactoryBean은 mariadb 설정 기능을 사용하도록 세팅, mapperLocation 즉 SQL문을 mybatis/sql 경로에 있는 xml파일로 한다고 명시
  - SqlsessionTemplate는 트랜잭션 관리와 쓰레드 처리, DB 연결 및 종료를 관리하는 영역

  정리하면 mybatis-config.xml(마이바티스 설정)파일은 resource -> mybatis에 존재해야하며, SQL을 담고있는 xml파일인 test.xml은 mybatis/sql 경로 안에 존재해야 합니다.
  
  - mybatis-config.xml 작성
  ```
    <?xml version="1.0" encoding="UTF-8"?>
  <!DOCTYPE configuration
    PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
    "http://mybatis.org/dtd/mybatis-3-config.dtd">

  <configuration>
    <typeAliases>
      <typeAlias type="com.moses.vo.MovieVO" alias="movieVO" />
    </typeAliases>
  </configuration>
```

  - logback.xml 작성
    자바 오픈소스 로깅 프레임워크인 logback의 설정파일
    위치는 src/main/resources/logback.xml
    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <configuration>
	  <include resource="org/springframework/boot/logging/logback/base.xml"/>
    
    <!-- log4jdbc-log4j2 -->
    <logger name="jdbc.sqlonly"     level="DEBUG" />
    <logger name="jdbc.sqltiming"     level="INFO" />
    <logger name="jdbc.audit"         level="WARN" />
    <logger name="jdbc.resultset"     level="ERROR" />
    <logger name="jdbc.resultsettable" level="ERROR" />
    <logger name="jdbc.connection"     level="INFO" />

    </configuration>
    ```
    
  - log4jdbc.log4j2.properties 작성
  위치는 src/main/resource/log4jdbc.log4j2.properties
  ```
  log4jdbc.drivers=org.mariadb.jdbc.Driver
  log4jdbc.spylogdelegator.name=net.sf.log4jdbc.log.slf4j.Slf4jSpyLogDelegator
  log4jdbc.dump.sql.maxlinelength=0
  ```
  
  - test.xml 작성
 위치는 src/main/resource/mybatis/sql/test.xml
  ```
  <?xml version="1.0" encoding="UTF-8" ?>
  <!DOCTYPE mapper
  PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
  "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
 
  <mapper namespace="com.moses.mybatis.sql.test">
	<select id="selectMovie" resultType="movieVO">
		SELECT MOVIE_NAME, DIRECTOR, TYPES FROM MOVIE
	</select>
</mapper>
  ```
  
- 데이터 조회/처리를 위한 java코드 작성
![26](https://user-images.githubusercontent.com/79196972/109808418-710d3280-7c6a-11eb-8455-06d5d2340117.PNG)

자바코드는 src/main/java 안에 존재
위 구조와 같이 패키지와 파일 구조로 이루어져 있음

- MovieDAO.java 작성
```
package com.test.dao;
import java.util.List;
import com.test.vo.MovieVO;
 
public interface MovieDAO {
    public List<MovieVO> selectMovie() throws Exception;
}
```
MovieDAO는 MoiveVO를 담고 있는 리스트를 가지는 함수가 있는 인터페이스를 작성

- MovieDAOImpl.java 작성
```
import java.util.List;
import javax.inject.Inject;
import org.apache.ibatis.session.SqlSession;
import org.springframework.stereotype.Repository;
 
import com.test.vo.MovieVO;
 
@Repository
public class MovieDAOImpl implements MovieDAO {
 
    @Inject
    private SqlSession sqlSession;
    private static final String Namespace = "com.devfun.mybatis.sql.test";
    
    @Override
    public List<MovieVO> selectMovie() throws Exception {
 
        return sqlSession.selectList(Namespace+".selectMovie");
    }
 
}
```
MovieDAOImpl의 경우 Sqlsession을 통해 등록된 SQL 쿼리문을 실행하여 List를 리턴
MovieDAOImpl 작성 후 root-context.xml에 dao를 등록(스프링에서 스캔을 통해 빈으로 등록하게 하기 위한 설정)
component-scan에 해당하는 내용으로 앞서 등록한 root-context.xml에서 확인 가능

- MovieServiceImpl 작성
```
import java.util.List;
import javax.inject.Inject;
import org.springframework.stereotype.Service;
 
import com.devfun.dao.MovieDAO;
import com.devfun.vo.MovieVO;
 
@Service
public class MovieServiceImpl implements MovieService {
 
    @Inject
    private MovieDAO dao;
    
    @Override
    public List<MovieVO> selectMovie() throws Exception {
 
        return dao.selectMovie();
    }
 
}
```
- HomeController.java 작성
```
package com.test.settingweb;

import java.util.List;
import java.util.Locale;
 
import javax.inject.Inject;
 
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
 
import com.test.vo.MovieVO;
import com.test.service.MovieService;
 
/**
 * Handles requests for the application home page.
 */
@Controller
public class HomeController {
    
    private static final Logger logger = LoggerFactory.getLogger(HomeController.class);
    
    @Inject
    private MovieService service;
    
    /**
     * Simply selects the home view to render by returning its name.
     */
    @RequestMapping(value = "/", method = RequestMethod.GET)
    public String home(Locale locale, Model model) throws Exception{
 
        logger.info("home");
        
        List<MovieVO> movieList = service.selectMovie();
        
        model.addAttribute("movieList", movieList);
 
        return "home";
    }
    
}
```
RequestMapping에서는 호출하기 위한 url의 path임.
여기에서는 "/"로 작성.
controller에서는 service에서 selectMovie를 호출해 model에 담은 후 해당 내용을 화면으로 전달.
return "home"의 경우 home.jsp 화면으로 전달한다는 내용임.

- MovieVO.java 작성
```
package com.test.vo;

public class MovieVO {
	private String movie_name;
	private String director;
	private String types;
	
	public String getMovie_name() {
		return movie_name;
	}
	public void setMovie_name(String movie_name) {
		this.movie_name = movie_name;
	}
	public String getDirector() {
		return director;
	}
	public void setDirector(String director) {
		this.director = director;
	}
	public String getTypes() {
		return types;
	}
	public void setTypes(String types) {
		this.types = types;
	}
}
```

- home.jsp 작성
```jsx
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
<html>
<head>
<title>Home</title>
</head>
<body>
    <h1>Hello world!</h1>
 
    <table>
        <thead>
            <tr>
                <th>영화이름</th>
                <th>감독</th>
                <th>장르</th>
            </tr>
        </thead>
        <tbody>
            <c:forEach items="${movieList}" var="movie">
                <tr>
                    <td>${movie.movie_name}</td>
                    <td>${movie.director}</td>
                    <td>${movie.types}</td>
                </tr>
            </c:forEach>
        </tbody>
    </table>
 
 
</body>
</html>
```
movieList를 받아 c:forEach문으로 조회된 결과를 뿌려줌.
실무에서는 보통 데이터를 json으로 받아와 Dom id를 설정한 후, javascript, jquery, angularjs 등으로 동적으로 뿌림.

- tomcat 세팅 변경
  Server 탭에서 구동할 서버 더블 클릭 -> Module 탭 클릭 -> Path를 /로 수정

-- 결과 -- 

![27](https://user-images.githubusercontent.com/79196972/109810286-b599cd80-7c6c-11eb-87a3-bae2189d7841.PNG)
