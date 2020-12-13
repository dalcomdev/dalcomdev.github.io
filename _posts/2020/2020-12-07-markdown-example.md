---
toc: true
categories:
  - Jekyll
tags:
  - jekyll
---
Markdown 예제가 현재 theme 에서 어떻게 표현되는지 알아보자.  
일부는 원하는 결과가 아니지만 그럭저럭 괜찮은듯 하다.<br /><br /><br />
# 제목(Header)
# 제목 1
## 제목 2
### 제목 3
#### 제목 4
##### 제목 5
###### 제목 6
```markdown
# 제목(Header)
# 제목 1
## 제목 2
### 제목 3
#### 제목 4
##### 제목 5
###### 제목 6
```

# 강조(Emphasis)
이텔릭체는 *별표(asterisks)* 혹은 _언더바(underscore)_를 사용하세요.  
두껍게는 **별표(asterisks)** 혹은 __언더바(underscore)__를 사용하세요.  
**_이텔릭체_와 두껍게**를 같이 사용할 수 있습니다.  
취소선은 ~~물결표시(tilde)~~를 사용하세요.  
<u>밑줄</u>은 `<u></u>`를 사용하세요.
```markdown
이텔릭체는 *별표(asterisks)* 혹은 _언더바(underscore)_를 사용하세요.  
두껍게는 **별표(asterisks)** 혹은 __언더바(underscore)__를 사용하세요.  
**_이텔릭체_와 두껍게**를 같이 사용할 수 있습니다.  
취소선은 ~~물결표시(tilde)~~를 사용하세요.  
<u>밑줄</u>은 `<u></u>`를 사용하세요.
```

# 목록(List)
1. 순서가 필요한 목록
1. 순서가 필요한 목록
- 순서가 필요하지 않은 목록(서브) 
- 순서가 필요하지 않은 목록(서브) 
1. 순서가 필요한 목록
   1. 순서가 필요한 목록(서브)
   1. 순서가 필요한 목록(서브)
1. 순서가 필요한 목록

- 순서가 필요하지 않은 목록에 사용 가능한 기호  
  - 대쉬(hyphen)
  * 별표(asterisks)
  + 더하기(plus sign)
```markdown
1. 순서가 필요한 목록
1. 순서가 필요한 목록
- 순서가 필요하지 않은 목록(서브) 
- 순서가 필요하지 않은 목록(서브) 
1. 순서가 필요한 목록
   1. 순서가 필요한 목록(서브)
   1. 순서가 필요한 목록(서브)
1. 순서가 필요한 목록

- 순서가 필요하지 않은 목록에 사용 가능한 기호  
  - 대쉬(hyphen)
  * 별표(asterisks)
  + 더하기(plus sign)
```

# 링크(Links)
[GOOGLE](https://google.com)  
[NAVER](https://naver.com "링크 설명(title)을 작성하세요.")  
[상대적 참조](../users/login)  

문서 안에서 [참조 링크]를 그대로 사용할 수도 있습니다.  

다음과 같이 문서 내 일반 URL이나 꺾쇠 괄호(`< >`, Angle Brackets)안의 URL은 자동으로 링크를 사용합니다.  
구글 홈페이지: https://google.com  
네이버 홈페이지: <https://naver.com>  

```markdown
[GOOGLE](https://google.com)
[NAVER](https://naver.com "링크 설명(title)을 작성하세요.")

문서 안에서 [참조 링크]를 그대로 사용할 수도 있습니다.

다음과 같이 문서 내 일반 URL이나 꺾쇠 괄호(`< >`, Angle Brackets)안의 URL은 자동으로 링크를 사용합니다.
구글 홈페이지: https://google.com
네이버 홈페이지: <https://naver.com>
```

# 이미지(Images)
![대체 텍스트(alternative text)를 입력하세요!](http://www.gstatic.com/webp/gallery/5.jpg "링크 설명(title)을 작성하세요.")

![Kayak][logo]

[logo]: http://www.gstatic.com/webp/gallery/2.jpg "To go kayaking."

[![Vue](https://kr.vuejs.org/images/logo.png)](https://kr.vuejs.org/)
```markdown
![대체 텍스트(alternative text)를 입력하세요!](http://www.gstatic.com/webp/gallery/5.jpg "링크 설명(title)을 작성하세요.")

![Kayak][logo]

[logo]: http://www.gstatic.com/webp/gallery/2.jpg "To go kayaking."

[![Vue](https://kr.vuejs.org/images/logo.png)](https://kr.vuejs.org/)
```

# 코드(Code) 강조
## 인라인(inline) 코드 강조
`background`혹은 `background-image` 속성으로 요소에 배경 이미지를 삽입할 수 있습니다.

## 블록(block) 코드 강조
```html
<a href="https://www.google.co.kr/" target="_blank">GOOGLE</a>
```

```css
.list > li {
  position: absolute;
  top: 40px;
}
```

```javascript
function func() {
  var a = 'AAA';
  return a;
}
```

```bash
$ vim ./~zshrc
```

```python
s = "Python syntax highlighting"
print s
```

```
No language indicated, so no syntax highlighting. 
But let's throw in a tag.
```
# 표(Table)

| 값          | 의미                     | 기본값      |
|------------|:----------------------:|---------:|
| `static`   | 유형(기준) 없음 / 배치 불가능     | `static` |
| `relative` | 요소 자신을 기준으로 배치         |          |
| `absolute` | 위치 상 부모(조상)요소를 기준으로 배치 |          |
| `fixed`    | 브라우저 창을 기준으로 배치        |          |

<br />
<br />

| 값            | 의미                             | 기본값    |
|--------------|:------------------------------:|-------:|
| ------------ | ------------------------------ | ------ |
| `relative`   | 요소 **자신**을 기준으로 배치             |
| `absolute`   | 위치 상 **_부모_(조상)요소**를 기준으로 배치   |
| `fixed`      | **브라우저 창**을 기준으로 배치            |

# 인용문(BlockQuote)
인용문(blockQuote)

> 남의 말이나 글에서 직접 또는 간접으로 따온 문장.
> _(네이버 국어 사전)_

BREAK!

> 인용문을 작성하세요!
>> 중첩된 인용문(nested blockquote)을 만들 수 있습니다.
>>> 중중첩된 인용문 1
>>> 중중첩된 인용문 2
>>> 중중첩된 인용문 3

# 원시 HTML(Raw HTML)
<u>마크다운에서 지원하지 않는 기능</u>을 사용할 때 유용하며 대부분 잘 동작합니다.

<img width="150" src="http://www.gstatic.com/webp/gallery/4.jpg" alt="Prunus" title="A Wild Cherry (Prunus avium) in flower">

![Prunus](http://www.gstatic.com/webp/gallery/4.jpg)

# 수평선(Horizontal Rule)
---
(Hyphens)

***
(Asterisks)

___
(Underscores)

# 줄바꿈(Line Breaks)
동해물과 백두산이 마르고 닳도록 
하느님이 보우하사 우리나라 만세   <!--띄어쓰기 2번-->
무궁화 삼천리 화려 강산<br>
대한 사람 대한으로 길이 보전하세