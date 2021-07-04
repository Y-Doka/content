🛠 В настоящий момент стили для псевдокласса `:invalid` применяются к невалидному полю сразу же, что не всегда удобно. Было бы круто, если бы валидация включалась, только если пользователь начал что-то вводить, но, к сожалению, пока нет такой возможности «из коробки».

В будущих версиях спецификации CSS должен появиться псевдокласс `:user-invalid`, который задуман как раз для целей, описанных выше. То есть, он будет применяться, например, к полю ввода только после того, как пользователь начал там что-то писать.

Но это пока перспективы, а что же можно сделать сейчас? В настоящий момент добиться похожего поведения можно только для полей ввода. При этом нужно выполнить два условия:

- добавить атрибут `placeholder`;
- использовать псевдокласс [`:placeholder-shown`](/css/placeholder-shown).

```html
<form>
  <div class="form-row">
    <label for="first-name">Имя:</label>
    <input type="text" name="first-name" id="first-name" required placeholder="Например, Пётр">
    <span class="validity-icon"></span>
  </div>
  <div class="form-row">
    <label for="email">E-mail:</label>
    <input type="email" name="email" id="email" placeholder="Например, mymail@gmail.com">
    <span class="validity-icon"></span>
  </div>
  <div class="form-row">
    <button type="submit">Отправить</button>
  </div>
</form>
```

```css
input:invalid {
  border: 2px solid red;
}

input:invalid:placeholder-shown {
  border-color: black;
}

input:invalid:placeholder-shown + .validity-icon::before,
input:valid:placeholder-shown + .validity-icon::before {
  visibility: hidden;
}
```

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="ezhkov" data-slug-hash="GRNKxvy" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title=":invalid / :valid">
  <span>See the Pen <a href="https://codepen.io/ezhkov/pen/GRNKxvy">
  :invalid / :valid</a> by Denis Ezhkov (<a href="https://codepen.io/ezhkov">@ezhkov</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
