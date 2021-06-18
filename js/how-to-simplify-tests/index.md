---
title: "Как упростить тестирование"
authors:
  - bespoyasov
tags:
  - article
summary:
  - test
  - pure functions
  - coupling
---

Давайте будем откровенными, тесты писать *лень*. Даже если мы работаем по [TDD](/js/tdd/), и тесты стали частью культуры, внешнее давление может нас вынудить тесты пропустить.

Часто лень — это следствие *неудобства*. Если писать тесты неудобно, то и охоту их писать быстро отобьёт.

Мы можем использовать разные стратегии для того, чтобы сделать тестирование удобнее:

- использовать чистые функции и писать слабо-сцепленный код;
- делать тесты независимыми друг от друга и окружения;
- чётко описывать предусловия и ожидания от теста, следовать [ПВП](/js/how-to-test-and-why/),
- тестировать только свой код;
- использовать более удобные инструменты тестирования;
- вести общее хранилище фиктивных данных и моков.

В этой статье мы подробно разберём каждый из этих способов.

## Чистые функции и слабое зацепление

*Чистая функция (pure function)* — это функция, которая не взаимодействует с окружением, то есть не производит сайд-эффектов. Такие функции *всегда* возвращают одинаковое значение при одинаковых аргументах.

:::callout 💡

Например, все математические функции — чистые. `sin(30°)` всегда равен 1/2, безотносительно расположения звёзд на небе.

:::

Функции с побочными эффектами («нечистые») возвращают разный результат при разных состояниях среды:

```js
function currentTime() {
  return Date.now()
}
```

У функции `currentTime` есть побочные эффекты: она ссылается на текущее время, при каждом вызове это время будет разным.

Тестировать чистые функции проще остальных. Для теста нам нужны только исходные данные и ожидаемый результат, никакой дополнительной инфраструктуры не требуется.

На чистых функциях удобно описывать бизнес-логику. Это главная часть приложения, и чем проще она написана, тем меньше трения для тестов и тем надёжнее эта часть написана.

Если использовать чистые функции по каким-то причинам нельзя, то стоит посмотреть в сторону функциональной архитектуры.

### Функциональная архитектура

В такой архитектуре принято, что чистые функции не могут вызывать функции с сайд-эффектами, только наоборот. Используя её, мы можем создать «сэндвич», где:

- Функции с сайд-эффектами общаются с внешним миром, получают от окружения данные (запросы к БД, реакция на действия пользователей — это всё здесь);
- Затем чистые функции как-то преобразовывают полученные данные;
- А после функции с сайд-эффектами меняют состояние внешнего мира (например, перерисовывают пользовательский интерфейс).

Получается, как его [зовёт Марк Симан](https://blog.ploeh.dk/2020/03/02/impureim-sandwich/), *impure / pure / impure* или *impureim* сэндвич.

![Impureim сэндвич: тонкий красный слой сверху, толстый зелёный злой посередине, тонкий красный слой снизу.](images/impureim-sandwich.png)

Чистые функции в таком сэндвиче только преобразовывают данные, получить эти данные и отобразить — дело функций с сайд-эффектами.

Можно сказать, что «хлеб» в этом сэндвиче позволяет нам создать условия для вызова чистой функции с основной работой, а потом посмотреть или вывести результат.

### Слабое зацепление

Ещё одна большая проблема при написании тестов — сильное зацепление кода.

[Зацепление](https://ru.wikipedia.org/wiki/Зацепление_(программирование)) — это степень взаимозависимости разных модулей. Чем выше зацепление, тем более хрупкой, запутанной получается система, и тем сложнее вносить изменения.

:::callout 🙅

Зацепление не стоит путать со связностью. [Связность](https://ru.wikipedia.org/wiki/Связность_(программирование)) — степень, в которой задачи некоторого модуля, связаны друг с другом. Чем выше связность, тем строже модули следуют [SRP](https://ota-solid.now.sh/srp), тем выше сфокусирован модуль на конкретной задаче.

:::

Чем выше зацепление, тем больше приходится городить заглушек, моков, подставных объектов, чтобы что-то протестировать. Написание тестов превращается в долгое исследование зависимостей, которые надо замокать, чтобы хоть что-то запустилось.

Добиться низкого зацепления можно, следуя [принципу инверсии зависимостей](https://ota-solid.now.sh/dip). Согласно ему, детали реализации должны зависеть от абстракций и никогда не наоборот.

Следуя этому принципу мы пишем такой код, что сущности между собой связываются через [интерфейсы](/js/oop/) — контракты на поведение. Если детали реализации зависят от интерфейса, то их становится проще заменить.

Заменять детали реализации можно не только другими модулями в коде, но и моками при тестировании. Сложных зависимостей становится меньше, неудобство тестирования уменьшается.

## Независимые тесты

Тесты стоит писать так, чтобы их можно было запускать в каком угодно порядке, во сколько угодно потоков, на какой угодно машине.

Когда тесты друг от друга не зависят, они не будут влиять на результаты работы друг друга. Соответственно они не смогут и исказить результаты тестирования.

Кроме того, если каждый тест независим от других тестов и окружения, их можно запускать параллельно группами, чтобы ускорить процесс.

Также независимые тесты экономят нам время, когда падают. Они однозначно показывают, что и где именно сломалось.

## Чёткие условия и ожидания

Деталей в описании теста должно быть ровно столько, чтобы быстро понять, что тест проверяет и в каких условиях.

Меньшее количество деталей отнимет время в будущем, когда тест упадёт. Скудные описания трудно читать и соотносить с задачами. Большее количество деталей отнимает время при написании и чтении в будущем, отвлекает от сути теста.

Также важно однообразие и последовательность при описании. Если в проекте встречается несколько стилей описания тестов, это будет сбивать с толку и мешать их читать.

## Юнит-тесты только на свой код

Тестировать сторонние библиотеки или фреймворки _не надо_. Юнит-тестами следует покрывать только код, написанный вами и вашей командой.

Тестирование чужого кода отнимает много времени, но притом почти бессмысленно. Мы не можем поменять чужой код, как хотим и когда захотим.

Зато мы можем поменять код адаптеров к сторонним библиотекам, лучше покрыть тестами их. Для проверки работы проекта при обновлении зависимостей стоит использовать интеграционные и E2E-тесты.

## Удобные инструменты тестирования

Удобный тест-раннер решает большую часть проблем с неудобством при написании. Например, в случае с Jest:

- используйте `only`, `skip`, `todo` и [другие методы](https://jestjs.io/docs/api), которые помогают фокусироваться на конкретных тестах;
- интегрируйте [тесты в git-flow](https://jestjs.io/docs/cli#--changedsince), чтобы тестировать только изменённые с последнего коммита файлы;
- используйте фильтры в [watch-режиме](https://jestjs.io/docs/cli#--watch), чтобы запускать тесты по нужным критериям;
- вызывайте [`--debug`](https://jestjs.io/docs/cli#--debug) для быстрой отладки тестов.

## Продуманное хранилище фейковых данных и моков

Общее хранилище моков и данных избавит от необходимости каждый раз с нуля придумывать данные или настраивать моки.

Вместе с таким хранилищем удобно будет завести стратегию автоматического сброса моков, генерации данных по типам и сущностям проекта.

Стоит относиться к инфраструктурному коду так же трепетно, как и к продуктовому, так как пользоваться им придётся вам и вашей команде.

## Заключение

Если упростить тестирование и код тестов, можно решить часть проблем с неудобством. Чем комфортнее процесс, тем меньше трения будет возникать при мысли о тестах для нового модуля.

Первичная настройка и поддержание инфраструктуры может занять какое-то время и ресурсы, но окупится после запуска проекта и во время его поддержки.