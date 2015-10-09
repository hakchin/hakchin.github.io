---
layout: post
title: 'HUGO Hosting on GitHub Pages'
author: "Hakchin Kim"
comments: true
tags: hugo
categories: blog-engine
---
## Introduction

### 참조 사이트
* [Hosting on GitHub Pages](https://gohugo.io/tutorials/github-pages-blog/ "Hosting on GitHub Pages")
* [spf13/hugoThemes](https://github.com/spf13/hugoThemes/ "hugoThemes")
* 기타 참조 홈페이지
  * [Samuel Debruyn](http://sa.muel.be "hugo 관련 아이디어를 얻을 수 있다")
  * [Sample](https://github.com/SamuelDebruyn/samueldebruyn.github.io "Source Check")

* github subtree
  * [git subtree를 사용하여 재사용할 코드 독립 시키기](http://readme.skplanet.com/?p=8542 "git subtree 사용하기")
  * [Git 도구 - Subtree Merge](https://git-scm.com/book/ko/v1/Git-도구-Subtree-Merge "subtree merge")



## Hakchin's How-To

```
- hugo server --theme=purehugo --buildDrafts --watch
- hugo server --theme=nofancy --buildDrafts
- hugo server --theme=vienna --buildDrafts
- hugo server --theme=material-design --buildDrafts
- hugo server --theme=liquorice --buildDrafts
- hugo server --theme=tachyons --buildDrafts


### To use a theme for a site:
- hugo -t nofancy



eerfmai-2:hakchingithubio sn2ro$ git subtree add --prefix=public https://github.com/hakchin/hakchingithubio.git gh-pages --squash


git subtree add --prefix public git@github.com:hakchin/hakchingithubio.git master --squash

git subtree pull --prefix=public https://github.com/hakchin/hakchingithubio.git gh-pages


git subtree push --prefix=public https://github.com/hakchin/hakchin.github.io.git gh-pages





https://github.com/hakchin/hakchin.github.io.git




============
//이전에 생성된 결과물 제거
rm -rf public

//hakchingithubio 저장소의 public 디렉토리를 subtree로 지정
git subtree add --prefix public git@github.com:hakchin/hakchingithubio.git gh-pages --squash


//커밋한 내용을 내보내기 ??
git subtree pull --prefix=public git@github.com:hakchin/hakchingithubio.git gh-pages

//hugo 실행해서 결과물 생성하기
hugo -t purehugo

// Add everything
git add -A

// Commit and push to master
git commit -m "Updating site" && git push origin master

// Push the public subtree to the gh-pages branch (subtree를 웹Root인 cdpython.github.io에 푸시)
git subtree push --prefix=public git@github.com:hakchin/hakchingithubio.git gh-pages



--------------------
git remote add public git@github.com:hakchin/hakchin.github.io.git

git subtree add --prefix=public git@github.com:hakchin/hakchin.github.io gh-pages
git subtree add --prefix=public git@github.com:hakchin/hakchin.github.io master
--------------------------

git remote add public_repo git@github.com:hakchin/hakchin.github.io.git

git subtree add --prefix=public public_repo gh-pages

git checkout --track public_repo/gh-pages -b public_br

git subtree push --prefix=public public_repo gh-pages

git push public_repo public_br



결국은
hakchingithubio에서,
git subtree push --prefix=public public_repo gh-pages

hakchin.github.io에서,
gh-pages 와 master를 merge

```
