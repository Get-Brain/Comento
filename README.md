# Mac OS 환경에서 스프링 개발환경 셋팅

1. JDK 설치
  - 오라클 사이트에서 다운로드
  <img width="1301" alt="InstallJava" src="https://user-images.githubusercontent.com/79196972/109389950-26ca3f80-7952-11eb-9537-5636c965c1b2.png">

  설치 후 JDK가 제대로 깔렸는 지 확인!! -> Terminal을 열어서, 아래 명령을 입력합니다.
  <img width="650" alt="java_version" src="https://user-images.githubusercontent.com/79196972/109389974-3ea1c380-7952-11eb-8588-13be13560663.png">
  
  (저는 이미 11 버전이 깔려 있어서 8 버전이 아닙니다.)
  
  - 자바 환경변수 설정
    ``` 
        cd /Library/Java/JavaVirtualMachines
        -> 위 경로로 이동
    
        ls
        -> 설치된 버전의 JDK가 보일 것이다.
        
        cd jdk 설치한 버전.jdk/Contents/Home/
        -> jdk 홈 디렉터리 이동
        
        vi ~/.bash_profile
        -> bash_profile 파일 편집기로 열기
        
        JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk 설치된 버전.jdk/Contents/Home
        -> 자바 환겨 변수를 위 문장 그대 적어준 뒤, ESC키르 누른 후, :wq! 를 쳐서 저장 후 나온다.
        
        java --version
        -> 위 명령을 자바 버전을 확인한다.
  
  
2. 인텔리제이 설치
  - 자바 설치 후 자바를 사용하기 위한 인텔리제이 설치
    인텔리제이 홈페이지 접속 후 다운로드(https://www.jetbrains.com/ko-kr/idea/)
    <img width="1322" alt="Intellij_homepage" src="https://user-images.githubusercontent.com/79196972/109390595-fbe1ea80-7955-11eb-9f27-dd496a7fe118.png">
    다운로드 클릭해서 설치
    
    

   
    

    
  
  
