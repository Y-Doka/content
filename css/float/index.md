---
title: "float"
author: lenaryan
summary:
  - float
  - обтекание
  - clearfix
  - flow-root
---

## Кратко

Свойство помогает «обтекать» блоки текстом.

## Пример

<p class="codepen" data-height="350" data-theme-id="light" data-default-tab="result" data-user="lenaryan" data-slug-hash="PobvRGz" style="height: 350px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Float Demo">
  <span>Посмотреть пен <a href="https://codepen.io/lenaryan/pen/PobvRGz">
  Float Demo</a> на <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## Как это понять

Иногда при вёрстке блока нужно, чтобы текст рядом с картинкой занимал всё оставшееся место, а после картинки располагался на всю ширину блока. Для таких ситуаций и создан `float`. Элемент, для которого указано это свойство, частично выходит из потока: все элементы блочного контекста, прописанные в коде после элемента с `float`, занимают его место, а элементы строчного контекста — «обтекают» его.

## Как пишется

```css
.element {
  float: left;
}
```

В файле стилей пишем селектор элемента, который будем «обтекать», и указываем одно из трёх значений свойства:

- `left` — элемент встанет у левого края родительского блока.
- `right` — элемент встанет у правого края родительского блока.
- `none` — значение по умолчанию, элемент останется в потоке.

## Подсказки

💡 Применяя `float` к элементу, мы неявно делаем его блочным.
