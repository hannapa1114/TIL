#React hook

### keyword useState, useEffect

- state와 life cycle을 사용할 수 없는 functional component에서 사용이 가능하게끔 만들어주는 라이브러리 혹은 함수


### 사용법
```
import React, {useState, useEffect} from 'react' 

const [state, setState] = useState(initial state)

// state값, state값을 변경해주는 setState를 선언해주고 useState() 안에는 초기값 지정이 가능하다.
// 변수 명은 정하기 나름

useEffect(() => {
  fetch('http://example.com').then(response => {
    setState(response)
})

```

주의해야 할 점은 useEffect는 state가 변하는 것을 감지하고 실행이 되기 때문에 setState는 state의 상태를 변화시키기 때문에 무한루프에 빠질 수 있다.

### Solution
```
//useEffect()의 두번째 인자로 빈배열을 넣어주면 무한루프에 빠지는 것을 막을 수 있다. 
useEffect(() => {
  fetch('http://example.com').then(response => {
    setState(response)
}, [])
```
