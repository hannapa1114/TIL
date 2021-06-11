### Throttling & Debouncing

1. Throttling
- 마지막 함수 호출 혹은 이벤트 발생 이후 일정시간 동안 다시 호출되거나 발생하지 않게 하는 것
ex) 웹페이지 스크롤에 무한스크롤 이벤트가 있다고 가정했을때 잦은 스크롤링은 서버에 과부하, 클라이언트 단에 성능저하를 가져올 수 있음
    스크롤 시 2초 안에는 해당 이벤트가 발생하지 않도록 막아 놓는 방법으로 활용할 수 있을 것 같다.

```
throttleBtn.addEventListener('click', throttle(function() {
  return console.log('Hey! It is', new Date().toUTCString());
}, 1000));

const throttle = (func, limit) => {
  let lastFunc
  let lastRan
  return function() {
    const context = this
    const args = arguments
    if (!lastRan) {
      func.apply(context, args)
      lastRan = Date.now()
    } else {
      clearTimeout(lastFunc)
      lastFunc = setTimeout(function() {
        if ((Date.now() - lastRan) >= limit) {
          func.apply(context, args)
          lastRan = Date.now()
        }
      }, limit - (Date.now() - lastRan))
    }
  }
}
```

2. Debouncing
- 마지막 함수 호출이나 이벤트만 발생하게 하는 것
ex) 유료 api 요청 시 불필요한 잦은 요청이 발생하면 높은 비용 발생 -> 마지막 요청만 요청되게 하면 비용을 낮출 수 있음

```
debounceBtn.addEventListener('click', debounce(function() {
  console.info('Hey! It is', new Date().toUTCString());
}, 3000));

const debounce = (func, delay) => {
  let inDebounce
  return function() {
    const context = this
    const args = arguments
    clearTimeout(inDebounce)
    inDebounce = setTimeout(() => func.apply(context, args), delay)
  }
}
```

3. 차이점
- 쓰로틀링은 X 밀리 초마다 정기적인 실행을 보장한다는 것이고 디바운싱은 특정 시간안에 한번 이상의 요청은 다 무시된다는 것이다.



출처
[Throttling and Debouncing in JavaScript](https://codeburst.io/throttling-and-debouncing-in-javascript-b01cad5c8edf)
[쓰로틀링과 디바운싱](https://www.zerocho.com/category/JavaScript/post/59a8e9cb15ac0000182794fa)