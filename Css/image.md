# Img의 모든 것

### image 요소 아래에 패딩된 여분의 공간 제거하기
- img 요소는 inline 즉 텍스트로 취급된다
- 웹에서 텍스트를 display 하는 방식인 typography를 보면 텍스트의 기본 높이인 x-height를 기준으로 상하에 Ascender와 Descender가 존재한다.
- 아래에 패딩 공간은 'Descender' 때문에 발생하는 것!
- 해결책
  - display 속성을 block로 바꿔주면 된다

![typo](https://user-images.githubusercontent.com/49268125/119931366-39d5c580-bfbc-11eb-89b6-a6453bc562bc.png)