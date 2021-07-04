🛠 При вёрстке «классических» макетов необходимости в управлении полосой прокрутки практически нет. Чтобы избежать появления нежелательных полос прокрутки, минимизируйте явное задание высоты (кроме случаев, где это действительно необходимо).

Ещё один пример, когда будет полезно знание свойства `overflow` — обрезание текста с многоточием (в сочетании со свойством `text-overflow: ellipsis` или недокументированного `-webkit-line-clamp`):

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="css,result" data-user="Realetive" data-slug-hash="poERRWW" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="truncate text">
  <span>See the Pen <a href="https://codepen.io/Realetive/pen/poERRWW">
  truncate text</a> by Roman Ganin (<a href="https://codepen.io/Realetive">@Realetive</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
