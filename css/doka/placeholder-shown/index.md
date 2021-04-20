---
title: ":placeholder-shown"
author:
  -  ezhkov
summary:
  - форма
  - плейсхолдер
  - валидация
---

## Кратко

Псевдокласс `:placeholder-shown` выбирает на странице все [`<input>`](/html/doka/input) или [`<textarea>`](/html/doka/textarea), у которых показывается плейсхолдер.

## Пример

```html
<input placeholder="Введите ваше имя">
```

```css
input {
  border: 1px solid black;
}

input:placeholder-shown {
  border-color: teal;
}
```

## Как это понять

Если полю ввода задан атрибут `placeholder` с каким-то значением, то внутри поля будет показана текстовая подсказка. Она пропадёт, если пользователь введёт хотя бы один символ. По сути псевдокласс `:placeholder-shown` будет применять стили к пустым полям ввода.

## Как пишется

```css
:placeholder-shown {
  color: teal;
}
```

## Подсказки

💡 Псевдокласс `:placeholder-shown` — это **не то же самое**, что псевдоэлемент [`::placeholder`](/css/doka/placeholder). Псевдокласс применит стили к самому полю ввода. А стили, применённые к псевдоэлементу [`::placeholder`](/css/doka/placeholder), изменят внешний вид текста подсказки, но никак не затронут само поле ввода.
