# DAY02

### 가상 환경(Virtual Machine)

실제 컴퓨터 대신 소프트웨어를 사용하여 프로그램을 실행하고 앱을 배포하는 컴퓨팅 리소입니다. <br>하나 이상의 가상 게스트 시스템(OS)가 물리적 호스트 시스템(로컬)에서 실행됩니다.

### ubuntu

영구 기업 캐노니컬이 개발, 배포하는 컴퓨터 운영체제입니다.<br>데비안 리눅스를 기반으로 개발되며, 데비안에 비해 사용자 편의성에 초점을 맞춘 리눅스 배포판입니다. <br> 즉 리눅스는 핵심 운영 체제이고 ubuntu는 리눅스 배포본인 운영체제입니다.

### ssh

ssh란 시큐어 셀(Secure Shell)은 네트워크 상의 다른 컴퓨터에 연결하거나 원격 시스템에서 명령을 실행하고 다른 시스템으로 파일을 복사할 수 있도록 해주는 응용프로그램 또는 그 프로토콜입니다. 즉 컴퓨터와 컴퓨터가 서로 통신을 할 때 보안적으로 통신할 수 있도록 도와주는 프로토콜입니다.

### Shell

리눅스의 셸은 명령어와 프로그램응 실행할 때 사용하는 인터페이스 입니다. 즉 셸은 커널과 사용자 간의 다리 역할 을 하는 것으로 명령을 받아 해석하여 프로그램을 실행하는 역할을 합니다.

### bash

현재 리눅스의 표준 셸입니다.
<br>[참고]https://jhnyang.tistory.com/entry/%EB%A6%AC%EB%88%85%EC%8A%A4%EC%85%B8Shell%EC%9D%B4%EB%9E%80-%EC%85%B8%EC%9D%98-%EB%B3%80%EA%B2%BD-%EC%89%98-%EA%B0%9C%EB%85%90-%EA%B8%B0%EB%8A%A5-%EC%A2%85%EB%A5%98%EC%99%80-%ED%8A%B9%EC%A7%95sh-bash-csh-tcsh-ksh

### NAT

VMWare를 실행하는 PC에서 가상머신 안에 설치된 OS에게 IP를 할당합니다. 마치 공유기가 하나의 외부 IP를 받은 후에 그 안에서 여러 기기에게 내부 IP를 알아서 할당하는 것과 마찬가지입니다.

### bridged

VMWare가 설치된 PC상에 깔린 OS라고 하더라도, 마치 공유기에 직접 연결되어 있는 PC인 것처럼 인식하게 만들어줍니다. 즉 물리적으로 존재하는 컴퓨터인 거처럼 만들어주고, 따라서 우분투에 SSH만 설치하면 22번 포트를 통해 바로 접속이 가능합니다. ssh 원격접속에서는 이 방법을 택했습니다.

### ssh 연결 준비

sudo -s // root 전환<br>
apt-get install ssh // ssh 설치<br>
service ssh start // 서버 시작<br>
service ssh status // 현재 상태 확인<br>
[참고] https://velog.io/@nathan29849/Linux-ssh%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%98%EC%97%AC-%EA%B0%80%EC%83%81%EB%A8%B8%EC%8B%A0%EC%97%90-%EC%9B%90%EA%B2%A9%EC%9C%BC%EB%A1%9C-%EC%A0%91%EC%86%8D%ED%95%98%EA%B8%B0

### 유저 생성

sudo adduser BoostTest
후에 home에서 ls 실행 시 계정 하나가 더 생긴 것을 볼 수 있다.

### 로컬 컴퓨터에서 가상환경으로 원격 접속하기

가상환경에서
sudo apt-get install net-tools를 통해 IP확인 툴을 install 한다.
ifconfig를 통해 가상환경의 ip를 확인한다.
로컬에서는 터미널에 ipconfig를 통해 로컬 ip를 확인한다.

### 디렉토리 생성

mkdir

### 권한부여

chmod [권한] [파일]<br>
r : 읽기<br>
w : 쓰기<br>
x : 실행<br>
1 : 가능<br>
0 : 불가능

### 리눅스 설치

[참고] https://travel-log.tistory.com/33

### Axios

node.js와 브라우저를 위한 Promise 기반 HTTP통신 라이브러리입니다.

### cheerio

Node.js에서 HTML을 파싱해서 Scrapping하기 위한 라이브러리입니다.

### iconv-lite

EUC-KR
UTF-8

### Promise

JS는 비동기 처리 방식을 가집니다. 특정 코드가 실행되도 완료될 때까지 기다리는 것이 아니라 다음 코드를 우선 수행하는 특징을 가집니다.
이러한 특징을 가지는 상황에서 HTTP get을 통해 정보를 가져온다라고 가정합십다. 그런 상황에서 이 정보를 통해 어떤 작업을 처리한다고 하면 아직 정보를 다 받아오지도 않았는데 뒤의 내용이 실행이 된다면 문제가 생깁니다. 이러한 문제를 방지하는 것이 Promise입니다.

### jquery

자바스크립트 언어를 간편하게 사용할 수 있도록 단순화시킨 오픈소스 기반의 자바스크립트 라이브러리입니다.
