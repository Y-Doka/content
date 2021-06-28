---
permalink: false
---

🛠 Используй индексы для получения отдельных элементов коллекции:

```js
let paragraphs = document.getElementsByTagName("p")
console.log(paragraphs[0])
```

🛠 Если нужно обойти все элементы в цикле, то можно написать классический цикл `for`:

```js
let paragraphs = document.getElementsByTagName("p")
for (let i = 0; i < paragraphs.length; ++i) {
  console.log(paragraphs[i].id) // печатаем значение атрибута id элемента
}
```

Другой вариант — воспользоваться синтаксисом `for..of`:

```js
let paragraphs = document.getElementsByTagName("p")
for (let item of paragraphs) {
  console.log(item.id)
}
```

🛠 Когда пишешь цикл с `HTMLCollection` убедись, что подходящие элементы не добавляются или удаляются со страницы в момент работы цикла. Так как коллекция живая, её обновление во время цикла может создать бесконечный цикл.

🛠 Если очень нужны методы массива, то преобразуй `HTMLCollection` или `NodeList` в массив с помощью `Array.from`.

```js
let paragraphs = document.getElementsByTagName("p")
let array = Array.from(paragraphs)

console.log(array.pop())
```

Такое преобразование обычно не требуется. Подумай, точно ли оно подходит под твою задачу.
