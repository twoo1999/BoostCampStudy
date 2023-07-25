### 비동기 처리 문법

비동기 처리 문법에는 현재 많이 사용하는 async/await가 있습니다.

근데 이 문법은 기존에 사용하던 Promise를 사용하기에 Promise에대 자세히 배울 필요가 있다고 판단됩니다.

- `callback 함수`

  콜백 함수란 특정 함수에 매개변수로 전달된 함수를 의미합니다. JS에서는 함수 또한 변수에 저장할 수 있는 객체이니까요.

  다만 비동기에서 콜백함수를 실행한다면 이런식의 구조를 가질 것 입니다.

  ```
  function func(){
    setTimeout(()=>{
      console.log('1');
      setTimeout(()=>{
        console.log('2');
        setTimeout(()=>{
          console.log('3');
        }, 1000)
      }, 1000)
    }, 1000)
  }
  ```

  위의 프로그램은 1초에 한 번씩 1 2 3을 출력하는 함수입니다.

  위와 같이 어떤 동작 후에 원하는 동작을 하고 싶다면(1을 출력하고 2를 출력하고 3을 출력하는 동작)콜백함수를 사용할 수 있습니다. 다만 콜백함수를 남용하게 되면 흔히 말하는 콜백 지옥이 발생할 수 있습니다.

  이런 문제를 해결하기 위해 JS에서는 Promise라는 것을 두어 비동기를 제어합니다.

- `Promise`

  ES6의 문법으로 추가된 Promise입니다.

  기본적인 문법은

  ```
  let promise = new Promise((resolve, reject)=>{
    // 동작
  })
  .then(콜백함수)
  .catch(콜백함수)

  ```

  - 동작(executor)
    - Promise를 처음 생성되면 실행되는 부분
    - resolve, reject를 부르는 역할
  - resolve
    - 정상 처리되면 value와 함께 호출
  - reject
    - 에러 혹은 예외 처리할 때 error 객체와 함께 호출
  - then
    - 동작 부분에서 resolve를 value와 함께 호출하면 then의 매개변수인 콜백함수가 실행(콜백함수의 매개변수는value)
  - catch
    - 동작 부분에서 reject를 error 객체와 함께 호출하면 catch의 매개변수인 콜백함수가 실행(콜백함수의 매개변수는error)

  ````

      let promise = new Promise((resolve, reject) => {
        setTimeout(() => {
          console.log('1');
          resolve(2);
        }, 1000);
      })
        .then((value) => {
          return new Promise((resolve, reject) => {
            setTimeout(() => {
            console.log(value);
            resolve(3);
          }, 1000);
        });
      })
        .then((value) => {
          return new Promise((resolve, reject) => {
            setTimeout(() => {
            console.log(value);
            reject('초과');
          }, 1000);
        });
      })
        .catch((err) => {
          console.log(err);
        });

    ```
    위와 같이 promise를 반환하며 계속 연결되는 것을 프로미스 체이닝이라고 합니다.


    즉 Promise는 콜백함수의 depth가 깊어지는 것을 방지하고자 등장했습니다.

  ````

- `async,await`
  ES7의 문법으로 추가된 async,await 입니다.

  기존의 Promise 또한 콜백지옥을 완화시켜줬지만 then에 콜백함수를 넣어줌으로써 콜백함수의 가독성 저하는 해결하지 못했습니다.

  그리하여 ES7부터는 한층 간결하고 직관적으로 코드 작성할 수 있도록 async,awiat를 추가했습니다.

  - async
    - 함수 앞에 작성
  - await
    - async로 작성된 함수안에서만 사용

[참고]

https://ko.javascript.info/async

https://thisisprogrammingworld.tistory.com/99#Promises

https://hanamon.kr/javascript-%EC%BD%9C%EB%B0%B1-%EC%A7%80%EC%98%A5-%ED%83%88%EC%B6%9C%ED%95%98%EA%B8%B0-%EB%B9%84%EB%8F%99%EA%B8%B0-%EC%B2%98%EB%A6%AC-%EB%B0%A9%EB%B2%95/

https://www.youtube.com/watch?v=m0icCqHY39U

### 병렬처리와 스레드

- 병렬 처리 :
  동시간에 두개 이상의 동작이 처리되는 것
- 스레드 :
  context switch을 통해 동시성을 만족하는 것

동시성과 병렬처리의 관계는 살짝 다릅니다.

동시성은 하나의 작업이 끝나진 않았지만 다른 작업을 실행해서 동시에 하는 것을 만족시킵니다.

이는 물리적으로 같은 시간에 두개의 동작을 한다는 느낌은 아닙니다.

그래서 스레드에 배울 때 context switch을 배웠습니다.

그러나 병렬 처리는 멀티 코어 시스템에서 물리적으로 같은 시간에 여러 동작을 수행하는 것입니다. 진짜로 동시에 처리를 하는 것이죠.

그러니 병렬 처리 > 스레드 의 느낌입니다. 완전히 같은게 아니라 비교가 불가능하지만 그래도 느낌상에는 이정도로 표현하겠습니다.

하지만 멀티코어시스템에서는 스레드를 통해 병렬처리가 가능합니다.

그리고 스레드에서 나왔던 공유자원의 문제 또한 병렬처리에서 발생하며 이를 동기화해주는 방법이 필요한데 이 또한 뮤텍스, 세마포어 등으로 처리합니다.
[참고]

https://vagabond95.me/posts/concurrency_vs_parallelism/

https://velog.io/@honeyoung_0117/%EB%B3%91%EB%A0%AC%EC%B2%98%EB%A6%AC

### 스레드 풀

스레드가 많아져 CPU가 부담하는 일이 많아지면 이는 성능 저하로 이어집니다. 그래서 스레드 풀을 사용합니다.

스레드는 정해진 수만큼 생성하고 작업 큐라는 것을 만들어 작업을 저장합니다.

스레드는 직접 작업을 할당받는 것이 아닌 작업 큐의 작업을 하나씩 가져와 실행하기 때문에 CPU가 받는 부하가 적어집니다.

따라서 작업이 많아져도 작업 큐에 작업이 쌓일 뿐 CPU가 받는 부담은 일정하게 됩니다.

다만 단점 또한 존재합니다.

너무 많은 작업은 메모리의 낭비를 발생시킬 수 있습니다.

또한 너무 많은 스레드의 생성 또한 메모리의 낭비로 이어질 수 있습니다.
[참고]

https://steady-coding.tistory.com/548

### Event Emiter / 이벤트 큐 / 이벤트 핸들러

비동기 프로그래밍의 이벤트 루프와 이벤트 이미터는 다른 개념입니다.
이벤트 루프는 이전 과제에 정리했습니다.

https://gist.github.com/twoo1999/b5e657dd027cb9fab22fa0b93aaac120

간단히 말하면 Event Loop는 Node.js의 비동기식 동작을 관리하는 역할을 하고있고 이벤트 이미터는 특정 이벤트에 연결된 리스너를 추적합니다.

이벤트 리스너를 등록하면 이미터 객체 내부에 저장됩니다.

왼쪽은 이벤트 큐이고 각자의 이벤트에 해당되는 핸들러(콜백함수)가 실행되는 구조입니다.

또한 이벤트 이미터를 통해 이벤트 헨들러를 동작시키면 이는 동기적으로 동작합니다.

![이벤트 이미터](https://user-images.githubusercontent.com/125804293/255561894-577afc07-a5ea-4d5b-84c6-069fbdf7a7d5.jpg)

### Event Emitter 문법

EventEmitter.on(event, ,listener) / .addListener
특정 이벤트가 발생했을 때 호출됩니다.

.once
이벤트가 처음 발생했을 때 수행되고 사라집니다..

.emit
이벤트를 발생시킵니다.

.removelistener / .removeAllListeners
특정 이벤트의 리스너를 제거합니다.

[참고]

https://yceffort.kr/2021/06/misconceptions-on-nodejs

# 토론을 하고 난 후

하나의 문제로도 많은 의견이 있을 수 있다는 것을 다시금 느꼈습니다.

개인적으로 아쉬운 점은 이벤트를 실생활에 사용하는 것처럼 더 효율적으로 사용하는 방법을 끊임없이 고민했으나 아이디어가 잘 나오지 않았습니다.

이벤트를 저런 형식으로 사용할 수 있구나란 부분을 알 수 있어 새로웠던 시간이었습니다.

모든 과정이 자연스럽게 끝나는 조건을 어떻게 구현할까 생각하던 중 한 캠퍼분이 재귀호출을 이용해 자연스럽게 종료하는 코드를 봤습니다. 매우 좋은 방법이라고 생각하고 나도 해야지 라고 생각하는 찰나 다른 캠퍼분께서 재귀 호출은 콜스택이 많이 쌓이니 이벤트를 활용해서 재귀적(?)호출하는 방법을 사용했다고 말씁하셨습니다. 사실 이벤트라 재귀적이다라는 표현 자체가 어색하지만 그래도 그런 느낌으로 받아들여 이렇게 적었습니다.

다시금 사람들의 생각은 무한하고 이를 공유함으로써 한 층 더 나아갈 수 있다고 생각했습니다. 저도 하루 빨리 남들에게 도움이 될 수 있는 개발자가 될 수 있도록 노력해야겠습니다.
