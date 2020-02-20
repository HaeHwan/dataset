---
title: <i class="fab fa-python"> Jupyter to Blogdown</i>
date: 2020-02-16 19:36:00 +0800
categories: [Python, Jupyter]
tags: [Jupyter, github pages]
toc: true
comments: true
seo:
  date_modified: 2020-02-18 23:36:14 +0900
---

깃헙 블로그에는 다양한 방식으로 글을 올릴 수가 있습니다.  
이번 글에서는 jupyter notebook을 이용한 방법을 소개합니다.  
[링크](https://www.timlrx.com/2018/03/25/uploading-jupyter-notebook-files-to-blogdown/)의 자료를 참고하였습니다.



## ipynb <i class="fas fa-fw fa-angle-right"></i> md
포스팅하길 희망하는 ipynb 파일과 동일한 위치에 있는 ipynb 파일에서 아래와 같이 작성한다.
```python
!jupyter nbconvert --to markdown USERNAME.ipynb
```
위의 코드를 실행하면, 새로운 MD 파일 하나와 폴더가 생성된다.
바꾸고자 했던 ipynb 파일명에 `_files`가 추가된 폴더에는 해당 ipynb안에서 그려지거나 사용되었던 시각자료와 이미지들이 모두 들어가있다.


## upload a markdown file
위에서 생성된 md 파일을 posting 형식에 맞추어 올려준다.
단, 기존에 있던 ipynb 파일의 시각자료들이 보여지지 않는 경우가 많다.
이때에는 생성된 폴더에 이미지들을 함께 올려주면 된다.
