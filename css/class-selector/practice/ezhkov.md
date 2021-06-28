---
tags:
  - practice
permalink: false
---

🛠 Селектор по классу является основным селектором для стилизации любой веб-страницы. Благодаря тому, что одному элементу можно задать несколько классов, а нескольким элементам — один и тот же класс, мы получаем очень гибкий способ стилизации страниц любой сложности.

Например, мы можем уточнить один селектор по классу другим:

```html
<form action="">
  <label class="form-label invalid" for="input">Ваш email</label>
  <input class="form-input invalid" type="email">
</form>
```

```css
.form-label.invalid {
  color: red;
}

.form-input.invalid {
  border-color: red;
  background-color: #ff000022;
}
```

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="html,result" data-user="ezhkov" data-slug-hash="wvzqMVg" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Class selector 2">
  <span>See the Pen <a href="https://codepen.io/ezhkov/pen/wvzqMVg">
  Class selector 2</a> by Denis Ezhkov (<a href="https://codepen.io/ezhkov">@ezhkov</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

А можем добавить класс родительскому элементу, чуть изменить селекторы и получить тот же результат:

```html
<form action="" class="invalid">
  <label class="form-label" for="input">Ваш email</label>
  <input class="form-input" type="email">
</form>
```

```css
.invalid .form-label {
  color: red;
}

.invalid .form-input {
  border-color: red;
  background-color: #ff000022;
}
```

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="html,result" data-user="ezhkov" data-slug-hash="JjRyGgV" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Class selector 3">
  <span>See the Pen <a href="https://codepen.io/ezhkov/pen/JjRyGgV">
  Class selector 3</a> by Denis Ezhkov (<a href="https://codepen.io/ezhkov">@ezhkov</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

Самое сложное в вёрстке — выбрать способ решения задачи, потому что любая задача решается двумя и более способами 🙂

<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
