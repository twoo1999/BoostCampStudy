### VCS

버전 관리 시스템(VCS, Version Control System) : 파일의 변화를 시간에 따라 기록했다가 후에 특정 시점의 버전을 다시 불러올 수 있는 시스템

#### 로컬 버전 관리

- 관리하기 쉬움
- 실수하기 쉬움
- RCS(Revision Control System)

#### 중앙집중식 버전 관리

- 여러 사람과 함께 작업해서 생기는 문제를 해결하기 위해 개발
- 로컬 버전 관리 보다 관리가 쉽다
- 중앙 서버에 문제가 생기면 치명적이다.
- CVS, Subversion, Perforce

#### 분산 버전 관리

- 파일의 마지막 스냅샷을 Checkout하지 않고 저장소를 히스토리와 함께 전부 복제
- 서버에 문제가 생겨도 복제물로 다시 작업 가능
- 많은 수의 리모트 저장소를 가지기 때문에 다양한 방법으로 협업할 수 있음
- Git
  [참고] https://yoongrammer.tistory.com/17

### git

https://yanacoding.tistory.com/4

### repository

데이터 집합체가 보관되고 조직적인 방식으로 유지되는 대체로 컴퓨터 저장장치 내의 주요 장소이다

### SHA(해쉬 알고리즘)

https://sisiblog.tistory.com/317

### hash와 맵

key와 value로 이루어진 데이터 구조

JS에서는 object, Map, Set등이 있다

https://velog.io/@jun094/Hash%EC%99%80-Map

### 파일 상태

untracked : git으로 버전관리 하지 않는 상태, 파일을 추적 관리하지 않는 상태
unmodified : git add로 파일이 staging Area에 올라갔지만 파일 변경은 없는 상태, git은 이 파일을 추적관리하고 있다.
modified : 추적 관리하던 파일이 수정된 상태
staged : staging area에서 file이 staged 되어 반영된 상태

### fs

https://www.daleseo.com/js-node-fs/

### zlib

파일의 압축을 도와주는 기본 모듈이다

https://m.blog.naver.com/kim-stone/60189885812
