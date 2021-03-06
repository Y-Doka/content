🛠 Чаще всего этот селектор применяется в самом начале файла CSS-стилей, чтобы переопределить встроенные стили браузера для некоторых тегов. Например, сразу определить стили для тегов заголовков или задать внешний вид для абзацев.

```css
h1,
h2,
h3 {
  font-weight: 500;
}

p {
  margin-bottom: 0.5em;
}
```

🛠 Селекторы по тегам активно используются в техниках сброса и нормализации стилей.

```css
h1,
h2,
h3,
h4,
h5,
h6,
p,
figure {
  margin: 0;
}

ul,
ol {
  padding: 0;
  list-style: none;
}

button {
  border: none;
  background-color: transparent;
  padding: 0;
}
```
