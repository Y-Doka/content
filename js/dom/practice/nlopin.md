---
permalink: false
---

🛠 Напрямую с DOM работают редко. Обычно работают на [уровне элементов](/js/element/).

🛠 Из-за своей древовидной структуры искать элементы по DOM можно не только от корня. В диаграмме выше можно найти сначала элемент `ul`, а затем искать элементы среди его потомков.

```js
let ulElement = document.getElementsByTagName("ul")[0] // получили узел ul
let lastLi = ulElement.querySelector("li:last-child") // среди потомков ul нашли последний li

lastLi.style.color = "red" // поменяли цвет шрифта
```
