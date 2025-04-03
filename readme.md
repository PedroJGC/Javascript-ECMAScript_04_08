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

---

## Exemplos no Mundo Real

- **Babel:** Realiza transpilação para transformar ES6+ em ES5.
- **TypeScript:** Transpila código TypeScript para JavaScript.
