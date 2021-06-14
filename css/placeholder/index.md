---
title: "::placeholder"
tags:
  - doka
  - sprint-2
authors:
  - ezhkov
contributors:
  - skorobaeus
summary:
  - плейсхолдер
  - placeholder
---

## Кратко

Псевдоэлемент `::placeholder` используется для стилизации текста-плейсхолдера в полях ввода [`<input>`](/html/input/) и [`<textarea>`](/html/textarea/).

## Пример

```html
<input class="form-input" type="email" placeholder="Например: mygre@ema.il">
```

```css
.form-input::placeholder {
  color: gray;
}
```

<iframe title="Плейсхолдер в поле ввода" src="demos/index.html"></iframe>

## Как это понять

Элементам [`<input>`](/html/input/) и [`<textarea>`](/html/textarea/) можно задавать атрибут `placeholder`. Текст, содержащийся в этом атрибуте, будет отображаться внутри поля ввода, пока пользователь ничего не ввёл. Этот текст можно стилизовать, используя псевдоэлемент `::placeholder`. Стили для введённого текста и текста-плейсхолдера в общем случае должны различаться.

## Как пишется

```css
::placeholder {
  color: gray;
}
```

Стиль применится ко всем плейсхолдерам на странице.

```css
.email-input::placeholder {
  color: darkblue;
}
```

Стиль применится только к плейсхолдерам на полях ввода атрибут `class` которых равен `email-input`.

## Подсказки

💡 Для стилизации плейсхолдера можно использовать только следующие свойства:

- все шрифтовые свойства, начинающиеся с `font` (например, [`font-size`](/css/font-size/) или [`font-style`](/css/font-style/));
- все свойства для работы с фоном, начинающиеся с `background-` (например, [`background-color`](/css/background-color/) или [`background-size`](/css/background-size/));
- свойство [`color`](/css/color/);
- свойства [`word-spacing`](/css/word-spacing/), [`letter-spacing`](/css/letter-spacing/), [`text-decoration`](/css/text-decoration/), [`text-transform`](/css/text-transform/) и [`line-height`](/css/line-height/);
- свойства [`text-shadow`](/css/text-shadow/), группу свойств [`text-decoration`](/css/text-decoration/) и [`vertical-align`](/css/vertical-align/).
