---
title: Github Actions Error - Process completed with exit code 1. 해결
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-09 20:30:00 +0900 # for Korea (UTC+9)
categories: [Development, Github]
tags: [minimal mistakes, github actions]
sitemap:
  priority: 0.8
---

![Desktop View](/assets/posts/20220109/example2-1.png){: width="500" height="500" }
_삽질의 흔적들..._

## Minimal Mistake

![Desktop View](/assets/posts/20220109/example2-2.png){: width="972" height="589" }
_Error: Process completed with exit code 1_

깃허브는 내가 [앞 포스트](https://cometj03.github.io/posts/github-actions-solved/)를 올리자마자 새로운 오류를 선사해주었다. 그 내용은 바로.. `Error: Process completed with exit code 1`

## Solution

삽질을 좀 하긴 했지만 결론은 **"글 제목에 따옴표 넣지 마라"**이다.

```diff
---
- title: Github Actions Error - "The process failed with exit code 16" 해결
+ title: Github Actions Error - The process failed with exit code 16 해결
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
...
---
```

> 물론 나와 원인이 다를 수도 있겠지만, 제목 등 글 설정 부분에 잘못 입력한 건 없는지 확인하는 게 좋을 것 같다.

`title: ` 뒤에 나오는 코드를 자동으로 문자열로 인식해서 중간에 따옴표를 넣으면 안 되는 것 같다. 저것도 나름의 문법이 있을 텐데 무슨 언어인지도 모르겠다..
