### Settings

#### eslint issue

nestjs 기본 모듈 import 오류가 날 때는 tsconfig.json 파일 경로를 못 찾아서 발생하는 경우가 있다.
**tsconfigRootDir: \_\_dirname,** 옵션을 추가해준다.

```
//.eslintrc.js
parserOptions: {
    project: 'tsconfig.json',
    tsconfigRootDir: __dirname,
    sourceType: 'module',
  },
```
