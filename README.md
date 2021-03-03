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
