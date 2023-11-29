Git 필기.md
## Git
- (버전을 통해, 분산된 방식으로) 코드를 관리하는 도구    
- 코드관리?   
    - 백업도구  
    - 협업도구  
    - 배포도구  
- SCM(Source Code Management) : 코드 관리 도구로써의 Git을 의미  
- VCS(Version Control System) : 버전 관리 시스템(도구)로써의 Git을 의미  
- DVCS(Distributed VCS) : 분산형 버전 관리 시스템(도구)로써의 Git을 의미   

 
         

## Git 명령어  
### [part.1 버전 관리 Git 명령어] 
[1] `git init`: Git 프로젝트를 시작한다는 의미의 명령어  
- Git은 폴더/디렉토리 단위로 코드를 관리한다.  
- So, Git 프로젝트 시작 전에는 해당 프로젝트를 관리할 폴더/디렉토리를 생성해야 한다.  
- 결과 : 프로젝트 폴너 내에 `.git` 폴더 생성   



```
$ git init 
Initialized empt Git respository in C:/Users/skqk3/test/.git/ 
```  
(.git? 점은 숨김파일을 의미! 즉, test파일 안에 숨김파일로 git파일이 만들어진것임 
)  



[2] `git status` : Git 상태 출력  
- 결과 



(최초 상태)
```
On branch master -> master라는 branch에 있음

No commits yet -> commit이 아직 없음

nothing to commit (create/copy files and use "git add" to track) -> commit할 것도 없음
```    

<br/>

(`a.txt` 파일 생성 후 상태)  
```
On branch master

No commits yet

Untracked files: -> 추적되지 않은 파일 있음 
  (use "git add <file>..." to include in what will be committed)
        a.txt
   -> 어떻게 할지 팁을 알려줌(츤데레)
   -> commit 될 것에 포함시키고 시키면 git add <파일명>을 사용해 

nothing added to commit but untracked files present (use "git add" to track)
 -> commit 할 것은 없는데, 추적되지 않은 파일은 있어 (추적하고 싶으면 git add 사용해) 
```   

<br/>

(`git add a.txt` 입력 후 상태)
```
On branch master

No commits yet

Changes to be committed: 
  (use "git rm --cached <file>..." to unstage)  -> 내일 배우는 내용
        new file:   a.txt
```   

<br/>

(`git commit` 실행 후)
```
On branch master
nothing to commit, working tree clean
-> commit 할게 없음, working tree(== working directory, 작업중인 폴더)가 깔끔하다. 
```      


[3] `git add [파일/폴더]` : commmit을 하기 위한 (== 버전을 생성하기 위한 준비단계)  


[4] `git commit -m "메시지"`  
- commit : 버전을 생성하는 역할  
- 보통 처음꺼는 git commit -m "First commit" or "Initial commit"을 사용  



(최초 commit 시)
```
Author identity unknown -> 작자 미상
 
*** Please tell me who you are. -> 너가 누군지 알려줘  

Run -> 실행해봐

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity. -> 너의 계정의 기본 신원을 설정하기 위해
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'skqk3@LAPTOP-4602OEH2.(none)')
```  
  

  [5] `git config` : Git 관련 설정 (최초 한번만 설정하면 됨)  
  ```
    git config --global user.email "you@example.com" 
  git config --global user.name "Your Name"
  ```
    
      
참고) `cat ~/.gitconfig` 명령어 입력하면 내가 설정한 email과 name이 나온다.  



[6] `git log` : Commit 목록을 불러옴  
- commit이 잘됐는지 확인할 때 사용하는 명령어  



### [Part.2 백업 Git 명령어]  
 
[7] `git remote` : 원격 저장소  
- 원격 저장소(Remote Repository)에 대한 정보 
- `git remote add` : 원격 저장소 추가  
- `git remote add [저장소이름] [저장소주소]`  
- `git remote add origin https://github.com/xxx` : 첫번째 저장소는 origin 칭호가 붙음  
     

[8] `git push` : 원격 저장소에 프로젝트 업로드  
- `git push [저장소이름] [브랜치이름]`  
- `git push origin master`
