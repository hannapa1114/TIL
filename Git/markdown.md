# Let's talk about Markdown

### Table of Contents
* Headers
* Emphasis
* Lists
* Links
* Images
* Code and Syntax Highlighting
* Tables
* Blockquotes
* Inline HTML
* Horizontal Rule
* Line Breaks
* YouTube Videos

#### Headers
```
# H1
## H2
### H3
#### H4
##### H5
###### H6 

#과 text 사이에 공백이 필요하다

underline style

Alt-H1
======   6개!

Alt-H2
------
```

#### Emphasis
```
italics(기울임) *asterisks* or _underscores_.

bold(진하게) **asterisks** or __underscores__.

Combined italics&bold **asterisks and _underscores_**.

Scratch(줄긋기) ~~Scratch this.~~  

```

#### List
```
숫자의 관계없이 숫자 순서대로 표시된다.
1. First ordered list item
2. Another item
⋅⋅* Unordered sub-list. 
1. Actual numbers don't matter, just that it's a number(1)
⋅⋅1. Ordered sub-list(2)
4. And another item.(3)
   들여쓰기 할 때
⋅⋅⋅You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).

⋅⋅⋅To have a line break without a paragraph, you will need to use two trailing spaces.⋅⋅
⋅⋅⋅Note that this line is separate, but within the same paragraph.⋅⋅
⋅⋅⋅(This is contrary to the typical GFM line break behaviour, where trailing spaces are not required.)
  
* Unordered list can use asterisks
- Or minuses
+ Or pluses
```

#### Link
```

[Linkname](url)

```

#### Images
```
Inline-style: 
![alt text](https://example.com/image "Alt Text 1")

Reference-style: 
![alt text][image]

[image]: https://example.com/image "Alt Text 2"

Local Image Upload
Issue 게시판에 new issue로 새 글 쓰기를 하고, write 영역에 image를 drag&drop 한다
생성되는 경로를 복사해서 이미지를 올릴 곳에 붙여넣기를 한다!
```

#### Code and Syntax Highlighting
```
Inline `code` has `back-ticks around` it.

 '```'javascript
 var s = "JavaScript syntax highlighting";
 alert(s);
 '```'

```

#### Tables
```
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

테이블 헤드 표시는 적어도 3개이상의 -가 필요하다.
: 으로 가운데정렬 오른쪽 정렬을 시켜줄 수 있다

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

테이블 안에 인라인 마크다운 적용이 가능하다.
기울임 하이라이트 진하게
```

#### Blockquotes
```

> 이것은 인용문입니다.

```

#### innerHTML
```
<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>
raw HTML이 마크다운 문법안에서 사용이 가능하다. Html 태그 안에서 마크다운 문법은 적용이 되지 않는다.
```

#### Horizontal Rule
```
수평선 긋기
최소 3개이상 쓰면 그어진다~

---

Hyphens

***

Asterisks

___

Underscores


```

#### Line Breaks
```
줄과 줄 사이에 Enter 넣기

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.

```
This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.

#### Youtube
```
<a href="http://www.youtube.com/watch?feature=player_embedded&v=YOUTUBE_VIDEO_ID_HERE
" target="_blank"><img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>
```
### Reference
* [Markdown Cheetsheet in Github](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#code)
