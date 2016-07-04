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

