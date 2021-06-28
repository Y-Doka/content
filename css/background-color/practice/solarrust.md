---
---

🛠 Если нужна красивая кнопка (`button`), то не забудь *сбросить* фон: укажи для `background-color: transparent`. Или тот цвет фона, который нужен по дизайну. По умолчанию у всех кнопок серый фон с приветом из девяностых.

🛠 Аналогичным способом можно сделать красивые прозрачные поля ввода (`input`) в формах.

```html
<form class="form">
  <label>
    Email:
    <input class="input" type="text" placeholder="Введите ваш email">
  </label>
  <button class="submit">Подписаться</button>
</form>
```

```css
.form {
  background-color: #ffd829; /* Фон для всей формы */
}

.input {
  background-color: transparent; /* Прозрачное поле ввода */
}

.submit {
  background-color: black; /* Чёрный фон для кнопки */
  transition: 0.3s ease-in-out; /* Анимируем всё анимируемое */
}

.submit:hover {
  background-color: transparent; /* Прозрачный фон при наведении курсора */
}
```

<iframe title="Форма" src="../demos/form.html"></iframe>

🛠 Если вам нужен градиент, то `background-color` вам не подойдёт. Градиенты можно задать только при помощи `background-image`.

🛠 Если нужен блок с «рваным» краем, но без пробела между строками, то для этого есть множество трюков. Один из них:

```html
<div class="parent">
  Чем отличается маркер от текстовыделителя?
  <span class="bkg">
    Текстовыделительные маркеры заправляются флуоресцентными полупрозрачными
    чернилами. Они не покрывают поверхность бумаги плотным слоем, не
    пропускающим свет, как это делают обычные маркеры на водной или спиртовой
    основе.
  </span>
</div>
```

```css
.parent {
  padding: 25px;
}

.bkg {
  font-size: 16px;
  line-height: 1.5;
  background-color: #ffd829;
  box-shadow: 0 6px 0 #ffd829; /* Тень для каждой строки, перекрывающая пробел */
}
```

<iframe title="Блок с рваным краем, но без пробела" src="../demos/shadow.html"></iframe>

🛠 С помощью полупрозрачного фонового цвета у псевдоэлемента можно создать красивый оверлей поверх фотографий или фоновых изображений. Это круто потому что фоном можно будет ставить любую фотографию и она в большинстве случаев не будет выбиваться из дизайна.

```html
<header class="header">
  <h1 class="title">The best site all ower the world!</h1>
</header>
```

```css
.header {
  position: relative; /* Чтобы псевдоэлемент считал своё положение от этого блока */
  z-index: 0;
  background: url("background.png") no-repeat center / cover; /* Фоновое изображение на всю ширину и высоту блока */
}

.header:before {
  content: "";
  position: absolute;
  z-index: -1;
  display: block;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 79, 130, 0.5);
  /* Оверлей поверх картинки с прозрачностью 50% */
}
```

<iframe title="Цветная вуаль поверх блока" src="../demos/veil.html"></iframe>

Для `.header` можно задать любую картинку фоном и поверх неё всегда будет голубой оверлей 💁‍♀️
