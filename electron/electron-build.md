## Electron 빌드 관련

### LNK 1318 오류

- Windows 7 / 32bit
- Python 2.7
- NodeJS 6.1.0
- Visual Studio 2015 Community Edition
- Electron v1.2.5


빌드를 하다보면 LNK 1318 에러가 발생한다.

다른 원인들이 있겠지만, 인터넷으로 검색을 해보니 Electron을 Release 빌드를 하려하면 최소 8GB 정도의 메모리가 필요하다고 한다.

32bit Window에서는 4GB 메모리가 한계이니 64bit 윈도우에서 빌드를 실행하면 된다.

#### 추가로 할일
- 출처를 남겨야 한다.


### ia32 버전 빌드

- Windows 7 / 64bit
- Electron v1.2.5
- NodeJS 6.1.0

nodejs를 x64버전으로 설치후 빌드시 x64 target 옵션을 넣지 않아도 x64용으로 빌드가 됨.
```sh
$ python script\bootstrap.py -v --target_arch=x64
```

32bit windows에서 실행하기 위해서 ia32 옵션을 넣어 빌드했지만 32bit windows에서
실행은 되지만 동작이 이상함.

```
$ python script\bootstrap.py -v --target_arch=ia32
```

nodejs를 32bit용으로 설치하고 빌드를 구성하니 32bit windows에서 정상동작함

#### 추가로 궁금한것
- 왜 기본 옵션을 x64로 넣지 않았는데 x64용으로 빌드가 된것일까?
