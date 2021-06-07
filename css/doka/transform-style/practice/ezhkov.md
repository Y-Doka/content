---
permalink: false
tags:
  - practice
---


🛠 Если нам нужно просто повернуть какой-то элемент в 3D-пространстве, то можно оставить `transform-style: flat` (либо вообще не задавать это свойство). Элемент всё равно будет поворачиваться, к нему будет применяться перспектива, всё будет выглядеть красиво. `transform-style: preserve-3d` нужно задавать, когда мы хотим применять 3D-трансформации и к родителю, и к потомкам, и при этом учитывать их визуальное взаимодействие. Классическим примером такой ситуации является куб, собранный из шести элементов-сторон.

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="ezhkov" data-slug-hash="vYyeZmv" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="transform-style2">
  <span>See the Pen <a href="https://codepen.io/ezhkov/pen/vYyeZmv">
  transform-style2</a> by Denis Ezhkov (<a href="https://codepen.io/ezhkov">@ezhkov</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
