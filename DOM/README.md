# Document Object Model

## 👉🏻 &nbsp; DOM Element 접근하기

    - Node.querySelector(선택자)
    - Node.querySelectorAll(선택자)

<br>

## 👉🏻 &nbsp; Element 수정

    - Element.innerText = 내용
    - Element.innerHTML = 내용

<br>

## 👉🏻 &nbsp; Element 속성 가져오기

    - Element.getAttribute("속성명")

<br>

## 👉🏻 &nbsp; Element 속성 수정하기

&nbsp;&nbsp; ⭐️ &nbsp;&nbsp;속성 값이 이미 존재하면 새로운 속성 값으로 수정, 없
다면 새로 추가

    - Element.setAttribute("속성명")

<br>

## 👉🏻 &nbsp; Event handler 와 addEventListenr 차이

- event handler : 한 요소에 하나의 이벤트 처리기만 연결 가능 (덮어쓰기)
- addEventListener : 한 요소에 여러 이벤트 처리기 연결하여 실행 가능 (누적)

```javascript
let btn = document.querySelector(".btn");

/*
    버튼 클릭 시 onclick 이벤트 핸들러 결과 값 : 300
    ⭐️ 결과가 한번만 출력된다. -> 이전 이벤트처리가 덮어씌어진다.(덮어쓰기)
*/
btn.onclick = function () {
  console.log("100");
};

btn.onclick = function () {
  console.log("200");
};

btn.onclick = function () {
  console.log("300");
};

/*
    버튼 클릭 시 addEventListener 결과 값 :  100, 200, 300
    ⭐️ 결과가 3번 출력 -> 이벤트가 누적된다!(누적)
    ⭐️ 함수안에 on을 붙이지 않고 이벤트 자체를 입력!
*/
btn.addEventListener("click", function () {
  console.log("100");
});

btn.addEventListener("click", function () {
  console.log("200");
});

btn.addEventListener("click", function () {
  console.log("300");
});

// addEventListener : 캡처링과 버블링 방지!
```

<br>

## 👉🏻 &nbsp; 이벤트 캡처링과 이벤트 버블링

- 이벤트 캡처링 : DOM의 부모 노드에서 자식 노드로 전달 되는 것
- 이벤트 버블링 : DOM의 자식 노드에서 부모 노드로 전달 되는 것

<br>

## 👉🏻 &nbsp; DOM에서 노드 추가-삭제하기

- 요소 노드 만들기
  - ⭐️ &nbsp; document.createElement(태그);
- 속성 노드 만들기
  - ⭐️ &nbsp; document.createAttribute(속성명);
- 텍스트 노드 만들기
  - document.createTextNode(텍스트);
- 자식 노드 연결하기
  - 부모노드.appendChild(자식노드);
- 노드 삭제 하기
  1. 부모노드 찾기 : 노드.parentNode
  2. 부모노드에서 해당노드 삭제 : ⭐️ &nbsp; 부모노드.removeChild(자식노드);
