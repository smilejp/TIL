# TIL(Today I Learned)

### gollum 설치(Mac)
```bash
$ sudo gem install gollum
```

### mac에서 gollum 설치 에러 발생시
- [gollum install 문서](https://github.com/gollum/gollum/wiki/Installation) 참고
- mini_portile2 에러 발생시 [이슈 처리](https://github.com/sparklemotion/nokogiri/issues/1483#issuecomment-224684394) 참고


### gollum 설치(Windows)
- jRuby를 설치한다.
```bash
> gem install gollum
```

### windows에서 gollum 에러
- NoMethodError 에러 발생
jRuby 설치 폴더\lib\ruby\gems\shared\gems\rjgit-4.3.1.0\lib\rjgit_helpers.rb 파일의
```ruby
jblob_lookup = walk.lookup_blob(treewalk.objectId(0))
```
이 부분을 아래와 같이 변경하면 된다. [출처](https://github.com/gollum/gollum/issues/1120)
```ruby
jblob_lookup = walk.lookup_blob(treewalk.getObjectId(0))
```
