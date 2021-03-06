# GIT & GitHub

### local 에서 remote branch list update

로컬에서 브랜치 목록 확인
```bash
$ git branch -a
```
또는,

```bash
$ git branch -r
```

remote branch list를 업데이트
```bash
$ git remote update origin --prune
```

#### 확인 필요한 부분
- git remote 명령은 무엇인가?
- --prune 옵션은 무엇인가?
- sourcetree에서 업데이트하는 방법은 무엇일까?

### Git + LFS(Large File System)

```bash
$ git lfs install
$ git lfs track *.exe
```

lfs를 초기화하고 track 파일을 추가하면 lfs로 관리가 된다.
문제없이 잘 사용하고 있었는데 jenkins에서 빌드 연동을 하려고 테스트해보니
checkout된 파일크기가 너무 작은 문제가 있었다.
lfs로 관리가 안되는 건가하며 이것저것 테스트를 해봤지만,

git checkout 후 lfs를 사용하여 pull을 하니 제대로 파일을 받았다.
```bash
$ git lfs pull
```

lfs로 관리하는 파일은 git checkout 이후에 lfs pull을 해줘야
제대로 파일의 모든 데이터를 받아오는 것 같다.

### git tags 푸쉬

local에서 만든 tag를 remote에 적용하기 위해서는 push를 해야 한다.

```
> git push --tags  # 모든 태그를 푸쉬
```

### 로그 한줄로 보기
```
> git log -10 --pretty=oneline
```

### 다른 branch의 commit 내역을 merge 하기
* merge할 commit 값이 A 일때

```
> git checkout -b merged_branch
> git cherry-pick A
```

### merge와 rebase
* 절대로 이미 푸시했던 커밋을 대상으로는 rebase를 하지 않는다!

* remote와 local에 동시에 존재하는 브랜치를 pull 할때는 rebase를 사용하도록 한다.
```
> git pull --rebase
```
* 기능 브랜치에 대해서는 merge를 사용, rebase와 비슷한 동작을 하게되는 fast-forward merge를 사용하지 않는다.
* 기능 브랜치에 그 부모의 브랜치의 내용을 합칠때는 로컬 브랜치일 때만 rebase로 합침
(출처 : https://elegantcoder.com/git-merge-or-rebase/)

### git ignore
* 끝에 > 를 넣으면 폴더를 무시하라는 것임
```
!lib.a        # lib.a는 무시하지 않음
doc/*.txt     # doc 바로 아래의 txt파일들만 무시
doc/**/*.txt  # doc 아래의 모든 txt 파일 무시
```

#### 궁금한 부분
- jenkins로 처리하는게 아니라 터미널에서 테스트를 해보면 checkout을
하는 것 만으로도 lfs로 관리하는 파일을 전부 다 받는데 jenkins쪽에 뭔가
문제가 있는것은 아닐까?
- jenkins가 설치된 git 버전에 따른 문제이지는 않을까?
