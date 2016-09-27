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

### 다른 branch의 commit 내역을 merge 하기
* merge할 commit 값이 A 일때

```
> git checkout -b merged_branch
> git cherry-pick A
```

#### 궁금한 부분
- jenkins로 처리하는게 아니라 터미널에서 테스트를 해보면 checkout을
하는 것 만으로도 lfs로 관리하는 파일을 전부 다 받는데 jenkins쪽에 뭔가
문제가 있는것은 아닐까?
- jenkins가 설치된 git 버전에 따른 문제이지는 않을까?
