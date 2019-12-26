---
title: Git
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: 2.Git
    weight: 3
toc: yes
type: docs
---



## 1.Command Line (터미널)


## ls

* 파일보기 

## ls -A

* 숨겨진 파일까지 보기

## ls -al

* 상세 내용

```js
// (1)         (2)(3)   (4)      (5) (6)   (7)   (8)
//drwxr-xr-x   2 root  wheel    64B 11  7 14:14 test/


//1접근 권한 (읽기/쓰기/실행 가능) 여부
//2chmod 명령어
//3링크된 파일 갯수
//4소유자
//5소유그룹
//6파일 크기
//7만든 날짜
//8만든 시간
//9파일/디렉토리 이름


```

## cd 디렉토리 이름 

* 디렉토리로 이동( print working List )

```js
 myuser@mymachine:~$ `cd` Downloads

```

## cd-

* 뒤로가기 

## cd /  

* global 로 가기 (제일 처음 root 디렉토리로 이동 )

## pwd

* 내가 어디있는지 확인

```js
// myuser@mymachine:~/Downloads$ pwd
// showing that .. Users/myuser/Downloads
```


##  touch [file_name]
* 빈 파일 생성

##  mkdir [dir_name]

* 디렉토리 생성

## cat [file_name]

* 텍스트 형태의 파일 확인

##  mv [file_or_dir] [target_dir]

* 파일 및 디렉토리 옮기기


##  mv [file_or_dir] [new_name]

* 파일 및 디렉토리 이름 바꾸기

##  cp [file] [target_dir] or cp -r [folder]

* 복사


##  rm [filename] 

* 파일 삭제
* 휴지통에 들어가지 않음 

##  rm -r [dirname]

* 폴더 삭제
* 휴지통에 들어가지 않음 

##  rm -f [file or dirname];

* `coution` 강제로 지우기 



## ------------------------------------------------------------
## 2.Git(Version Control System)


## git-work-flow

* 페어랑 같이 fork 를 받아서 작업할때 쓰는 명령어 
  
  * 1. 각각 서로 github 에 있는 레포주소를 clone 해서 연결한다. 
  * 2. John이 코드를 작성한다. 그리고 add,commit,push 명령어를 통해 github 에 올린다. 
  * 3. Tim 이 변경된 작성 코드를 가져온다. git pull [명칭] master 명령한다. 그리고 pull 땡겨온 것 을 `꼭` add commit push 를 통해 github 에 올린다. 변경된 push 를 하지 않은체 한다면 다음 commit 이 작동하지 않고 충돌이 난다. 
  
  ![](/tutorial/Git_files/1.png)
  ![](/tutorial/Git_files/2.png)
  ![](/tutorial/Git_files/3.png)
  ![](/tutorial/Git_files/4.png)
  ![](/tutorial/Git_files/5.png)
  ![](/tutorial/Git_files/6.png)
  ![](/tutorial/Git_files/7.png)
  ![](/tutorial/Git_files/8.png)
  
  







## git remote remove [명칭]

* remote 연결된거 지우기 

## git branch -d test

* branch 지우기 

```js

git branch -d test
# Deleted branch test (was ########).


```


## git push origin --delete test

* remote 지우기 

```js

it branch -a
# *master
#  test
#  remote/origin/master
#  remote/origin/test



git push origin --delete test
# To <URL of your repository*.git
#  - [deleted]         test

```



## git branch -a

* 현재 romote 상태 보기 





```js

git branch -a
# *master
#  test
#  remote/origin/master
#  remote/origin/test




```


## git init

* Create an empty Git repository or reinitialize an existing one

## git clone

* Clone a repository into a new directory

## git add .


* Add all file contents to the index


## git add 파일 이름 

* one file add 

```js
git add jung.html

```
## git commit -m ""

* write message into github

## git remote add origin""

* link local to github 

```js
Git remote add origin "https://github.com/J-E-Y/test_2.git"

```

## git push


```js
// git push -u origin master  최종 깇허브에 올리기 
// git push -u origin master  
// git push -f origin master ( 강제로)

```

## git log


* 그동안 commit 한 내용을 볼수 있다.

*enter 키를 치면 밑에 내용을 계속 볼수 있다.

* log 파일을 나오려면 q  버튼을 누르면 된다. 





## git status


* 현재 진행 상태 보기



## git config --global

* 등록하기 

```
git config --global user.email "yourGitHub@email.com"
git config --global user.name "yourGitHubusername"

```






## git branch : 충돌 방지하기



* merge 하는 중 출돌이 존재할수 있다. 

* master branch 와 develop branch와 내용이 다를경우 master branch 에서 통합을 한다. 

* merge 하는 순간 conflict 가 발생 한다.

* git은 병합한 코드가 무엇이 다른지 코드안에 표시가 되게 한다. 
* 그리고 그분은에 들어가서 HAED 부분을 선택할지 develop 부분을 선택할지 직접 수동으로  코드를 삭제해서 결정을 하고 저장한다. 


*  git add . 하고 다시  git merge develop 한다. 

* 그럼 병합이 된것이다. 

* 확인 git merge develop 하면 이미 병합이 되었다 .

* 그럼 log 하면 같은 화면에 master와 develop 가 동시에 나온다. 

* develop 는 필요없기 떄문 git branch -d develop 명령으로 삭제한다. 

* git branch 만 확인하면 master branch 만 남아있다. 

* git push  로 마무리 

## git Branch


![](/tutorial/Git_files/Screen Shot 2019-09-24 at 3.19.15 PM.png)



* Branch : git 은 동시에 여러 개발자들이 프로젝트에서 각기 다른 기능을 개발할 수 있도록 브랜치 (branch) 기능을 제공한다.  

* 일반적으로 EX) 

  * Master Branch 
  * Develop Branch
  * Bug Fix Branch


* 기능들이 수정되면 Master Branch 에 합치기(Merge) 라면 명령어를 사용해서 합치면 된다. 


* Branch 에는 두가지 용어

  * 1. 통합Branch : Master Branch 를 말한다. 
  * 2. 토픽Branch : 특정 기능을 위해 만들어진 Branch 를 말한다. 




* 실습

  * git branch 명령 하면 현재 몇개의 branch 가 있는지 확일할수 있다. 

  * git branch develop 명령 branch 생성 

  * cheakout develop 명령을 현재 default 값이 master 에서 새로만든 develop branch 로 바꿔준다. (git branch 로 확인할수 있다.);


  * 이상태에서 기존 master branchs 에 있는 코드에 수정을 하고 git add 하고 git commit 을 하고 log 명렁을 하면 현재 'HAED -* develop' 바뀐것을 볼수 있다. 

  * 그러면 master branch 에는 적용이 안되있고 새로생성한 branch 에만 해당되어있다.  그러면 develop 에서 작업을 할수 있다. 

  * 이것을 합치기 위해서는 merge 명령을 한다. 

  * git cheakout master 명령을 해서 되돌아 간다. 

  * 그리고 git merge develop 명령을 해서 합친다.

  * 마지막으로 git push 명령을 해서 깃허브에 저장한다. 


  * 필요없는 branch develop 를 삭제는 git branch -d develop 이다. 












## 기존에 commit한 내용으로 되돌아 가기 


* log 명령을 하고 

* git reset --hard 9a9sdsa8fsdfsd6a78f6safs 명령을 한다. 

* 가져온 주소명령으로 돌아가고 그 이후에 있는 commit 내용들을 싹다 지운다.  

* *주의* commit 내용들이 지워질뿐 아니라 모든 로컬에 저장되어있는 파일들도 제거된다. 

* 그리고 나서 push 를 해주는데 push -f 를 명령해야 깃허브 저장소에서도 동일하게 적용된다. 


---
## git :log
---

---
## git :commit -- amend
---

* commit 명령을 잘못 넣으면  이명령어를 통해 수정할수 있다. 


* unix 에디터가 실행된다. 이모드는 수정모두와 관리자 모드로 나뉜다.

* 수정 모드로 들어가고자 한다면 a 를 입력하면 된다. 

* 그리고 내용을 수정하고 ESC 누르고 : 입력하면 wq! 수정되고 밖으로 나오게 된다. 

* git status  하면 수정된 파일을 볼수 있다. 

* git push -f 강제로 명령하면 적용된다. 




## git cheakout--


* add 한다음에 git status 명령을 하면  수정된 파일이 스테이지에 올라가게 된다. 

* cheakout-- 이라는 명령을 하면 add 하기전 코드상태로 되돌아 간다. 







## git reset


* add 한 파일을 다시 되돌리기 







