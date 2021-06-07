---
permalink: false
tags:
  - practice
---
🛠 Поскольку картинка — строчный элемент, после неё есть небольшой отступ, похожий на пробел между словами. Иногда этот отступ сильно мешает. Но не все начинающие разработчики понимают, как от него избавиться.

Всё просто! Измени поведение картинки со строчного на блочное (`block`) или строчно-блочное (`inline-block`).

🛠 Частый дизайнерский приём — наложение поверх картинки цветного оверлея. И если для фоновой картинки это можно сделать при помощи псевдоэлемента, то с тегом `<img>` этот приём не сработает. Для этого элемента невозможно задать псевдоэлемент, так уж устроены _замещаемые_ элементы, вроде `<iframe>`, `<video>`, `<img>` и других.

Чтобы реализовать оверлей, нужно будет завернуть картинку в дополнительный блок-обёртку и уже ей задать псевдоэлемент.

```html
<div class="parent">
  <img class="child" src="some-image.jpg" alt="Три собаки: одна смотрит влево, вторая закрыла глаза и спит, третья смотрит вправо">
</div>
```

```css
.parent {
  position: relative;
  width: 380px;
}

.parent::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(15, 180, 29, 0.7);
}

.child {
  display: block;
  width: 100%;
}
```

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="solarrust" data-slug-hash="dyvGrRZ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="dyvGrRZ">
  <span>See the Pen <a href="https://codepen.io/solarrust/pen/dyvGrRZ">
  dyvGrRZ</a> by Alena (<a href="https://codepen.io/solarrust">@solarrust</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
