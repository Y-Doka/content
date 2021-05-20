---
title: "animation"
authors:
  - solarrust
summary:
  - CSS-анимации
  - ключевые кадры
---

## Кратко

`animation` это мега-шорткат, в котором можно за раз указать значения для всех свойств, начинающихся на `animation-`:

- `animation-name`;
- `animation-duration`;
- `animation-iteration-count`;
- `animation-direction`;
- `animation-timing-function`;
- `animation-delay`;
- `animation-play-state`;
- `animation-fill-mode`.

## Пример

```css
.element {
  animation: circle-to-square 2s infinite alternate-reverse ease-in 1s;
}
```

## Как пишется

Значения указываются через пробел. Порядок указания значений не важен. Из-за того, что значения этих свойств очень разные, браузер сам догадывается, какое значение к какому свойству относится. Важно только помнить, что первое значение времени будет воспринято как значение `animation-duration` (длительность анимации), а второе — `animation-delay` (задержка воспроизведения).

Для работы анимации совсем не обязательно перечислять все значения. Достаточно указать имя анимации и её длительность. Для остальных свойств будут установлены значения по умолчанию.

## Подсказки

:::callout 🦄

Подробнее об анимациях написано в статье [CSS-анимации](/css/articles/animation).

:::
