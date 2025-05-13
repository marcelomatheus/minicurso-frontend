<div class="icon-row">
  <img class="icon" width="80" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" />
  <img class="icon" width="80" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" />
</div>

# Frontend Moderno com Javascript
### Parte I
---

## Ministrantes

<div class="two-columns">


<div class="card">
Marcelo Oliveira<br/>
Engenheiro de Software Jr | Nocorp Applied

https://www.linkedin.com/in/marcelooliveiradev
</div>
<div class="card">
Bernardo Mendes<br/>
Engenheiro de Software Pl | Blips Ativos

https://www.linkedin.com/in/bernardomennndes
</div>

</div>

---

## Agenda do Minicurso

### Parte 1
1. Fundamentos do JavaScript Moderno
2. React: Conceitos Essenciais
3. Praticando JS

### Parte 2
1. Boas Práticas e Padrões
2. Ferramentas do Ecossistema
3. Projeto Prático

---

## 1. O trio do frontend

- **HTML**: Estrutura do conteúdo (títulos, parágrafos, botões, imagens, etc.)
- **CSS**: Estilização da interface (cores, fontes, espaçamentos, animações)
- **JavaScript**: Comportamento dinâmico e interação com o usuário

 Eles trabalham em conjunto: HTML estrutura, CSS estiliza, JS dá vida.

---

## 2. O que é JavaScript?

- Linguagem de programação interpretada pelo navegador
- Orientada a objetos e baseada em protótipos
- Utiliza o DOM para manipular elementos HTML
- **Single-thread** (usa uma thread principal)
- Executa scripts dinamicamente no lado do cliente (e no servidor com Node.js)

---

## 3. DOM (Document Object Model)

- Representação em árvore dos elementos HTML
- Permite interagir e modificar dinamicamente o conteúdo da página

```js
document.getElementById('meuBotao')
document.querySelector('.classe')
```

Propriedades comuns:
- `innerText`, `innerHTML`, `style`, `value`

---

## 4. Prototypes

Todos os objetos em JS herdam de `Object.prototype`.

Exemplo com arrays:
```js
const arr = [1, 2, 3]
arr.map(n => n * 2)  // [2, 4, 6]
```

`Array.prototype` contém: `map`, `filter`, `reduce`, `length`, etc.

Strings também herdam métodos:
```js
'Olá'.toUpperCase()  // "OLÁ"
```

---

## 5. Objetos e tipagem fraca

- Objetos armazenam pares `chave: valor`
```js
const user = { nome: 'João', idade: 25 }
```

- JS é **dinâmico** e **não tipado**:
```js
user.idade = 'vinte e cinco' // válido, mas perigoso
```

Problemas:
- Erros de execução
- Dificuldade de manutenção em projetos grandes

---

## 6. Funções e variáveis

Tipos de função:
```js
function soma(a, b) { return a + b } // Função declarada
const mult = function(a, b) { return a*b } // Função expressa
const sub = (a, b) => a - b // Arrow function
```

Declaração de variáveis:
- `var`, `let`, `const`

---

## 7. Importando e exportando arquivos (ES Module)
Importação/Exportação:
```js
// arquivoA.js
export const nome = 'JS'

// arquivoB.js
import { nome } from './arquivoA.js'
```

---

## 8. Lidando com Promises

Você pode escolher não resolver um promise, ou resolvê-la:
.then()
```js
fetch(url)
  .then(res => res.json())
  .finally(() => console.log('Finalizado'))
```
Async/await:
```js
async function carregar() {
  const res = await fetch(url)
  const dados = await res.json()
}
```

---

## 9. Fetch API

- Usado para consumir dados de APIs HTTP

```js
fetch('https://api.exemplo.com')
  .then(res => res.json())
  .then(data => console.log(data))
```

É uma Promise, pode ser usada com `await`.

---

## 10. Callbacks

- Callback: função passada como argumento para outra função
```js
function somar(a, b) {
  return a + b;
}

function executar(fn, a, b) {
  return fn(a, b)
}

console.log(executar(somar, 4, 5))
```

---

## 11. Sintaxe básica JS

```js
const nome = 'Maria'
function saudacao(pessoa) {
  return `Olá, ${pessoa}`
}
console.log(saudacao(nome))
```

- Tipagem dinâmica
- Orientado a objetos
- Operadores: `=`, `==`, `===`, `&&`, `||`

---

## 12. O que é React?

- Biblioteca JS para construção de interfaces
- Resolve o problema da atualização manual do DOM
- Cria interfaces reativas baseadas em **estado** e **componentes**

---

## 13. Conceitos principais do React

- **Componentes**: funções que retornam JSX
- **Estado**: dados que mudam ao longo do tempo
- **Hooks**: funções que adicionam comportamento aos componentes
- **Ciclo de vida**: montagem, atualização, desmontagem
- **Estado global**: dados compartilhados entre vários componentes

---

## 14. O que torna uma função um componente?

- Começa com letra maiúscula
- Retorna JSX
```jsx
function MeuComponente() {
  return <h1>Olá React</h1>
}
```

- `.jsx` permite usar HTML dentro do JS (JSX)

---

## 15. Principais hooks

- `useState`: armazena valores mutáveis
```jsx
const [contador, setContador] = useState(0)
```

- `useEffect`: executa efeitos colaterais
```jsx
useEffect(() => {
  fetchDados()
}, [])
```

- Hooks customizados: lógica reutilizável com base em outros hooks

---

## 16. SPA (Single Page Application)

- Aplicações que carregam uma única página HTML
- Navegação feita via JS, sem recarregar a página
- React re-renderiza partes da tela com base no estado

---

## 17. O que são hooks

- Hooks são funções especiais do React que permitem a você "ligar" recursos do React em componentes funcionais (como estado, ciclo de vida e contexto.

- Hooks "enganam" o React para que ele trate componentes funcionais como se fossem de classe) com estado, efeitos e mais.

- Eles são funções simples, reutilizáveis e fáceis de compor.

- Não podem ser usados fora de componentes React ou dentro de condições/loops (devem ser usados sempre na raiz do componente).

---

## 18. Entenda hooks
<img src="https://guide.sst.dev/assets/understanding-react-hooks/react-class-lifecycle-flochart.png" class="border"/>

---

## 19. Renderização de componentes

- Baseada em props e estado
- Re-renderiza ao mudar o estado
- **Renderização condicional**:
```jsx
{logado ? <Dashboard /> : <Login />}
```

---

## 20. Ciclo de renderização de uma aplicação JS pura

<img src="https://lh3.googleusercontent.com/pw/AP1GczPVgS2BjREJ0WQynab15mL4mes_lv6XhP9QFQGC_nyeSe_EGu0PWsogwTY4kD8z2N81zaC7TLZ7aoXX9h6qWwt35UPy-kUwgUAG6Doz6r8joPQ107Z-xQZK2oPLu26eN4Rt7rpNb92OXuhl3NwgdKqj4A=w1165-h583-s-no-gm?authuser=0" width="1000px"/>

---

## 21. Ciclo de renderização de uma aplicação React
<img src="https://lh3.googleusercontent.com/pw/AP1GczP2MsCfxBmIAl0yjbs9mYWGdVIVaqZA0eSUzrHOYc-nz7XR6Nt7BQY2oeDN-PZ0YR7tFOpyjq1WL4_lEpJU55gnvYHA_hroqKokTCBCBbiW_-fjMlWyiDiCG6C_gxDaOOQ5CqxtOAIadZpM_0EQamZYpw=w1295-h299-s-no-gm?authuser=0" width="100%"/>

---

## 22. Compilando React

- JSX não é compreendido nativamente pelo navegador
- O React Compiler transforma JSX em JS
- O navegador interpreta o bundle (conjunto de js e html) para gerar o DOM

---

## 23. Estrutura de um app React simples

```
my-app/
├── public/
├── src/
│   ├── App.jsx
│   ├── index.js
│   ├── components/
│   └── pages/
├── package.json
```

- `App.jsx`: componente principal
- `index.js`: ponto de entrada
- Separação por componentes e páginas

---

## 24. Build tools e frameworks

- Vite: Usado para inicializar projetos front-end com configurações de eficiência pré-definidas.
- Next: Next.js é um framework React com foco em performance, SEO e renderização no servidor (SSR).

---

# Obrigado!
### Dúvidas?