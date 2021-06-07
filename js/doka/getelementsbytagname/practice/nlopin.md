---
permalink: false
tags:
  - practice
---


🛠 Поиск по тегам нужен нечасто.

🛠 Для поиска вообще всех элементов в качестве аргумента нужно передать строку `'*'`, её называют wildcard.

🛠 Метод возвращает живую коллекцию. Это означает, что коллекция будет автоматически обновляться, если на странице появятся подходящие элементы:

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="js,result" data-user="Lopinopulos" data-slug-hash="xNOBow" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="xNOBow">
  <span>See the Pen <a href="https://codepen.io/Lopinopulos/pen/xNOBow">
  xNOBow</a> by Nikolai Lopin (<a href="https://codepen.io/Lopinopulos">@Lopinopulos</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

🛠 Не спеши, когда пишешь циклы над `HTMLCollection`. Так как коллекция живая, то цикл может стать бесконечным в тех случаях, когда на страницу добавляются и удаляются подходящие под поиск элементы.

🛠 Скрипты, которые работают с HTML видят только ту разметку, которую уже распарсил браузер. Браузер парсит HTML сверху вниз. Если ваш скрипт находится вверху страницы, то он не найдёт элементы ниже в странице — браузер их ещё не увидел и ничего о них не знает. Поэтому скрипты либо подключают в конце страницы, либо [подписываются на событие](/js/doka/event-load-and-domcontentloaded/) `DOMContent​Loaded`, которое сигнализирует о том, что браузер распарсил весь HTML.
