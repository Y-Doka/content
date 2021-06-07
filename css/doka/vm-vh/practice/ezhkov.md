---
permalink: false
tags:
  - practice
---
🛠 В операционных системах Linux и Windows использование `100vw` может осложняться тем фактом, что вертикальный скроллбар является частью вьюпорта и уменьшает фактическую ширину страницы. Но ширина вьюпорта остаётся неизменной. Поэтому, если есть вертикальный скролл, то задание ширины блока `100vw` вызовет появление горизонтального скролла. На MacOS этот эффект не наблюдается, потому что там скролл располагается НАД содержимым страницы, а не рядом.

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="ezhkov" data-slug-hash="pobLBBd" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="vw100">
  <span>See the Pen <a href="https://codepen.io/ezhkov/pen/pobLBBd">
  vw100</a> by Denis Ezhkov (<a href="https://codepen.io/ezhkov">@ezhkov</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

В ОС Linux и Windows в этом примере будет наблюдаться горизонтальный скролл.

🛠Относительные единицы измерения прекрасно подходят для адаптивной вёрстки, а если учесть, что на мобильных устройствах скролл находится НАД содержимым страницы, у нас вообще нет никаких проблем с этими единицами.
