# Como ligar as confirmações à Planilha Google

As confirmações do formulário vão para uma Planilha Google, e a página `/confirmados` lê os dados de lá.

## 1. Colar o código na planilha
1. Abra a planilha no Google Planilhas.
2. Vá em **Extensões > Apps Script**.
3. Apague o que estiver no editor e cole todo o conteúdo do arquivo `google-apps-script/Code.gs`.
4. Na linha `const SENHA = '...'`, deixe a senha que vocês vão usar na página `/confirmados`.
5. Clique no ícone de disquete (**Salvar**).

## 2. Publicar como App da Web
1. Clique em **Implantar > Nova implantação**.
2. Na engrenagem ao lado de "Selecionar tipo", escolha **App da Web**.
3. Preencha assim:
   - **Executar como:** Eu
   - **Quem pode acessar:** Qualquer pessoa
4. Clique em **Implantar** e depois em **Autorizar acesso**. Escolha a sua conta e, se aparecer "O Google não verificou este app", clique em **Avançado > Acessar (não seguro)**. O aviso aparece porque o script é seu, e é normal.
5. Copie a **URL do App da Web**, a que termina em `/exec`.

## 3. Colar a URL no site
Abra o arquivo `config.js` e cole a URL entre as aspas:

```js
SCRIPT_URL: 'https://script.google.com/macros/s/XXXXXXXX/exec',
```

Pronto. Os envios do formulário passam a cair na aba **Confirmações** da planilha, e a página `/confirmados` mostra a lista depois de digitar a senha.

## Se mudar o código depois
Vá em **Implantar > Gerenciar implantações**, clique no lápis, escolha **Versão: Nova versão** e clique em **Implantar**. Assim a URL continua a mesma.
