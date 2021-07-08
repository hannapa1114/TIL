### 공식문서 파헤치기

> COMPONENT FORMAT

- 컴포넌트 확장자는 .svelte고 HTML superset을 차용
- script, style, markup(html) section이 있고 optional하게 사용

```
<script>
  // logic
</script>

<style>
  // css
</style>

<!-- markup ( zero or more items) goes here>
```

> script

- script 태그는 컴포넌트 인스턴스가 만들어질 때 실행된다
- 컴포넌트, 프롭스, 라이브러리 import 하는 부분

```
<script>
// Component
import Test from './Test.svelte'

// Library
import { writable } from 'svelte/store'

// props 상위 컴포넌트로 받은 프롭스는 export로 바인딩 해줘야 함
export let format
</script>
```

1. <span style="color:skyblue">export</span> creates a component prop
   변수 선언과 함수 선언 사용 등이 가능

```
<script>
  let foo = 'foo'

  function printFoo() {
      alert(`hello ${foo}!`)
  }

  printFoo()
</script>
```

2. Assignments are 'reactive'
   state 변경과 re-render 시

```
<script>
	let count = 0;

	function handleClick () {
		// calling this function will trigger an
		// update if the markup references `count`
		count = count + 1;
	}
</script>
```

3. <span style="color:skyblue">$:</span> marks a statement as reactive
top-level statement(block이나 function 내부 제외)에서 <span style="color:skyblue">$:</span>(JS label syntax)를 사용해서 반응형으로 만들 수 있다
   컴포넌트가 업데이트 되면 관련있는 statement는 즉시 바뀐다

```
<script>
	let x = 0;
	let y = 0;

	function yPlusAValue(value) {
		return value + y;
	}

	$: total = yPlusAValue(x);
</script>

Total: {total}
<button on:click={() => x++}>
	Increment X
</button>

<button on:click={() => y++}>
	Increment Y
</button>
```

4. Prefix stores with <span style="color:skyblue">$</span> to access their values

   - svelte에 내장되어 있는 store를 통해 props drilling을 하지 않고 컴포넌트 간 변수를 공유할 수 있다

   ```
   <script>
       import { writable } from 'svelte/store';

       const count = writable(0);
       console.log($count); // logs 0

       count.set(1);
       console.log($count); // logs 1

       $count = 2;
       console.log($count); // logs 2
   </script>
   ```

   - Store contract
     svelte/store 없이도 store contract를 구현하여 store를 만들 수 있다
     subscribe/unsubscribe method는 필수, set method는 선택

   ```
   store = { subscribe: (subscription: (value: any) => void) => (() => void), set?: (value: any) => void }
   ```
