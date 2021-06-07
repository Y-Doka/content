---
permalink: false
tags:
  - practice
---
🛠 Как правило, в реальных формах обязательные к заполнению поля выделяют не так явно, как в примерах выше. Обычно после текстового описания обязательного поля ставят звёздочку. В примере ниже, кроме того, показано, как можно стилизовать подсказку к полю.

```html
<form>
  <div class="form-row">
    <label for="first_name">Имя*</label>
    <input type="text" id="first_name" required>
    <span class="hint">Обязательно к заполнению</span>
  </div>
  <div class="form-row">
    <label for="last_name">Фамилия</label>
    <input type="text" id="last_name">
    <span class="hint">Необязательно</span>
  </div>
</form>
```

```css
.hint {
  color: #555555;
}

input:required + .hint {
  color: lightcoral;
}
```

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="ezhkov" data-slug-hash="mdrNzgw" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title=":required">
  <span>See the Pen <a href="https://codepen.io/ezhkov/pen/mdrNzgw">
  :required</a> by Denis Ezhkov (<a href="https://codepen.io/ezhkov">@ezhkov</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
