#### Next.js

Next JS 는 React 를 이용하여 Client Side Rendering과 Server Side Rendering을 같이 사용할 수 있게 해주는 프레임워크

> 빌드 시점에 Server Side Rendering으로 생성한 페이지로 First Meaningful Paint를 앞당길 수 있으며, 이후 페이지를 이동할 때마다 Page Rendering에 필요한 JSON_DATA를 가져와 필요한 부분만 다시 그리므로써 Client Side Rendering의 장점 또한 살릴 수 있다.

- 모든 페이지들의 정적인 생성은 /pages/** directory 안에서 일어난다.
- 모든 정적인 파일들은 /public/** directory 에서 제공된다.
- Customizing The 404 Page
  - To create a custom 404 page you can create a pages/404.js file. This file is statically generated at build time.
  
```
  // pages/404.js
  export default function Custom404() {
    return <h1>404 - Page Not Found</h1>
  }
```

