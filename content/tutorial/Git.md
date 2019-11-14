---
title: Gi2
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: Gi2
    weight: 0
toc: true
type: docs
---



__
## new Learning
__


---
## branch 충돌 방지하기 
---


> merge 하는 중 출돌이 존재할수 있다. 

> master branch 와 develop branch와 내용이 다를경우 master branch 에서 통합을 한다. 

> merge 하는 순간 conflict 가 발생 한다.

> git은 병합한 코드가 무엇이 다른지 코드안에 표시가 되게 한다. 
> 그리고 그분은에 들어가서 HAED 부분을 선택할지 develop 부분을 선택할지 직접 수동으로  코드를 삭제해서 결정을 하고 저장한다. 


>  git add . 하고 다시  git merge develop 한다. 

> 그럼 병합이 된것이다. 

> 확인 git merge develop 하면 이미 병합이 되었다 .

> 그럼 log 하면 같은 화면에 master와 develop 가 동시에 나온다. 

> develop 는 필요없기 떄문 git branch -d develop 명령으로 삭제한다. 

> git branch 만 확인하면 master branch 만 남아있다. 

> git push  로 마무리 

---
## git : Branch
---


![](/tutorial/Git_files/Screen Shot 2019-09-24 at 3.19.15 PM.png)



> Branch : git 은 동시에 여러 개발자들이 프로젝트에서 각기 다른 기능을 개발할 수 있도록 브랜치 (branch) 기능을 제공한다.  

* 일반적으로 EX) 

> Master Branch 
> Develop Branch
> Bug Fix Branch


> 기능들이 수정되면 Master Branch 에 합치기(Merge) 라면 명령어를 사용해서 합치면 된다. 


> Branch 에는 두가지 용어

> 1. 통합Branch : Master Branch 를 말한다. 
> 2. 토픽Branch : 특정 기능을 위해 만들어진 Branch 를 말한다. 




* 실습

> git branch 명령 하면 현재 몇개의 branch 가 있는지 확일할수 있다. 

> git branch develop 명령 branch 생성 

> cheakout develop 명령을 현재 default 값이 master 에서 새로만든 develop branch 로 바꿔준다. (git branch 로 확인할수 있다.);


> 이상태에서 기존 master branchs 에 있는 코드에 수정을 하고 git add 하고 git commit 을 하고 log 명렁을 하면 현재 'HAED -> develop' 바뀐것을 볼수 있다. 

> 그러면 master branch 에는 적용이 안되있고 새로생성한 branch 에만 해당되어있다.  그러면 develop 에서 작업을 할수 있다. 

> 이것을 합치기 위해서는 merge 명령을 한다. 

> git cheakout master 명령을 해서 되돌아 간다. 

> 그리고 git merge develop 명령을 해서 합친다.

> 마지막으로 git push 명령을 해서 깃허브에 저장한다. 


> 필요없는 branch develop 를 삭제는 git branch -d develop 이다. 















---
## git : **기존에 commit한 내용으로 되돌아 가기 **
---

> log 명령을 하고 

> git reset --hard 9a9sdsa8fsdfsd6a78f6safs 명령을 한다. 

> 가져온 주소명령으로 돌아가고 그 이후에 있는 commit 내용들을 싹다 지운다.  

> *주의* commit 내용들이 지워질뿐 아니라 모든 로컬에 저장되어있는 파일들도 제거된다. 

> 그리고 나서 push 를 해주는데 push -f 를 명령해야 깃허브 저장소에서도 동일하게 적용된다. 


---
## git :**log**
---

> 그동안 commit 한 내용을 볼수 있다.

>enter 키를 치면 밑에 내용을 계속 볼수 있다.
> log 파일을 나오려면 q  버튼을 누르면 된다. 


---
## git :**commit -- amend**
---

> commit 명령을 잘못 넣으면  이명령어를 통해 수정할수 있다. 


> unix 에디터가 실행된다. 이모드는 수정모두와 관리자 모드로 나뉜다.

> 수정 모드로 들어가고자 한다면 a 를 입력하면 된다. 

> 그리고 내용을 수정하고 ESC 누르고 : 입력하면 wq! 수정되고 밖으로 나오게 된다. 

> git status  하면 수정된 파일을 볼수 있다. 

> git push -f 강제로 명령하면 적용된다. 





---
## git :**cheakout--**
---

> add 한다음에 git status 명령을 하면  수정된 파일이 스테이지에 올라가게 된다. 

> cheakout-- 이라는 명령을 하면 add 하기전 코드상태로 되돌아 간다. 






---
## git :**reset**
---

> add 한 파일을 다시 되돌리기 


__
## new Learning 
__



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




