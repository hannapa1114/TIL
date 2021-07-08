### svelte/store

svelte/store module은 _readable_, _writable_ and _derived_ function을 지원한다

상태관리는 상태변경에 즉각 변경되는 $store syntax와 같이 모든 객체에는 subscribe, unsubscribe and set method 구현이 가능하다

state를 store라고 부르고 store들의 집합을 stores라고 지칭

#### writable

```
state = writable(value?: any)
```

value에 state의 초기값을 넣어줌

```
store = writable(value?: any, start?: (set: (value: any) => void) => () => void)
```

두번째 argument로 함수를 받는데, 구독자가 0에서 1로 늘 때 호출된다

```
import { writable } from 'svelte/store';

const count = writable(0);

count.subscribe(value => {
	console.log(value);
}); // logs '0'

count.set(1); // logs '1'

count.update(n => n + 1); // logs '2'
```

- set method은 한가지 argument의 value를 set하는 method
- update method는 callback 함수를 argument로 받아 새로운 값을 return

writable 값은 페이지가 refresh 되면 사라짐(localStorage 같은 곳에 저장하는 logic 필요)

#### readable

```
store = readable(value?: any, start?: (set: (value: any) => void) => () => void)
```

형태는 writable과 같고 문자그대로 읽기전용

```
import { readable } from 'svelte/store';

const time = readable(null, set => {
	set(new Date());

	const interval = setInterval(() => {
		set(new Date());
	}, 1000);

	return () => clearInterval(interval);
});
```

#### derived

stores에서 하나 이상의 store를 분리하는 것

```
store = derived(a, callback: (a: any) => any)
```

```
store = derived(a, callback: (a: any, set: (value: any) => void) => void | () => void, initial_value: any)
```

```
store = derived([a, ...b], callback: ([a: any, ...b: any[]]) => any)
```

```
store = derived([a, ...b], callback: ([a: any, ...b: any[]], set: (value: any) => void) => void | () => void, initial_value: any)
```

두번째 argument에 set을 사용할 경우 third argument에 derived한 store의 초기값을 넣어줘야 한다

```
import { derived } from 'svelte/store';

const delayed = derived(a, ($a, set) => {
	setTimeout(() => set($a), 1000);
}, 'one moment...');
```

배열은 첫번째 argument로 pass됨 (단일 저장소 X)

```
import { derived } from 'svelte/store';

const summed = derived([a, b], ([$a, $b]) => $a + $b);

const delayed = derived([a, b], ([$a, $b], set) => {
	setTimeout(() => set($a + $b), 1000);
});
```

#### get

빈번하게 변하는 value 값을 subscribe하는 방법

```
import { get } from 'svelte/store';

const value = get(store);
```
