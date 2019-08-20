---
title: Git
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: Git
    weight: 6
toc: true
type: docs
---

---
## Git : **pwd**
---

> print working Directory 

---
## Git : **ls** 
---

> print working List 

---
## Git :**cd**
---

> go back to beginning

---
## Git :**cd -**
---

> previous directory (or back)

---
## Git :**init**
---

> Create an empty Git repository or reinitialize an existing one


---
## Git :**clone**
---

> Clone a repository into a new directory

---
## Git :**add .**
---

> Add all file contents to the index

---
## Git : **add**
---

> one file add 

```
git add jung.html
```

---
## Git :**rm**
---

> Remove files

---
## Git :**rm -f**
---

> Remove files and directory

---
## Git :**mkdir**
---
>create directory 

* ex
```
git mkdir jung

```

---
## Git :**touch**
---

> create file 

* ex
```
git touch jung.txt 
```

---
## Git :**commit -m ""**
---

> write message into github

---
## Git :**remote add origin""**
---

> link local to github 

```
Git remote add origin "https://github.com/J-E-Y/test_2.git"

```

---
## Git : **Push**
---

```
git push -u origin master  최종 깇허브에 올리기 
git push -u origin master  
git push -f origin master ( 강제로)

```


---
## Git : **log**
---


```
git log  기록 업데이트한 기록 확인

```

---
## Git : **status**
---

```
git 현재 진행 상태 보기
```

---
## Git : **Add your github email and username to git**
---


```
git config --global user.email "yourGitHub@email.com"
git config --global user.name "yourGitHubusername"

```


---
## Git : **branch**  
---

```

`기능 변경을 하고 싶을 때 생성 및 사용`


기능 변경하기
이미 돌아가고 있는 프로그램에서 기능을 바꾸고 싶은 일이 생길 수 있습니다. 그럴 때 어떻게 해야 하나요? 보통 초보 개발자들은 주석을 활용합니다. 돌아가고 있는 부분을 삭제하면 아까우니까 주석 처리하고 개발합니다. 시간이 지나면 코드가 엉망진창으로 짜장짬뽕 믹싱이 되는데 이런 코드를 스파게티 코드라고 하죠. 이런 상황을 막기 위해서 브랜치를 사용할 수 있습니다.


```
---
## Git : **merge**  
---

```
한 브랜치의 내용을 다른 브랜치에 반영 (통합)

```


---
## Git : **checkout**  
---

```
저장소에서 특정 커밋이나 브랜치로 돌아가고 싶을 때 사용
```

---
## Git : **diff**  
---

```

```




