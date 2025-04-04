# Aula 01 - Compiladores JavaScript

## Introdução

Os compiladores JavaScript desempenham um papel fundamental no processo de transformar código escrito em JavaScript em uma versão que pode ser executada de forma eficiente por navegadores ou outras plataformas. Nesta aula, vamos explorar os conceitos básicos de **Transpilação**, **Parser**, **Transformer** e **Generator**.

---

## Conceitos Principais

### **1. Transpilação**

A **transpilação** é o processo de converter código de uma linguagem para outra versão ou linguagem semelhante. No caso do JavaScript, a transpilação é amplamente utilizada para transformar código moderno (ES6 ou superior) em versões mais antigas que sejam compatíveis com navegadores antigos.

- Ferramentas populares: Babel, TypeScript.

---

### **2. Parser**

O **parser** é a etapa responsável por analisar o código-fonte e transformá-lo em uma estrutura de dados intermediária chamada **Árvore de Sintaxe Abstrata (AST)**. Essa estrutura é essencial para que o compilador entenda a lógica do programa.

- **Entrada:** Código-fonte em JavaScript.
- **Saída:** Árvore de Sintaxe Abstrata (AST).

---

### **3. Transformer**

O **transformer** é a etapa onde a AST é manipulada ou transformada para atender a diferentes necessidades. Isso pode incluir otimizações, adição de novos recursos ou compatibilidade com padrões mais antigos.

- **Entrada:** AST gerada pelo parser.
- **Saída:** AST modificada.

---

### **4. Generator**

O **generator** é a etapa final no processo de compilação. Ele converte a AST (original ou transformada) de volta para código JavaScript que pode ser executado.

- **Entrada:** AST.
- **Saída:** Código JavaScript transformado.

---

## Fluxo de Funcionamento de um Compilador JavaScript

1. **Parser:** Converte o código em uma AST.
2. **Transformer:** Modifica a AST conforme necessário.
3. **Generator:** Transforma a AST de volta para código JavaScript transpilado.

## Exemplos no Mundo Real

- **Babel:** Realiza transpilação para transformar ES6+ em ES5.
- **TypeScript:** Transpila código TypeScript para JavaScript.

# Aula 02 - Instalando o Babel

## Objetivo

Nesta aula, você aprenderá como instalar o Babel, uma ferramenta poderosa para transpilação de JavaScript moderno para versões compatíveis com navegadores mais antigos.

## Instalação do Babel

Para instalar o Babel no seu projeto, execute o seguinte comando no terminal:

```bash
npm install --save-dev @babel/core @babel/cli @babel/preset-env

```

### **Explicação dos pacotes instalados**:

1. **`@babel/core`**: O núcleo do Babel, responsável por realizar a transpilação.
2. **`@babel/cli`**: Interface de linha de comando do Babel, usada para executar os processos de transpilação diretamente pelo terminal.
3. **`@babel/preset-env`**: Preset que configura o Babel para transformar o JavaScript moderno (ES6+).

---

## Como Usar o Babel

1. Certifique-se de que os pacotes foram instalados corretamente.
2. Configure o Babel criando um arquivo chamado `.babelrc` no diretório raiz do seu projeto com o seguinte conteúdo:

```json
{
  "presets": ["@babel/preset-env"]
}
```

1. Use o Babel para transpilação:

   ```bash
   npx babel arquivo.js --out-file arquivo-transpilado.js

   ```

# Aula 03 - Configurando e Utilizando o Babel

## Objetivo

Nesta aula, vamos aprender a configurar e utilizar o Babel para transpilação de código JavaScript moderno.

## Configuração do Babel

### 1. Instalando os pacotes necessários

Certifique-se de que os pacotes do Babel estão instalados. Caso ainda não tenha feito, execute:

```bash
npm install --save-dev @babel/core @babel/cli @babel/preset-env

```

---

### 2. Criando a configuração do Babel

Crie um arquivo chamado `babel.config.js` na raiz do seu projeto e adicione o seguinte conteúdo:

```jsx
const presets = ['@babel/preset-env'];

module.exports = { presets };
```

Essa configuração define o preset `@babel/preset-env`, que permite transpilação de JavaScript moderno.

---

## Executando o Babel Manualmente

Para transpirar um arquivo específico, execute o seguinte comando no terminal:

```bash
./node_modules/.bin/babel src/main.js --out-dir dist

```

- **`src/main.js`**: Arquivo de entrada com o código fonte.
- **`dist`**: Diretório de saída onde o código transpilado será salvo.

# Aula 04 - Configurando Scripts no `package.json`

Adicione um script para facilitar a execução no arquivo `package.json`:

```json
"scripts": {
  "build": "babel src --out-dir dist"
}

```

Com essa configuração, você pode executar o Babel utilizando o comando:

```bash
npm run build

```

# Aula 05 - Utilizando o Arquivo Compilado

## Objetivo

Nesta aula, vamos aprender como utilizar o arquivo JavaScript compilado em uma página HTML para executar a lógica implementada.

## Estrutura HTML

Crie um arquivo HTML, como `index.html`, e insira o seguinte conteúdo:

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <script src="dist/main.js"></script>
  </body>
</html>
```

### Explicação:

- **`<!doctype html>`:** Declaração que informa ao navegador que o documento está no formato HTML5.
- **`<meta charset="UTF-8" />`:** Configuração de codificação de caracteres para o formato UTF-8.
- **`<script src="dist/main.js"></script>`:** Linka o arquivo JavaScript compilado, permitindo que as funcionalidades sejam executadas.

## Arquivo Compilado - `main.js`

Crie o arquivo `main.js` no diretório `dist` com o seguinte código:

```jsx
class User {
  constructor({ email }) {
    this.email = email;
  }

  sendMessage() {
    console.log(`Mensagem enviada para: ${this.email}`);
  }
}

let user = new User({ email: 'email@pedro.com' });
user.sendMessage();
```

### Explicação:

- **`class User`:** Define a classe `User` com suas propriedades e métodos.
- **`constructor({ email })`:** Inicializa o objeto com o atributo `email`.
- **`sendMessage()`:** Método que exibe uma mensagem no console com o email do usuário.
- **Criação de instância:** Uma instância da classe `User` é criada e o método `sendMessage()` é chamado.

## Como Testar

1. Certifique-se de que o arquivo compilado (`main.js`) está na pasta `dist` do projeto.
2. Abra o arquivo HTML (`index.html`) em um navegador.
3. Verifique o console do navegador (tecla F12) para visualizar a mensagem exibida:

   ```
   Mensagem enviada para: email@pedro.com

   ```
