### Webpack

- 여러가지 파일을 하나의 파일로 만들어 주는 역할

#### webpack, webpack cli
- 웹팩4부터는 webpack-cli를 같이 설치해야 커맨드라인에 webpack이란 명령어를 사용할 수 있다

#### webpack.config.js
- 웹팩으로 번들링 시 설정 파일
- mode : 개발, 배포 모드 설정 가능/ production 모드일 경우 자동으로 최적화 적용
- entry : 번들링 할 파일 설정 보통 최상단 index나 app
- output : 번들링 한 파일 생성 경로 및 생성 파일 이름 지정이 가능
- module : 사용한 loader들의 rule을 정의해주는 부분 ex) typescript -> ts-loader, css -> css-loader 등
- plugin : 부가적인 기능. 효과적인 번들링이 가능해짐 ex) 압축, 핫리로딩, 파일 복사 등
```
const webpack = require('webpack');
module.exports = {
  mode: 'development',
  entry: {
    app: '',
  },
  output: {
    path: '',
    filename: '',
    publicPath: '',
  },
  module: {

  },
  plugins: [],
  optimization: {},
  resolve: {
    modules: ['node_modules'],
    extensions: ['.js', '.json', '.jsx', '.css'],
  },
};
```