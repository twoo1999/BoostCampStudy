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

# 개선 후 논의 사항

### 타입스크립트

타입스크립트는 변수의 타입을 지정함으로써 알 수 없는 에러를 예방하고 또한 함수를 사용할 때 타입에 맞는 함수만 나와 코딩할 때 매우 편리

또한 타입이 없는 언어는 개인 개발에서는 매우 편리하지만 협업의 관점에서 보면 가독성이 낮고 분석하기 힘든 부분이 꽤 큼

이러한 점에서 타입스크립트는 가독성을 올려주고 협업하는 부분에 있어서 자바스크립트보다 더 좋은 효과를 보임

그래서 어차피 해야할거 지금부터 많이 연습을 해서 익숙해져야한다.

### 비동기 / 동기

이번 과제는 fs를 사용하는 부분이 많았음

그래서 모두 Sync가 포함된 함수를 사용했음

근데 비동기 프로그램에 익숙해지기 위해서는 단순히 Sync가 포함된 동기 모듈을 사용하는 것이 아닌 간단한 것 부터 promise, async/await를 사용해서 익숙해지고 공부하는 것이 좋음

그래서 시간이 있으면 Sync 모듈을 사용하던 부분을 전부 async/await를 사용해서 개선해보는 것도 좋은 공부가 될 수 있을 것.
