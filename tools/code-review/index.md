---
title: "Код-ревью — как, зачем, почему"
tags:
  - article
authors:
  - igorkamyshev
contributors:
  - furtivite
cover:
  desktop: 'images/cover.png'
  alt: 'Робот-тестировщик идёт над пропастью между двух год по подвесному мосту, который обрывается пунктиром'
summary:
  - code review
  - pull request
  - пул реквест
---

## Кратко

В индустрии разработки программ очень распространена практика __код-ревью__. Программист отправляет написанный код своим коллегам. Они просматривают код и высказывают свои замечания.

Такой подход позволяет найти потенциальные проблемы, которые не заметил автор. Кроме того, такая практика распространяет знания внутри команды и помогает всем инженерам хорошо разбираться в коде.

## Как происходит

Обычно разработчик отправляет на ревью набор изменений, которые решают определённую задачу — добавляют новую функциональность или исправляют ошибку. Чаще всего, такие изменения программист [делает в своей ветке](/js/tools/version-control/), а перед слиянием в основную запрашивает обзор своих изменений у коллег.

Отправка изменений на код-ревью происходит через __пул-реквесты__. Для прохождения код-ревью нужно получить одобрение одного или нескольких коллег. Способ выбора коллег для проведения ревью зависит от процессов внутри компании.

Пул-реквест (PR) — это предложение слить изменения в ветке разработчика с другой веткой. Иногда их называют мёрж-реквестами (MR).

Типичной код-ревью к пул-реквесту на GitHub выглядит так:

![Пример обсуждения в пул-реквесте](images/1.png)

В некоторых командах код-ревью — это опциональный процесс, автор изменений сам решает, нужен ли ему сторонний взгляд. Такой подход помогает разгрузить разработчиков, не заставляя их просматривать большое количество простых правок. С другой стороны, при таком подходе на автора ложится большая ответственность за качество написанного кода.
