# Basic Type

### boolean
```
let isDone: boolean = false;
```

### number
* number => float point number
* bigint => biginteger point number
```
let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
let big: bigint = 100n;
```

### string
* (`)백틱 또한 사용이 가능하다.
```
let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = `Hello, my name is ${fullName}.

I'll be ${age + 1} years old next month.`;
```

### array
* type 뒤에 [] 붙여주는 방법과 Array<type>을 넣어주는 방법 두가지가 있다.
```
let list: number[] = [1, 2, 3];

let list: Array<number> = [1, 2, 3];
```

### tuple
* 요소의 개수와 type을 제한하는 배열을 만들 수 있다.
* pair 값을 가지는 자료형으로 정의된 type의 순서를 지켜야 한다.
* index값으로 접근할 때도 자료형의 맞는 접근이 이루어져야 한다.
```
// Declare a tuple type
let x: [string, number];
// Initialize it
x = ["hello", 10]; // OK
// Initialize it incorrectly
x = [10, "hello"]; // Error
//Type 'number' is not assignable to type 'string'.
//Type 'string' is not assignable to type 'number'.
```

### enum
* 열거형 데이터로 인덱스가 0부터 시작하지만 매뉴얼하게 지정해 줄 수 있다.
```
enum Color {
  Red, // 0
  Green, // 1
  Blue, // 2
}
let c: Color = Color.Green;
```
```
enum Color {
  Red = 1,
  Green = 2,
  Blue = 4,
}
let colorName: string = Color[4];
console.log(colorName);
// colorName display Blue
```

### any
* 알지 못하는 type을 표현해야 할 때
* 3rd party library에서 동적으로 값을 받아올 때
* `Object`로 선언된 변수들은 오직 어떤 값이든 그 변수에 할당할 수 있게 해주지만 실제로 메서드가 존재하더라도, 임의로 호출할 수는 없다.
```
let list: any[] = [1, true, "free"];
//다른 타입이 섞인 배열을 사용할 때 유용하다
list[1] = 100;
```

### void
* void는 어떤 type도 존재할 수 없음을 나타내기 때문에, any의 반대 타입 같다. void는 보통 함수에서 반환 값이 없을 때 반환 type을 표현하기 위해 사용한다.
```
function warnUser(): void {
    console.log("This is my warning message");
}
```

### undefined, null
* 기본적으로 null 과 undefined는 다른 모든 타입의 하위 type. null과 undefined를 number 같은 type에 할당할 수 있다.
* --strictNullChecks를 사용하면, null과 undefined는 오직 any와 각자 자신들 type에만 할당 가능하다. (예외적으로 undefined는 void에 할당 가능합니다)
```
// 이 밖에 이 변수들에 할당할 수 있는 값이 없습니다!
let u: undefined = undefined;
let n: null = null;
```

### never
* never는 함수 표현식이나 화살표 함수 표현식에서 항상 오류를 발생시키거나 절대 반환하지 않는 type으로 쓰임
* never는 모든 type의 하위 type으로 쓰이고 never 하위 type으로는 아무것도 쓸 수 없다.
```
// never를 반환하는 함수는 함수의 마지막에 도달할 수 없다.
function error(message: string): never {
    throw new Error(message);
}

// 반환 타입이 never로 추론된다.
function fail() {
    return error("Something failed");
}

// never를 반환하는 함수는 함수의 마지막에 도달할 수 없다.
function infiniteLoop(): never {
    while (true) {
    }
}
```

### object
* object는 원시 type을 제외한 type들을 나타난다. 
* number, string, boolean, bigint, symbol, null, 또는 undefined 가 아닌 나머지!
```
declare function create(o: object | null): void;

create({ prop: 0 }); // 성공
create(null); // 성공

create(42); // 오류
create("string"); // 오류
create(false); // 오류
create(undefined); // 오류
```

### Type Assertion
* type을 할당하는 두 가지 방법
  1. < type >
  2. ... as type
```
let someValue: any = "this is a string";

let strLength: number = (<string>someValue).length;

```
```
let someValue: any = "this is a string";

let strLength: number = (someValue as string).length;
```

### About Number, String, Boolean, Symbol and Object
* type을 지정할 때 lowercase가 권장된다. do'not use upper case
```
function reverse(s: string): string {
  return s.split("").reverse().join("");
}

reverse("hello world");
```
