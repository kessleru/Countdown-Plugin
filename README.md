# Countdown Plugin

Um simples plugin de contagem regressiva para estudos.

## Tutorial de uso

1. **Baixe ou copie** o arquivo `countdown.js` para o seu projeto.
2. **Implemente** um arquivo principal (por exemplo `script.js`) e importe o plugin:
   ```js
   import Countdown from "./countdown.js";

   const viradaDoAno = new Countdown("31 December 2025 23:59:59 GMT-0300");
   console.log(viradaDoAno.total);
   ```
3. **Adicione** o seu arquivo principal a uma página HTML como módulo ES:
   ```html
   <script type="module" src="script.js"></script>
   ```
4. **Utilize** a propriedade `total` para obter um objeto com `days`, `hours`, `minutes` e `seconds`. Esses valores podem ser usados para atualizar o DOM ou qualquer outra interface.

### Exemplo prático

`script.js`

```js
import Countdown from "./countdown.js";

const natal = new Countdown("24 December 2025 23:59:59 GMT-0300");
const dias = document.querySelector("[data-dias]");
const horas = document.querySelector("[data-horas]");
const minutos = document.querySelector("[data-minutos]");
const segundos = document.querySelector("[data-segundos]");

function atualizarTela() {
  const tempo = natal.total;
  dias.textContent = tempo.days;
  horas.textContent = tempo.hours;
  minutos.textContent = tempo.minutes;
  segundos.textContent = tempo.seconds;
}

atualizarTela();
setInterval(atualizarTela, 1000);
```

`index.html`

```html
<section>
  <span data-dias></span>d
  <span data-horas></span>h
  <span data-minutos></span>m
  <span data-segundos></span>s
</section>
<script type="module" src="script.js"></script>
```
