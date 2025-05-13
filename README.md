---
marp: true
theme: default
paginate: true
author: Marcelo Oliveira & Bernardo Mendes
footer: 'Minicurso Frontend Moderno'
transition: slide
---

<style>
  :root {
    --primary: rgb(202, 158, 12);
    --primary-hover: rgb(255, 234, 0);
    --secondary: rgb(255, 242, 123);
    --bg-dark: #121212;
    --bg-medium: #2a2a2a;
    --text-light: rgb(212, 212, 212);
    --text-muted: #bbbbbb;
    --code-bg: rgba(12, 12, 12, 0.9);
    
    --padding-md: 1.2em;
    --padding-lg: 1.5em;
    --gap-md: 20px;
    --gap-lg: 30px;
    --radius-sm: 8px;
    --radius-md: 10px;
    --radius-lg: 30px;
    
    --transition-fast: 0.3s;
    --transition-normal: 0.5s;
    --transition-slow: 0.8s;
    
    --shadow-sm: 0 4px 8px rgba(0,0,0,0.2);
    --shadow-md: 0 4px 12px rgba(0,0,0,0.3);
    --hover-scale: 1.05;
    --hover-scale-lg: 1.2;
  }

  section {
    background-image: linear-gradient(to bottom right, var(--bg-dark), var(--bg-medium));
    color: var(--text-light);
    font-family: 'Segoe UI', Roboto, sans-serif;
  }

  h1, h2, h3 {
    color: var(--primary);
    margin-bottom: 0.8em;
  }

  h2 {
    transition: var(--transition-normal);
  }

  h2:hover {
    scale: var(--hover-scale);
    color: var(--primary-hover);
    transition: var(--transition-fast);
    cursor: pointer;
  }

  header {
    color: var(--text-muted);
    font-size: 0.9em;
  }

  pre {
    background-color: var(--code-bg) !important;
    padding: var(--padding-md);
    border-radius: var(--radius-sm);
    color: var(--text-light);
    font-size: 0.85em;
    box-shadow: var(--shadow-md);
    border-left: 4px solid var(--primary);
    overflow-x: auto;
    transition: var(--transition-normal);
  }
  
  pre:hover {
    scale: var(--hover-scale);
    transition: var(--transition-normal);
  }
  
  pre > code:hover {
    background-color: transparent !important;
    color: var(--text-light);
  }
  
  code {
    font-family: 'Fira Code', monospace !important;
    padding: 0.2em 0.4em;
    border-radius: var(--radius-md);
    transition: var(--transition-normal);
  }
  
  code:hover {
    background-color: var(--primary);
    color: var(--text-light);
    transition: var(--transition-normal);
  }

  .icon-row {
    display: flex;
    gap: var(--gap-lg);
    margin: 2em 0;
  }
  
  .icon {
    transition: transform var(--transition-fast);
  }

  img {    
    transition: transform var(--transition-fast);
  }

  img:hover {
    transform: scale(var(--hover-scale-lg));
    transition: transform var(--transition-fast);
  }

  li {    
    transition: transform var(--transition-fast);
  }

  li:hover {
    transform: scale(var(--hover-scale));
    cursor: pointer;
    transition: transform var(--transition-fast);
    color: var(--primary);
  }
  
  img.border {
    border-radius: var(--radius-lg);
  }
  
  .icon:hover {
    transform: scale(var(--hover-scale-lg));
  }
  
  .highlight {
    color: var(--primary);
    font-weight: bold;
  }
  
  .two-columns {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--gap-md);
  }
  
  .card {
    background: rgba(255,255,255,0.1);
    padding: var(--padding-lg);
    border-radius: var(--radius-md);
    box-shadow: var(--shadow-sm);
  }
</style>


<div class="icon-row">
  <img class="icon" width="80" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" />
  <img class="icon" width="80" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" />
  <img class="icon" width="80" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg" />
</div>

# Frontend Moderno com Javascript
### Parte I
---

## Ministrantes

<div class="two-columns">

<div class="card">
Marcelo Oliveira<br/>
Engenheiro de Software <br/>@ Nocorp Applied

- [![w:20](https://upload.wikimedia.org/wikipedia/commons/thumb/8/81/LinkedIn_icon.svg/2048px-LinkedIn_icon.svg.png) /marcelooliveiradev](https://www.linkedin.com/in/marcelooliveiradev)
</div>

<div class="card">
Bernardo Mendes<br/>
Engenheiro de Software <br/>@ Blips Ativos

- [![w:20](https://upload.wikimedia.org/wikipedia/commons/thumb/8/81/LinkedIn_icon.svg/2048px-LinkedIn_icon.svg.png) /bernardomennndes](https://www.linkedin.com/in/bernardomennndes)
</div>

</div>

---

## Agenda do Minicurso

1. Fundamentos do JavaScript Moderno
2. React: Conceitos Essenciais
3. Gerenciamento de Estado
4. Boas Práticas e Padrões
5. Ferramentas do Ecossistema
6. Projeto Prático

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

## 19. Ciclo do React
Ciclo

---

## 20. Bibliotecas importantes

- **React Router**: navegação SPA
- **Axios**: requisições HTTP
- **ESLint**: verificação de padrões e erros de código

---

## 21. Renderização de componentes

- Baseada em props e estado
- Re-renderiza ao mudar o estado
- **Renderização condicional**:
```jsx
{logado ? <Dashboard /> : <Login />}
```

---

## 22. Compilando React

- Transpila JSX para JS puro com Babel
- Empacota arquivos com Webpack/Vite
- `npm run build` gera versão otimizada para produção

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

# Obrigado!
### Dúvidas?