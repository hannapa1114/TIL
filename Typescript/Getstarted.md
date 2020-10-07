# Typescript

TypeScript stands in an unusual relationship to JavaScript.

The main benefit of TypeScript is that it can *highlight unexpected behavior* in your code, *lowering the chance of bugs.*

1. 변수의 Type을 알려준다.
```
let helloWorld = "Hello World";
//  ^ = let helloWorld: string
```
2. Interface를 사용하여 객체의 Type을 명시할 수 있다.
```
interface User {
  name: string;
  id: number;
}
```
------
```
const user: User = {
  name: "Hayes",
  id: 0,
};
```

3. class에도 Interface 적용이 가능하다.
```
interface User {
  name: string;
  id: number;
}

class UserAccount {
  name: string;
  id: number;

  constructor(name: string, id: number) {
    this.name = name;
    this.id = id;
  }
}

const user: User = new UserAccount("Murphy", 1);
```


4.
There are already a small set of primitive types available in JavaScript: `"boolean", "bigint", "number, "string", "symbol", "object", and "undefined"`, which you can use in an interface. TypeScript extends  this list with a few more, such as `any` (allow anything), `unknown` (ensure someone using this type  declares what the type is), `never` (it’s not possible that this type could happen),and `void` (a function which returns undefined or has no return value).

5. Composing Types
* Union
여러가지 변수를 정의할 수 있게 해준다.
```
type MyBool = true | false;
type WindowStates = "open" | "closed" | "minimized";
type LockStates = "locked" | "unlocked";
type OddNumbersUnderTen = 1 | 3 | 5 | 7 | 9;
```

* Generic
추후에 사용시에 type을 지정하여 쓸 수 있다.
```
interface Backpack<Type> {
  add: (obj: Type) => void;
  get: () => Type;
}

// This line is a shortcut to tell TypeScript there is a
// constant called `backpack`, and to not worry about where it came from.
declare const backpack: Backpack<string>;

// object is a string, because we declared it above as the variable part of Backpack.
const object = backpack.get();

// Since the backpack variable is a string, you can't pass a number to the add function.
backpack.add(23);
Argument of type 'number' is not assignable to parameter of type 'string'.
```

6. Structual Type System
One of TypeScript’s core principles is that type checking focuses on the shape that values have. This is sometimes called “duck typing” or “structural typing”.
모양이 비슷한 type에 대해 같은 규칙을 적용해서 check 하는 기능

```
interface Point {
  x: number;
  y: number;
}

function printPoint(p: Point) {
  console.log(`${p.x}, ${p.y}`);
}

// prints "12, 26"
const point = { x: 12, y: 26 };
printPoint(point);
```
point는 type 정의가 되지 않았지만 Point와 형태가 똑같기 때문에 error가 발생하지 않는다.
