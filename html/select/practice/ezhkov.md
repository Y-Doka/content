
🛠 Выпадающий список — это один из элементов формы, почти не поддающихся стилизации. Мы можем немного изменить внешний вид самого элемента `<select>`, но выпадающий список опций вообще не стилизуется. Многие дизайнеры любят рисовать нестандартные выпадающие списки в угоду красоте, но реализация таких списков очень трудоёмка и невозможна на чистом HTML и CSS. Рекомендуется для выпадающих списков оставлять родной вид, потому что такие списки обладают рядом преимуществ перед нестандартными. Например, выпадающий список опций может выходить за границы окна браузера, давая пользователю возможность выбрать нужный элемент.

🛠 Несмотря на вышесказанное, немного стилизовать выпадающий список всё же можно. Но только отображение самого `<select>`, но не списка опций. Вот как можно изменить вид стрелочки:

```html
<form>
  <label for="city-select">Нестандартная стрелочка</label>
  <div class="select-wrapper">
    <select name="city" id="city-select">
      <option selected disabled>-- Выберите город --</option>
      <option value="petersburg">Санкт-Петербург</option>
      <option value="moscow">Москва</option>
      <option value="kazan">Казань</option>
      <option value="samara">Самара</option>
      <option value="perm">Пермь</option>
      <option value="novosibirsk">Новосибирск</option>
    </select>
  </div>
</form>
```

В данном случае мы оборачиваем наш `<select>` дополнительным блоком, чтобы задействовать псевдоэлемент [`::after`](/css/after/) этого блока. К сожалению, `<select>` относится к такому типу элементов, у которых нет своих псевдоэлементов [`::before`](/css/before/) и [`::after`](/css/after/).

```css
.select-wrapper {
  position: relative;
}

.select-wrapper::after {
  content: "⬇️";
  position: absolute;
  right: 0;
  margin-top: -2px;
  pointer-events: none;
}

select {
  appearance: none;
  width: 200px;
  padding: 4px;
  border-color: #aaa;
  border-radius: 3px;
}
```

Используем свойство `appearance`, чтобы отключить браузерную стрелку справа. В качестве стрелки ставим псевдоэлемент [`::after`](/css/after/) от родительского блока. Не забываем про позиционирование, а также отключаем у псевдоэлемента взаимодействие с мышкой, иначе при клике на него выпадающий список раскрываться не будет.

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="html,result" data-user="ezhkov" data-slug-hash="YzGEKjP" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="&amp;lt;select&amp;gt; custom">
  <span>See the Pen <a href="https://codepen.io/ezhkov/pen/YzGEKjP">
  &lt;select&gt; custom</a> by Denis Ezhkov (<a href="https://codepen.io/ezhkov">@ezhkov</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
