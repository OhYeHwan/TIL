# Document Object Model

## ๐๐ป &nbsp; DOM Element ์ ๊ทผํ๊ธฐ

    - Node.querySelector(์ ํ์)
    - Node.querySelectorAll(์ ํ์)

<br>

## ๐๐ป &nbsp; Element ์์ 

    - Element.innerText = ๋ด์ฉ
    - Element.innerHTML = ๋ด์ฉ

<br>

## ๐๐ป &nbsp; Element ์์ฑ ๊ฐ์ ธ์ค๊ธฐ

    - Element.getAttribute("์์ฑ๋ช")

<br>

## ๐๐ป &nbsp; Element ์์ฑ ์์ ํ๊ธฐ

&nbsp;&nbsp; โญ๏ธ &nbsp;&nbsp;์์ฑ ๊ฐ์ด ์ด๋ฏธ ์กด์ฌํ๋ฉด ์๋ก์ด ์์ฑ ๊ฐ์ผ๋ก ์์ , ์
๋ค๋ฉด ์๋ก ์ถ๊ฐ

    - Element.setAttribute("์์ฑ๋ช")

<br>

## ๐๐ป &nbsp; Event handler ์ addEventListenr ์ฐจ์ด

- event handler : ํ ์์์ ํ๋์ ์ด๋ฒคํธ ์ฒ๋ฆฌ๊ธฐ๋ง ์ฐ๊ฒฐ ๊ฐ๋ฅ (๋ฎ์ด์ฐ๊ธฐ)
- addEventListener : ํ ์์์ ์ฌ๋ฌ ์ด๋ฒคํธ ์ฒ๋ฆฌ๊ธฐ ์ฐ๊ฒฐํ์ฌ ์คํ ๊ฐ๋ฅ (๋์ )

```javascript
let btn = document.querySelector(".btn");

/*
    ๋ฒํผ ํด๋ฆญ ์ onclick ์ด๋ฒคํธ ํธ๋ค๋ฌ ๊ฒฐ๊ณผ ๊ฐ : 300
    โญ๏ธ ๊ฒฐ๊ณผ๊ฐ ํ๋ฒ๋ง ์ถ๋ ฅ๋๋ค. -> ์ด์  ์ด๋ฒคํธ์ฒ๋ฆฌ๊ฐ ๋ฎ์ด์์ด์ง๋ค.(๋ฎ์ด์ฐ๊ธฐ)
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
    ๋ฒํผ ํด๋ฆญ ์ addEventListener ๊ฒฐ๊ณผ ๊ฐ :  100, 200, 300
    โญ๏ธ ๊ฒฐ๊ณผ๊ฐ 3๋ฒ ์ถ๋ ฅ -> ์ด๋ฒคํธ๊ฐ ๋์ ๋๋ค!(๋์ )
    โญ๏ธ ํจ์์์ on์ ๋ถ์ด์ง ์๊ณ  ์ด๋ฒคํธ ์์ฒด๋ฅผ ์๋ ฅ!
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

// addEventListener : ์บก์ฒ๋ง๊ณผ ๋ฒ๋ธ๋ง ๋ฐฉ์ง!
```

<br>

## ๐๐ป &nbsp; ์ด๋ฒคํธ ์บก์ฒ๋ง๊ณผ ์ด๋ฒคํธ ๋ฒ๋ธ๋ง

- ์ด๋ฒคํธ ์บก์ฒ๋ง : DOM์ ๋ถ๋ชจ ๋ธ๋์์ ์์ ๋ธ๋๋ก ์ ๋ฌ ๋๋ ๊ฒ
- ์ด๋ฒคํธ ๋ฒ๋ธ๋ง : DOM์ ์์ ๋ธ๋์์ ๋ถ๋ชจ ๋ธ๋๋ก ์ ๋ฌ ๋๋ ๊ฒ

<br>

## ๐๐ป &nbsp; DOM์์ ๋ธ๋ ์ถ๊ฐ-์ญ์ ํ๊ธฐ

- ์์ ๋ธ๋ ๋ง๋ค๊ธฐ
  - โญ๏ธ &nbsp; document.createElement(ํ๊ทธ);
- ์์ฑ ๋ธ๋ ๋ง๋ค๊ธฐ
  - โญ๏ธ &nbsp; document.createAttribute(์์ฑ๋ช);
- ํ์คํธ ๋ธ๋ ๋ง๋ค๊ธฐ
  - document.createTextNode(ํ์คํธ);
- ์์ ๋ธ๋ ์ฐ๊ฒฐํ๊ธฐ
  - ๋ถ๋ชจ๋ธ๋.appendChild(์์๋ธ๋);
- ๋ธ๋ ์ญ์  ํ๊ธฐ
  1. ๋ถ๋ชจ๋ธ๋ ์ฐพ๊ธฐ : ๋ธ๋.parentNode
  2. ๋ถ๋ชจ๋ธ๋์์ ํด๋น๋ธ๋ ์ญ์  : โญ๏ธ &nbsp; ๋ถ๋ชจ๋ธ๋.removeChild(์์๋ธ๋);
