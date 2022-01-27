# Aula 01 - Matrix Chat: Criando o nosso projeto | Imersão React 4

> ## **Configuração manual de um projeto Next.js**

1. Iniciar um projeto Node:

    ```shell
    $ npm init -y
    ```

2. Instalar os pacotes `next`, `react` e `react-dom` com NPM:

    ```shell
    $ npm i next react react-dom
    ```

3. Adicionar os scripts no arquivo `package.json`, afim de facilitar o desenvolvimento da aplicação:

    ```json
    "scripts": {
      "dev": "next dev",
      "build": "next build",
      "start": "next start",
      "lint": "next lint"
    }
    ```

3. Criar o arquivo `pages/index.js` e adicionar o seguinte trecho de código:

    ```js
    function HomePage() {
      return <div>Welcome to Next.js!</div>
    }

    export default HomePage
    ```

4. Iniciar a aplicação em mode de desenvolvimento:

    ```shell
    $ npm run dev
    ```

> ## **`<style jsx>`**

### **Definição**

A tag `<style jsx></style>` É uma tag JSX específica do framework Next.js com a função de definir estilos específicos para cada componente React.

Com o Next.js é possível definir o "HTML", o "JavaScript" e o "CSS" em um único arquivo.

### **Sintaxe**

```html
<style jsx>{`
  /* Estilo */
`}</style>
```

**IMPORTANTE**: a tag `style` e o atributo `jsx` são exclusivas do Next.js

### **Exemplo**

```js
function Title(props) {
  return (
    <>
      <h1>{props.children}</h1>

      <style jsx>{`
        h1 {
          color: red;
        }
      `}</style>
    </>
  );
}
```

### **Template Strings no JSX**

```js
function Title(props) {
  const Tag = props.tag;

  return (
    <>
      <Tag>{props.children}</Tag>

      <style jsx>{`
        ${Tag} {
          color: red;
          font-size: 24px;
          font-weight: 600;
        }
      `}</style>
    </>
  );
}
```

> ## **Estilo global**

### **Definição**

No contexto do CSS no JSX através do Next.js, é utilizado, por convenção, a tag `<GlobalStyle>` que é responsável por aplicar os estilos globais da aplicação, como a fonte, reset do CSS

### **Exemplo**

```js
function GlobalStyle() {
  return (
    <style global jsx>{`
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        list-style: none;
      }
    `}</style>
  );
}

function HomePage() {
  return (
    <div>
      <GlobalStyle />
      <Title tag="h2">Boas vindas de volta!</Title>
    </div>
  );
}
```

> ## **Coolors**

É uma site para gerar paletas de cores.

1. Entrar no site: https://coolors.co/

2. Clicar no botão `Start the generator!`

3. (OPCIONAL) Para gerar uma nova paleta de cores, basta apertar a tecla de espaço

4. Para ver os tons de uma cor na paleta, clicar no ícone `view shades`

> ## Skynexui

### **Configuração**

1. Instalar o pacote `skynexui/components` com NPM:

    ```shell
    $ npm install @skynexui/components
    ```

2. **OBS**: Erro durante a instalação do pacote:

    **Problema**:

    ```
    npm ERR! code ERESOLVE
    npm ERR! ERESOLVE could not resolve
    npm ERR! 
    npm ERR! While resolving: aluracord@1.0.0
    npm ERR! Found: styled-jsx@5.0.0-beta.6
    npm ERR! node_modules/styled-jsx
    npm ERR!   styled-jsx@"5.0.0-beta.6" from next@12.0.8
    npm ERR!   node_modules/next
    npm ERR!     next@"^12.0.8" from the root project
    npm ERR! 
    npm ERR! Could not resolve dependency:
    npm ERR! @skynexui/components@"*" from the root project
    npm ERR! 
    npm ERR! Conflicting peer dependency: styled-jsx@5.0.0
    npm ERR! node_modules/styled-jsx
    npm ERR!   peer styled-jsx@">= 4.x.x || 5.x.x" from @skynexui/components@1.24.2
    npm ERR!   node_modules/@skynexui/components
    npm ERR!     @skynexui/components@"*" from the root project
    npm ERR! 
    npm ERR! Fix the upstream dependency conflict, or retry
    npm ERR! this command with --force, or --legacy-peer-deps
    npm ERR! to accept an incorrect (and potentially broken) dependency resolution.
    npm ERR! 
    npm ERR! See /home/gabriel/.npm/eresolve-report.txt for a full report.

    npm ERR! A complete log of this run can be found in:
    npm ERR!     /home/gabriel/.npm/_logs/2022-01-27T19_46_41_369Z-debug.log
    ```

    **Solução**:

    ```shell
    $ npm install @skynexui/components --force
    ```