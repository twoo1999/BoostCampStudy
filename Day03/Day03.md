### 정규표현식

### trim

공백제거하는데 사용했습니다.

### import / export

npm init을 통해 프로젝트를 생성하고 생성된 package.json파일에 "type":"module"을 추가하면 외부 생성한 모듈을 가져와 사용할 수 있습니다.

### tokenizer

어떤 구문을 토큰화해줍니다.<br>
토큰 : 어휘 분석의 단위를 뜻하며 문자열을 의미있는 단위로 나눠줍니다.
본 과제에서 tokenizer는 의미있는 단위로 쪼개 배열에 저장하는 역할을 하게됩니다.

### Lexer

Tokenizer에 의해 의미있는 토큰 단위로 쪼개진 문장을 분석하는 역할을 가집니다.

### parser

위의 과정을 거친 데이터를 구조적으로 나타냅니다.