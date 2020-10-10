# react with typescript

1. install typescript & yarn
```
$ npm install -g yarn
$ npm install -g typescript

$ tsc -v
//Verison 4.0.3
```

2. transfiling
* tsc 명령어는 .ts => .js 바꿔준다.
> 컴파일은 일반적으로 소스 코드를 바이트 코드로 변환하는 작업을 의미한다. TypeScript 컴파일러는 TypeScript 파일을 자바스크립트 파일로 변환하므로 컴파일보다는 트랜스파일링(Transpiling)이 보다 적절한 표현이다.
```
$ tsc --init
//옵션 설정 파일 tsconfig.json 생성
```
[tsc CLI options](https://www.typescriptlang.org/docs/handbook/compiler-options.html)


3. typescript templete으로 react project를 생성할 수 있다.
```
npx create-react-app <app name> --templete typescript

or

npx create-react-app <app name> --typescript

```

4. install module
* 기본적인 typescript module이 설치되지만 추가적인 module 설치를 하려면 js와 ts module 설치를 같이 해줘야 한다.
* typescript module은 '@types/'가 앞에 붙는다.
```
yarn add styled-components @types/styled-components
```
