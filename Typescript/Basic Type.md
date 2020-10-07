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
