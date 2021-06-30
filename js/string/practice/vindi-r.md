
🛠 При работе с формами и вводом значений следует очищать поля ввода от замыкающих пробелов. Например если в поле ввода e-mail окажутся пробелы по концам — есть шанс что пользователь этого не увидит, а у нас сохранится неправильный адрес почты.

❗️ Не используй этот принцип для обработки паролей!

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="vindi-r" data-slug-hash="ZZjrzB" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Строки - в работе">
  <span>See the Pen <a href="https://codepen.io/vindi-r/pen/ZZjrzB">
  Строки - в работе</a> by vindi-r (<a href="https://codepen.io/vindi-r">@vindi-r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

🛠 Множественная замена в строке возможна через цикл или через регулярные выражения:

```js
let str = "Яблоко - вкусный овощ. Яблоко - вкусный овощ. Яблоко - вкусный овощ"
let hasApple = str.indexOf("Яблоко") !== -1
while (hasApple === true) {
  str = str.replace("Яблоко", "Помидор")
  hasApple = str.indexOf("Яблоко") !== -1
}
console.log(str) // Помидор - вкусный овощ. Помидор - вкусный овощ. Помидор - вкусный овощ
```

Для решения задачи по смене яблок на помидоры код выглядит слишком избыточно. Вариант с replace через регулярные выражения проще и удобнее, но для этого нужно изучить базовый синтаксис использования регулярных выражений.

```js
let str = "Яблоко - вкусный овощ. Яблоко - вкусный овощ. Яблоко - вкусный овощ"
let changedStr = str.replace(/Яблоко/g, "Помидор")
console.log(changedStr) // Помидор - вкусный овощ. Помидор - вкусный овощ. Помидор - вкусный овощ
```

🛠 Сравнение чисел: Если числа представлены в виде строк, то может получится неожиданный результат, например 2 будет больше чем 14 🤖

Поэтому если тебе нужно сравнить два числа, то их стоит принудительно приводить к числовому типу:

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="vindi-r" data-slug-hash="JVBLQG" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Строки - в работе">
  <span>See the Pen <a href="https://codepen.io/vindi-r/pen/JVBLQG">
  Строки - в работе</a> by vindi-r (<a href="https://codepen.io/vindi-r">@vindi-r</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>
