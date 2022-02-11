---
title: My Development Environment Settings / 나의 개발 환경 세팅들
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-16 13:12:00 +0900 # for Korea (UTC+9)
categories: [Chatting, About Me]
tags: [settings, customize]
sitemap:
  priority: 0.8
---

이번 블로그에서는 나의 개발 효율을 항상시켜주는 유용한 프로그램, 세팅들을 공유 겸 정리해보려고 한다. 글을 처음 작성하는 시점인 지금은 몇가지 없는데, 앞으로 공유할 만한 게 더 생기면 꾸준히 업데이트할 예정이다.

## AutoHotKey

[AutoHotKey](https://www.autohotkey.com/)는 키보드 단축키를 커스텀할 수 있는 일종의 매크로 프로그램이다. 나는 이 프로그램을 단축키에 방향키를 할당하는 용도로써, 코드를 작성하거나 글을 쓸 때 거의 항상 애용하고 있다.

타자를 많이 치는 사람이라면 방향키를 누르기위해 오른손을 많이 왔다갔다 움직이게 된다. 그리고 작은 움직임이라도 반복하다 보면 근육에 무리가 가기 마련이다. 나는 근육통이 와본 적은 없지만, 코드를 짜는 사람으로서 방향키나 마우스에 손을 가져다 대는 것이 너무 귀찮았다. 그러다가 한 유튜브 영상에서 나온 키보드 세팅을 적용하고 나서부터는 그 전으로 돌아갈 수 없는 몸이 되어버렸다.

내가 사용하고 있는 키보드 단축키는 다음과 같다. 이 단축키들은 `AutoHotKey`를 설치한 후, 아래에 첨부된 `.ahk` 확장자 파일[^ahk]을 실행하면 적용할 수 있다. (<kbd>Win</kbd>+<kbd>R</kbd>에서 `shell:startup`를 입력하면 나오는 창에 이 파일을 넣으면, 컴퓨터가 부팅될 때 자동으로 실행된다.)

|           단축키            |         실행         |
| :-------------------------: | :------------------: |
| <kbd>Alt</kbd>+<kbd>H</kbd> |     <kbd>←</kbd>     |
| <kbd>Alt</kbd>+<kbd>J</kbd> |     <kbd>↓</kbd>     |
| <kbd>Alt</kbd>+<kbd>K</kbd> |     <kbd>↑</kbd>     |
| <kbd>Alt</kbd>+<kbd>L</kbd> |     <kbd>→</kbd>     |
| <kbd>Alt</kbd>+<kbd>U</kbd> |   <kbd>Home</kbd>    |
| <kbd>Alt</kbd>+<kbd>I</kbd> |    <kbd>End</kbd>    |
| <kbd>Alt</kbd>+<kbd>P</kbd> |  <kbd>Page Up</kbd>  |
| <kbd>Alt</kbd>+<kbd>;</kbd> | <kbd>Page Down</kbd> |

처음에는 어색하고 불편하겠지만 하루 이틀이면 익숙해질 정도로 어렵지 않다. 연습을 조금만 한다면 대가로 손 근육의 무리와 귀찮음에서 해방될 수 있다.

물론 부족한 점이 없는 것은 아니다. 단축키를 길게 누르면, Alt키가 잠깐 눌리지 않았다고 인식하는 것인지, 의도치 않게 키보드의 문자가 입력될 때가 있다 (예를 들어 <kbd>Alt</kbd>+<kbd>H</kbd>를 꾹 누르고 있으면 커서가 왼쪽으로 이동하면서 `h`가 듬성듬성 입력된다). 또한 이 프로그램을 실행한 상태로 게임에 들어가면 안 된다. 명색이 메크로 프로그램인지라 게임이 핵으로 인식해 정지를 먹이기도 한다. ~~어떻게 알았는지는 물어보지 말자.~~ 모든 게임이 그런 것은 아니고, 롤이 특히 이런 것에 예민한 것 같긴 하다.

내가 활용하고 있는 기능은 `HotKey` 기능 중 매우 일부분이라서 이외의 어떤 유용한 기능이 있는지 잘 알지 못한다. 나와 다른 방법으로 이 프로그램을 활용하고 있거나, 내가 겪고 있는 문제를 해결하는 방법을 알고 있다면 댓글 또는 이메일로 공유해주기 바란다. (블로그의 댓글 기능은 추후에 추가 예정)

## Chrome Extension

### Dark Reader

[Dark Reader](https://chrome.google.com/webstore/detail/dark-reader/eimadpbcbfnmbkopoojfekhnkhdbieeh)는 웹사이트를 다크모드로 바꿔주는 크롬 익스텐션이다. Medium에서 블로그를 보던 중 왜 Medium에는 다크모드가 없을까 궁금해서 찾아보니 `Dark Reader`를 사용하는 방법이 있었다. 이 익스텐션은 Medium 뿐만 아니라 거의 모든 웹사이트를 다크모드로 바꿀 수 있다. 요즘은 대부분의 사이트에서 다크모드를 지원하지만 아직 모든 사이트가 그런 것은 아니기 때문에 이 익스텐션이 유용할 때가 종종 있다. 나처럼 쨍한 것을 잘 못보는 사람들의 눈 보호를 위해서라도 추천하고 싶은 익스텐션이다.

### Color Hunt

[Color Hunt](https://chrome.google.com/webstore/detail/color-tab/hchlgfaicmddilenlflajnmomalehbom)는 그냥 예뻐서 잘 사용하고 있는 크롬 익스텐션인데, Color Hunt의 색 조합을 기반으로 매번 다른 크롬의 새 탭을 볼 수 있다.

![Color hunt preview1](/assets/posts/20220116/colorhunt1.jpg)
_Image Sorce: color hunt extension store_

|![Color hunt preview2](/assets/posts/20220116/colorhunt2.jpg)|![Color hunt preview3](/assets/posts/20220116/colorhunt3.jpg)|

---

...

Comment

[^ahk]: [AutoHotKey 파일 다운로드](/assets/posts/20220116/AutoHotKeySettings.ahk)
