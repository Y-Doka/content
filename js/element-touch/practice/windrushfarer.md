🛠 Стоит учесть, что браузеры в ответ на некоторые действия пользователя отправляют одновременно и событие click и событие touch. Например при прикосновении к элементу (допустим по кнопке) последовательность событий будет следующей:

`touchstart` → `touchend` → `mousedown` → `mouseup` → `click`

Стоит помнить эту особенность, если вы на одном и этом же элементе делаете обработку этих событий. Если необходимо, чтобы события мыши не возникали на элементе, то в обработчике события касания нужно вызвать `preventDefault()`.

```js
element.addEventListener('touchstart', (event) => {
  // События мыши теперь не будут вызываться
  event.preventDefault()
})
```

🛠 С помощью `touch` событий можно делать обработку жестов. Например, свайпов. Для этого необходимо будет сохранять координаты, где пользователь прикоснулся (событие `touchstart`), и сравнивать с изменением координат во время движения пальца (событие `touchmove`). Подробнее можно посмотреть в примере.

<p class="codepen" data-height="500" data-theme-id="light" data-default-tab="js,result" data-user="Windrushfarer" data-slug-hash="KKgZGEq" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="KKgZGEq">
  <span>See the Pen <a href=" https://codepen.io/Windrushfarer/pen/KKgZGEq">
  Touch Draw</a> by Egor Ogarkov (<a href="https://codepen.io/Windrushfarer">@Windrushfarer</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>
