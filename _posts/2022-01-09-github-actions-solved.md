---
title: Github Actions Error - The process failed with exit code 16. 해결
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-09 19:26:00 +0900 # for Korea (UTC+9)
categories: [Development, Github]
tags: [minimal mistakes, github actions]
sitemap:
  priority: 0.8
---

## Intro

개발을 하면서 맞닥뜨리는 오류 중 가장 당황스러운 것은 처음보는 오류가 아니라, 예전에 기나긴 삽질을 거쳐 겨우 해결한 오류라는 것을 아마 많은 개발자들이 공감할 것 같다. 왜냐하면 해결하는 데에 많은 시간과 노력이 들어갔다는 사실만 떠오르고 어떻게 해결했는지는 기억이 안 나기 때문이다.. 그런 의미에서 나는 앞으로 [`minimal mistakes`](https://cometj03.github.io/tags/minimal-mistakes/) 태그에 내가 겪었던 실수나 오류들, 그리고 해결과정을 차곡차곡 기록해두려고 한다.

## Minimal Mistake

`minimal mistakes`의 첫 포스팅 주제는 Jekyll 블로그를 Github Page로 배포하다가 겪은 일이다.

![Desktop View](/assets/posts/20220109/example1-1.png){: width="400" height="400" }
_깃허브에게서 받은 이메일_

깃허브 블로그 설정을 이것저것 하다가 레포에 푸시했는데 빌드에 실패했다며 이런 이메일을 받았다. 나는 같은 현상을 [메인 저장소](https://github.com/cotes2020/jekyll-theme-chirpy)와 병합(버전 업데이트)할 때도 겪었다.

![Desktop View](/assets/posts/20220109/example1-2.png){: width="972" height="589" }
_확대 하려면 클릭_

들어가보면 이런 화면이 뜨는데, `Error: The process '~~' failed with exit code 16`라는 에러 문구를 볼 수 있다.

## Solution

나의 경우엔 `Gemfile.lock`에 입력된 버전이 맞지 않아서 생긴 문제 같다.

그냥 콘솔에 둘 중 하나를 실행한 후 커밋해서 올리면 문제는 간단하게 해결됐다.

```console
$ bundle
$ bundle install
```
