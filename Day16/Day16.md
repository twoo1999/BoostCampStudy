### 파일 시스템

파일이나 자료를 쉽게 발견 및 접근할 수 있도록 보관 또는 조직하는 체제

파일 시스테은 두가지로 나뉨

메타영역, 데이터 영역

메타영역은 파일에 대한 정보을 저장(파일이름, 파일위치, 파일 크기, 파일 유형 등)

데이터 영역은 실제 데이터를 포함한다.

https://plummmm.tistory.com/14

https://lgana1021.tistory.com/79

### 파일과 디렉토리

파일은 실제 데이터를 담고 있는 개별 문서를 의미.

디렉토리 또한 하나의 파일인데 디렉토리는 파일을 모아놓는 장소

하지만 폴더와는 다른점이 있음

폴더는 일종의 가상분류이지만 디렉토리는 일종의 전화번호부임

디렉토리에는 파일의 위치 등을 담아 사용 시 파일을 연결해주는 역할을 함

### HTTP

를 배우기 이전에 웹에 대해 간단히 학습

인터넷 !== 웹

웹은 인터넷에서 정보를 교환하기 위해 인터넷 위에서 제공하는 시스템

그 정보 교환을 위해 서로 간에 하는 약속이 HTTP

Hyper Text Transfer Protocol

Transfer Protocol는 통신 규약이니 그러려니 하는데 Hyper Text는 뭔가 싶었음

하이퍼 텍스트를 알기위해 하이퍼 링크를 말해보자면 하이퍼링크는 텍스트에 참조고리를 형성하여 파일, 사진, 영상 등의 위치를 지정할 수 있다.

하이퍼 텍스튼느 하이퍼링크를 나타낼 수 있는 텍스트를 의미한다.

즉 하이퍼 링크를 통해 다른 문서로 이동할 수 있는 글을 의미한다.

### 데이터 베이스

특정 정보를 저장하는 곳, 한 곳에 저장한 정보는 어디에서나 접근해서 가져올 수 있음

원하는 정보를 넣고 가져오는 등의 기능을 하는 것이 DBMS(DataBase Management System) 즉, 하나의 S/W임

### SQL(Structured Query Language)

데이터 베이스에서 데이터를 추출하고 조작하는 데에 사용하는 데이터 처리 언어

### 관계형 데이터베이스(RDB)

테이블, 행, 열의 정보르 구조화하는 방식

테이블을 조인하여 정보 간 관계 또는 링크를 설정할 수 있는 기능이 있어, 여러 데이터 포인트 간의 관계를 쉽게 이해하고 정보를 얻을 수 있음.

이러한 RDB를 저장, 수정, 삭제 및 검색할 수 있도록 하는 언어가 SQL임

관계형 데이터베이스는 데이터를 구성, 관리, 연결하는 데 도움이 되는 스프레드시트 파일 모음이라고 생각

스프레드시트는 열과 행으로 대표되는 정보를 저장하는 테이블

모든 테이블에는 각자의 고유한 키가 있으며 다른 테이블의 키를 참조하여 테이블간의 관계를 만들어낼 수 있음

https://cloud.google.com/learn/what-is-a-relational-database?hl=ko

https://www.youtube.com/watch?v=dgpBXNa9vJc

### mysql 실행

MySQL Server 8.0/bin에서 cmd를 통해 연결