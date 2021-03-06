🛠 Начинающие разработчики часто допускают ошибку при перечислении селекторов: по их логике первая часть составного селектора не требует повторения и её можно указать один раз в начале, а затем перечислить через запятую несколько «вторых» частей составного селектора.

Вложенным селектор считается только в первой строке, остальные классы отдельные,
сами по себе.

Вот так **неверно**:
```css
.parent-class .child-class,
.another-class,
.one-another-class {
  /* Стили */
}
```

А вот так **верно**! Все три перечисленных селектора являются вложенными:
```css
.parent-class .child-class,
.parent-class .another-class,
.parent-class .one-another-class {
  /* Стили */
}
```

По факту, перечисление через запятую — просто удобный способ сокращения кода, что вписывается в рамки [принципа DRY](https://ru.wikipedia.org/wiki/Don%E2%80%99t_repeat_yourself).

🛠 Не злоупотребляйте перечислением селекторов через запятую. Особенно составных. Если в стилях слишком много перечислений селекторов, присмотритесь к одной из методологий написания CSS — например, [БЭМ](https://ru.bem.info/methodology/) 😎
