###### * 리액트네이티브의 경우, 더욱 함축적이고 간결해진 최신 자바스크립트 문법(ES6) 사용

### 함수를 더 짧게 사용하기 - 화살표함수


기존

```
  let a = function() {
    console.log("function");
  }
  a();
```


ES6
```
  let a = () => {
    console.log("화살표함수");
  }
  a();
```

### 딕셔너리 키, 값 빠르게 추출하기 - 비구조할당

객체
```
let blog = {
  owner : "noah",
  url : "noah.--.com",
  getPost(){
    console.log("ES6 문법 정리");
```
기존 할당 방식
```
let owner = blog.owner
let getPost = blog.getPost()
```
비구조 할당 방식
```
let { owner, getPost } = blog;
```
함수에서 비구조 할당 방식으로 전달된 딕셔너리 값 꺼내기
```
let blogfunction = ({ owner, url, getPost}) => {
  console.log(owner)
  console.log(url)
  console.log(getPost())
}
blogfunction(blog)
```

### 백틱 (`)
+기호 없이 문자열 합치기

```
let name = "aemin"
let str = `my name is ${name}`;

console.log(str)

출력 결과 : my name is aemin
```

### 딕셔너리를 짧게 작성하기
기존
```
var name = "aemin"
var job = "developer"

ver user = {
  name : name
  job : job
}

console.log(uer);
// {name : "aemin", job : "developer"}
```
ES6
```
var name = "aemin"
var job = "developer"

ver user = {
  name 
  job 
}

console.log(uer);
// {name : "aemin", job : "developer"}

// key : value 형태에서 단순히 변수명만 작성해주면 변수명과 동일한 필드가 생성되며, 그 값이 대입됨
```


