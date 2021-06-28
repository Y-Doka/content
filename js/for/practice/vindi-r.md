---
---

🛠 Необязательно начинать счётчик с нуля. Он может быть равным любому значению. Отсчёт с нуля делается для удобства восприятия и облегчения дальнейшего обслуживания кода. Условие проверки так же может быть любым, важно чтобы результат проверки был true или false:

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="vindi-r" data-slug-hash="WWxaPV" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="for в работе">
  <span>See the Pen <a href="https://codepen.io/vindi-r/pen/WWxaPV">
  for в работе</a> by vindi-r (<a href="https://codepen.io/vindi-r">@vindi-r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

Завершающая операция может быть не только i++ или i--, а абсолютно любой:

```js
for (let i = 0; i < 10; i = i + 2) {
  console.log(i)
}
// Результат работы цикла
// 0
// 2
// 4
// 6
// 8
```

🛠 При необходимости произвести операции не над всеми данными, а только над частью.

Например при выборке каждого N элемента:

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="vindi-r" data-slug-hash="ROReQM" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="for в работе">
  <span>See the Pen <a href="https://codepen.io/vindi-r/pen/ROReQM">
  for в работе</a> by vindi-r (<a href="https://codepen.io/vindi-r">@vindi-r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

🛠 Через циклы удобно вставлять данные, например в таблицы или списки:

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="vindi-r" data-slug-hash="gyMQYq" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="for в работе">
  <span>See the Pen <a href="https://codepen.io/vindi-r/pen/gyMQYq">
  for в работе</a> by vindi-r (<a href="https://codepen.io/vindi-r">@vindi-r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

🛠 Важно следить за условиями и завершающими операциями, чтобы не попасть в бесконечный цикл. Если попасть в бесконечное исполнение, то страница «зависнет». Браузеры умеют определять такие страницы, но для пользователя это крайне неприятная штука:

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="vindi-r" data-slug-hash="axZQLY" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="for в работе, битый цикл">
  <span>See the Pen <a href="https://codepen.io/vindi-r/pen/axZQLY">
  for в работе, битый цикл</a> by vindi-r (<a href="https://codepen.io/vindi-r">@vindi-r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

🛠 Хотя для поиска элемента в массиве существуют встроенные функции, но если нет понимания как работают и что представляют из себя «функции высшего порядка» — можно воспользоваться циклом for:

```js
let arr = [1, 2, 5, -3, 15, 20, 13, -3, -5, -10, 22, 14]
// Задача — найти все отрицательные элементы
let found = []
for (let i = 0; i < arr.length; i++) {
  if (arr[i] < 0) {
    found.push(arr[i])
  }
}
console.log(found)
```
