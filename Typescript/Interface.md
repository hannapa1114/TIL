# use interface

### interface를 설정하는 두가지 방법
1.
```
function printLabel(labeledObj: { label: string }) {
    console.log(labeledObj.label);
}

let myObj = {size: 10, label: "Size 10 Object"};
printLabel(myObj);
```
2.
```
interface LabeledValue {
    label: string;
}

function printLabel(labeledObj: LabeledValue) {
    console.log(labeledObj.label);
}

let myObj = {size: 10, label: "Size 10 Object"};
printLabel(myObj);
```

- Type을 변수로 지정해서 쓰는 느낌

### Optional Prop
```
interface SquareConfig {
    color?: string;
    width?: number;
}
```
- 써도 되고 안써도 된다.

### Readonly Prop
```
interface Point {
    readonly x: number;
    readonly y: number;
}

let p1: Point = { x: 10, y: 20 };
p1.x = 5; // 오류!
```
- 객체 리터럴을 할당하여 Point를 생성하고 할당 후에는 x, y를 수정할 수 없다.

#### readonly vs const ?
> The easiest way to remember whether to use readonly or const is to ask whether you’re using it on a variable or a property. Variables use const whereas properties use readonly.
