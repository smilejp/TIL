# Python (2.7기반)

### 리스트안에 for문 포함

* [ 표현식 for 항목 in 반복가능 객체 if 조건 ] 형식으로 리스트안에 for문을 포함하여 반복을 처리할 수 있다.

* [ 표현식 for 항목1 in 반복가능객체1 if 조건1 for 항목2 in 반복가능객체2 if 조건2 ] 와 같이 조건을 여러개 넣을 수 도 있다.

예를 들면

```
 >> [ x for x in range(3)]
 -> [0, 1, 2]

 >> a = [1, 2, 3, 4]
 >> [x for x in a if x % 2 == 0]
 -> [2, 4]
```

### format string
* "{}".foramt 이용
```
>> "Test {} Format".format(10)
'Test 10 Format'
```

### 배열 초기화
>> a = [0] * 10
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

