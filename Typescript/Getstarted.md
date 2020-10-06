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
> There are already a small set of primitive types available in JavaScript: "boolean", "bigint", "number,
> "string", "symbol", "object", and "undefined", which you can use in an interface. 
> TypeScript extends  this list with a few more, such as 
> any (allow anything), //어느 것이나
> unknown (ensure someone using this type  declares what the type is), // 다른 곳에서 지정한 type이 있다
> never (it’s not possible that this type could happen), // 이건 쓰면 안된다
> and void (a function which returns undefined or has no return value). // undefinde를 return하거나 return value가 없다


