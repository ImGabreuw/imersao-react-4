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