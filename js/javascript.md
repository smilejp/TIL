# Javascript ES6

## 알아가고 있는 단계이기 때문에 오류가 존재할 수 있다.

### generator

```
function* range(start, stop) {
  for (var i = start; i < stop; i++)
    yield i;
}
```

* 위와 같이 function* 와 yield를 사용해서 만든다.
* generator는 iterator이기 때문에 iterator를 사용하는 곳에 응용 할 수 있다.
* custom iterator를 쉽게 만들 수 있다.

### template string
* ``(backtick이라 부른다.)으로 문자열을 입력한다.
* ${} 를 사용하여 값을 넣을 수 있다. 값은 모두 string 처리되어 들어간다.

```
`${name} 룰루`
```

### rest parameter, default parameter
* arguments를 사용하여 가변 파라미터를 처리했는데 명시적으로 가변 파라미터를 넘겨줄 수 있다.
* rest parameter는 ...로 시작하고 반드시 마지막에 위치해야 한다.
* default paramter는 파라미터 옆에 = 과 값을 넣어서 명시한다.
```
function Test(A=10, ...C) {
  for(i of C) {
    ...
  }
}
```


### arrow function
* => 함수 내부에서는 this를 정의하지 않는다. 그래서 this는 => 외부의 값이다.
* => 함수에는 arguments 객체가 전달되지 않는다.