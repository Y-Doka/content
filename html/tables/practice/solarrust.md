---
tags:
  - practice
permalink: false
---

🛠 Частый дизайнерский приём — подсветка строк таблицы через одну. Это помогает считывать длинные таблицы, глазу есть за что зацепиться.

Например, сделаем каждую вторую строку с серым фоном. Для этого понадобится всего одно CSS-правило с псевдоклассом [`:nth-child()`](/css/child/):

```css
tr:nth-child(even) {
  background-color: gray;
}
```

На всякий случай подстрахуемся и ограничим область _раскрашивания_ только телом таблицы, исключим шапку и подвал.

```css
tbody tr:nth-child(even) {
  background-color: gray;
}
```

🛠 Можно сделать так, чтобы строка с заголовками колонок **прилипала** при прокрутке длинной таблицы. Это удобно, если данных много и пользователь может просто забыть, в какой колонке какие данные.

Это довольно просто сделать при помощи `position: sticky`. Имейте в виду, что нельзя применить это свойство к тегам `<thead>` или `<tr>`, поэтому применим его к `<th>`.

```css
th {
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  z-index: 1;
}
```

Не забудьте добавить `position: relative` для родителя. Заодно подстрахуемся и сделаем прилипающими только заголовки в шапке таблицы.

```css
table {
  position: relative;
}

thead th {
  position: sticky;
  position: -webkit-sticky;
  top: 0;
  z-index: 1;
}
```

Задайте фон заголовкам, чтобы текст ячеек не был виден при прокрутке. А чтобы избавиться от белых линий между ячейками, зададим для всей таблицы свойство `border-collapse: collapse`:

```css
table {
  position: relative;
  border-collapse: collapse;
}

thead th {
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  z-index: 1;
  background-color: lightgray;
}
```

:::callout ☝️

Если сайт должен хорошо работать в старых браузерах, обязательно проверьте поддержку `sticky` на [Can I use…](https://caniuse.com/css-sticky).

:::