# AWS_1

분류: AWS

# AWS

<aside>
💡 **AWS(Amazon Web Services)**
아마존에서 제공하는 클라우드 컴퓨팅 플랫폼
클라우드 컴퓨팅을 중심으로 다양한 기능을 제공해 관련 서비스 업계의 상당 부분을 점유하고 있음

</aside>

- 주요 기능
    - Strorage / DB
        - Amazon S3(Simple Storage Service)
        - Amazon RDS
    - 네트워킹
    - 관리 및 보안
    - 인공지능
        - 머신러닝 모델 빌드 및 훈련, 배포
    - 서버리스, 애플리케이션 통합

# Lightsail로 Springboot 프로젝트 배포하기

### 1. Lightsail 셋업

1. **Springboot 프로젝트의 pom.xml을 우클릭, Run As의 Maven bulid 클릭**
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled.png)
    

1. Goals에 package 입력 후 Run 클릭
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%201.png)
    

1. project/target 디렉토리에 project-0.0.1-SNAPSHOT.jar가 생긴 것을 볼 수 있다.
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%202.png)
    

1. AWS에 접속하고 Lightsail을 검색한다.
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%203.png)
    
    <aside>
    💡 Lightsail
    AWS에서 제공하는 쉽고 가벼운 클라우드 서비스
    보통 소규모 팀 혹은 회사에서 사용한다.
    간단하게 웹 애플리케이션을 배포, 확장할 수 있게 해준다.
    
    </aside>
    
2. 인스턴스를 생성한다.
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%204.png)
    
3. 알맞은 Linux 배포판을 선택한다.
알맞은 요금제를 선택한다.
선택을 마치면 맨 아래의 인스턴스 생성 버튼을 누른다.
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%205.png)
    
4. 생성한 인스턴스를 클릭하고 네트워킹 탭을 선택한다.
    
    IPv4 방화벽에서 규칙 추가를 선택하고 이름과 TCP, 사용할 포트 번호를 입력한다.
    
    포트 번호는 Springboot 프로젝트의 app.properties에서 설정한 포트 번호와 일치해야 한다. 
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%206.png)
    
5. aws-key.pem 다운로드
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%207.png)
    
    - 원하는 위치에 .pem 확장자로 저장

### 2. MobaXterm 설치 및 배포

1. **MobaXterm을 설치한다.**
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%208.png)
    
2. **MobaXterm 실행 후 Session - SSH 선택**
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%209.png)
    
3. **Session Setting**
    
    ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%2010.png)
    
    - Remote host에는 아까 생성했던 인스턴스의 퍼블릭 IPv4 주소 입력
    - Specify username에는 ubuntu 입력
    - Use private key에는 아까 다운받은 aws-key.pem 파일 업로드
    
    1. 터미널을 통해 자바 설치 / 컨테이너에 jar 파일 업로드
        
        ![Untitled](AWS_1%204e32c21a4d684cfaaa3b04c901950ab3/Untitled%2011.png)
        
        ```powershell
        sudo apt update
        sudo apt install openjdk-17-jdk
        ```
        
        - 아까 생성한 .jar 파일 드래그 앤 드랍으로 업로드 후 아래 코드 실행
        
        ```powershell
        java -jar "파일명"
        ```