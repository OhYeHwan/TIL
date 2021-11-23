# JavaScript (with web) 요약 정리

<br>

## 🔥 함수

<hr>

<br>

### 👉🏻 &nbsp; 함수를 인자로 전달하기

```javascript
function hello() {
  console.log("hello");
}

function doSomething(func) {
  console.log(func);
}

/*
    함수를 인자로 전달하기 위해서는 ()를 붙이면 안된다.
    결과 값 : f hello() {
                console.log("hello");
            }
*/
doSomething(hello); // O

/*
    ()를 붙이면 해당함수가 호출된다.
    결과 값 : hello
*/
doSomething(hello()); // X
```

<br>

### 👉🏻 &nbsp; 함수 선언과 실행 순서

- 웹 브라우저가 JS를 해석할때 함수 선언을 가장 먼저하기 때문에 프로그램 흐름에영
  향을 주지 않는다.

<br>

### 👉🏻 &nbsp; var와 Hoisting

- 호이스팅
  - 변수의 선언과 할당을 분리해서 선언부를 scope의 가장 위쪽으로 끌어올린다.
  - 실제 소스코드에서 끌어올리는 것은 아니고 JS interpreter가 JS Source에서 var
    만 기억해둠으로서 선언한 것과 같은 효과를 낸다.
- var
  - 호이스팅뿐만 아니라 재선언과 재할당의 문제도 있다.

<br>

### 👉🏻 &nbsp; 매개변수(parameter)와 인수(argument)

```javascript
/*
    매개변수 : 함수 선언 시 외부에서 값을 받아 줄 변수
*/
function doSomething(매개변수) {}

/*
    인수 : 함수 호출시 함수안에 넣는 실제 값
*/
doSomething(인수);
```

<br>

## 🔥 이벤트

<hr>

<br>

### 👉🏻 &nbsp; 이벤트(event)와 이벤트 처리기(event handler)

- event : 웹 문서 영역 안에서 이루어지는 동작 / 웹 브라우저나 사용자가 행하는 동
  작

  - ex ) 마우스 클릭, 키보드 누르기, 문서 로딩 ...

  <br>

- event handler : 이벤트가 발생할 때 그 이벤트에 반응해서 실행하는 함수
  - 기본형식 : on + 이벤트명
  - ex ) click 이벤트 -> onclick 이벤트 처리기

<br>

## 🔥 Array

<hr>

<br>

### 👉🏻 &nbsp; Array 객체 메서드

흰색 : 원본 배열을 유지하는 메서드 <br> <span style="color: skyblue"> 파란색
</span> : 원본 배열이 변화하는 메서드

|                     종류                      | <center> 설명 </center>                                                                                                                                                                                                                                                                         |
| :-------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                    concat                     | 기존 배열에 요소를 추가해 <span style="color: red"> 새로운 </span> 배열 반환                                                                                                                                                                                                                    |
|                     every                     | 기존 배열에 요소를 추가해 <span style="color: red"> 새로운 </span> 배열을 반환                                                                                                                                                                                                                  |
|                    filter                     | 배열 요소 중 주어진 필터링 함수에 대해 True인 요소만을 골라 <span style="color: red"> 새로운 </span> 배열 반환                                                                                                                                                                                  |
|                    forEach                    | 배열의 모든 요소에 대해 주어진 함수를 실행                                                                                                                                                                                                                                                      |
|                    indexOf                    | 주어진 값과 일치하는 값이 있는 배열 요소의 첫 인덱스 반환                                                                                                                                                                                                                                       |
|                     join                      | 배열 요소를 주어진 구분자로 합쳐 문자열로 반환                                                                                                                                                                                                                                                  |
|  <span style="color: skyblue"> push </span>   | 배열의 맨 끝에 새로운 요소를 추가한 후 새로운 length 반환                                                                                                                                                                                                                                       |
|   <span style="color: skyblue"> pop </span>   | 배열의 마지막 요소를 꺼내 그 값을 반환                                                                                                                                                                                                                                                          |
|  <span style="color: skyblue"> shift </span>  | 배열에서 첫 번째 요소를 꺼내 그 값을 반환                                                                                                                                                                                                                                                       |
| <span style="color: skyblue"> unshift </span> | 배열의 맨 앞에 새로운 요소를 추가                                                                                                                                                                                                                                                               |
| <span style="color: skyblue"> splice </span>  | 배열에 요소를 추가하거나 삭제 <br> _ splice(인덱스) : 인덱스 ~ 배열 끝 까지 삭제 <br> _ splice(인덱스, 개수) : 인덱스 부터 개수 만큼 삭제 <br> \* splice(인덱스, 개수, "추가요소", ...) : 인덱스부터 개수만큼 삭제하고 삭제한 위치에 요소를 추가                                                |
|                     slice                     | 배열에서 특정한 부분을 잘라내서 <span style="color: red"> 새로운 </span> 배열로 반환 <br> \* slice(인덱스) : 인덱스부터 끝까지 <span style="color: red"> 새로운 </span> 배열로 반환 <br> \* slice(인덱스, 숫자) : 인덱스부터 (숫자-1) 까지 <span style="color: red"> 새로운 </span> 배열로 반환 |
| <span style="color: skyblue"> reverse </span> | 배열의 배치 순서를 역순으로 변경                                                                                                                                                                                                                                                                |
|  <span style="color: skyblue"> sort </span>   | 배열 요소를 지정한 조건에 따라 정렬                                                                                                                                                                                                                                                             |
|                   toString                    | 배열에서 지정한 부분을 문자열로 반환                                                                                                                                                                                                                                                            |