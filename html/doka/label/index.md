---
title: "<label>"
authors:
  - ezhkov
contributors:
  - skorobaeus
tags:
  - sprint-4
  - sprint-6
summary:
  - лейбл
  - подпись поля ввода
---

## Кратко

Элемент `<label>` используется для создания подписи к элементу формы:

## Пример

```html
<div class="form-row">
  <label for="bread">Купить хлеб</label>
  <input type="checkbox" name="bread" id="bread">
</div>
```

## Как пишется

```html
<!-- Прямая связь с элементом формы (элемент формы внутри <label>) -->
<label>Click me <input type="text"></label>

<!-- Связь с элементом формы через атрибут for -->
<label for="username">Click me</label>
<input type="text" id="username">
```

## Как это понять

На многих веб-страницах есть формы — группы интерактивных элементов (полей ввода, выпадающих списков, чекбоксов и т.п.), связанных общим функциональным назначением. Яркие примеры форм — форма регистрации, форма входа, фильтры в каталогах. Формами удобно пользоваться, когда мы понимаем назначение каждого элемента. Для этого необходимо подписывать каждый элемент. И вот как раз для этих целей служит элемент `<label>`.

Помимо текстовой подписи создаётся программная связь между подписью и элементом формы. Это сильно облегчает взаимодействие с формами незрячим или слабовидящим пользователям, использующим скринридеры. Когда фокус попадает на элемент формы, с которым связан `<label>`, скринридер автоматически зачитывает текст подписи, и пользователь понимает, какие данные необходимо ввести или какие данные представлены в текущем элементе формы.

Чтобы связать `<label>` с элементом формы можно пойти двумя путями:

1. Задаём элементу формы атрибут `id`. Такое же значение задаём атрибуту `for` тега `<label>`.
2. Оборачиваем элемент формы в тег `<label>`. В этом случае связь создаётся автоматически и нет необходимости в атрибутах `id` и `for`.

```html
<form action="">
  <label for="phone">Ваш телефон:</label>
  <input type="tel" name="phone" id="phone">

  <label>
    <input type="checkbox" name="agree">Согласен на обработку данных
  </label>
</form>
```

<iframe title="Два способа связать label и input" src="demos/label-input.html"></iframe>

## Атрибуты

`for` — значение этого атрибута должно соответствовать значению атрибута `id` связываемого элемента. Первый же элемент в документе, чей `id` будет совпадать со значением атрибута `for`, становится связанным с нашим `<label>`. Единственное условие — элемент должен принадлежать к группе связываемых элементов: [`<button>`](/html/doka/button), [`<input>`](/html/doka/input), [`<meter>`](/html/doka/TODO)(в работе), [`<output>`](html/doka/TODO)(в работе), [`<progress>`](html/doka/TODO)(в работе), [`<select>`](html/doka/select) и [`<textarea>`](html/doka/textarea).

Если элемент с нужным `id` не является связываемым, то связь не создаётся, и даже если дальше по документу найдётся связываемый элемент с таким же `id`, то он уже не будет учитываться.

## Подсказки

💡 Один элемент формы может быть связан с несколькими `<label>`, но один `<label>` может быть связан ровно с одним элементом формы.

💡 При клике на `<label>` событие клика вызывается также и на связанном элементе формы.

💡 По умолчанию `<label>` является инлайновым элементом и стилизуется аналогично [`<span>`](/html/doka/span) или [`<a>`](/html/doka/a).