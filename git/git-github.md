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
