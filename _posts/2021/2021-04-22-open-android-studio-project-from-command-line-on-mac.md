---
published: true
toc: true
categories:
  - Tips
tags:
  - android studio, tips
---

## Android Studio project 열기
mac 을 사용하다 보면, Android Studio project 를 command line 에서 열고 싶을 때가 있다. 그럴때 방법이 없을까 찾아보니 Android Studio 에서 이미 지원하는 기능이었다. 방법은 다음과 같다.  

1. 메뉴에서 Tools > Create Command-line Launcher... 를 선택한 다음  
<img src="https://user-images.githubusercontent.com/9858389/115602174-98eb4f00-a319-11eb-9ccd-587bdb0016bf.png" width="300" />  

2. 나오는 창에서 OK 를 한번 눌러주기만 하면 된다.
<img src="https://user-images.githubusercontent.com/9858389/115603008-99381a00-a31a-11eb-9176-79beb76ca248.png" width="600" />  

3. command line 에서는 다음과 같이 실행하면 된다. studio 가 위에서 생성한 Android Studio 를 여는 명령어이며, 첫번째 argument 가 open 하고자 하는 대상 프로젝트 폴더이다.  

```bash
studio architecture-components-samples/
```  


귀차니즘에 마우스를 쓰지않고 열고 싶을때 사용하면 좋다. 😀
