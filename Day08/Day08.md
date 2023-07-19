### path

리눅스 기준 ':' 이라면 여러개의 경로를 포함합니다. path를 출력 시 ':' 를 통해 구분되어 나옵니다.
윈도우는 기준 ';'입니다.

### .gitignore

foldername/

\*.json

을 통해 필요하지 않는 파일은 업로드 안 할 수 있습니다.

### Jest

코드가 제대로 동작하는 지 확인하는 테스팅 프레임워크입니다.

### Jest 시작

npm install --save-dev jest

package.json 하단에 {"script : {"test" : "jest}}추가

npm start를 통해 테스트 시작

### 기본 문법

- describe(name, func) :<br>
  테스트 그룹을 묶어주는 역할을 합니다. 또한 내부에 변수, 객체들을 선언하고 일회용으로 사용 가능합니다.

- expect:<br>
  값을 테스트 할 때마다 주로 matcher와 함께 사용합니다. func에 넣고 나중에 결과와 비교할 수 있다.(실제 함수를 테스트하는 당사자)

- matcher
  내가 원하는 방법으로 테스트할 수 있습니다.

  - tobe : 완전히 똑같을 때
  - toEqual, toStrictEqual : 객체의 값을 비교
  - not : 매처와 반대되는 케이스를 테스트 할 때 사용(not.toBe())
  - toMatch : 정규표현식을 검증할 때 사용
  - toContain : 배열, 이터러블 등에 특정 항목이 포함되어 있는지 테스트 할 때 사용
  - toThrow : 오류를 Throw하는 지 확인

  - beforEach : 여러개의 test 시 test 실행 전 실행되는 부분
  - afterEach : 여러개의 test 시 test 실행 후 실행되는 부분
  - beforAll : 모든 test의 실행 전 실행되는 부분
  - afterEach : 모든 test의 실행 후 실행되는 부분
