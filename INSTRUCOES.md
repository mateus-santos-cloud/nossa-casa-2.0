# 📋 Guia de Configuração — Nossa Casa

Siga cada passo com calma. Não precisa instalar nada no computador.

---

## PASSO 1 — Criar conta no Firebase (Google)

1. Acesse: **https://firebase.google.com**
2. Clique em **"Começar"** ou **"Get started"**
3. Faça login com sua conta Google
4. Clique em **"Criar um projeto"**
5. Nome do projeto: **nossa-casa** (ou qualquer nome)
6. Desative o Google Analytics (não precisa)
7. Clique em **"Criar projeto"**
8. Aguarde e clique em **"Continuar"**

---

## PASSO 2 — Ativar o banco de dados (Firestore)

1. No menu lateral esquerdo, clique em **"Firestore Database"**
2. Clique em **"Criar banco de dados"**
3. Selecione **"Iniciar no modo de produção"**
4. Escolha a região: **southamerica-east1 (São Paulo)** ← importante!
5. Clique em **"Ativar"**

### Configurar as regras de segurança:
1. Clique na aba **"Regras"**
2. Apague o que estiver lá e cole o seguinte:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

3. Clique em **"Publicar"**

---

## PASSO 3 — Ativar o login (Authentication)

1. No menu lateral, clique em **"Authentication"**
2. Clique em **"Começar"**
3. Na aba **"Sign-in method"**, clique em **"E-mail/senha"**
4. Ative a primeira opção (E-mail/senha)
5. Clique em **"Salvar"**

---

## PASSO 4 — Pegar as configurações do Firebase

1. Clique no ícone de engrenagem ⚙️ ao lado de "Visão geral do projeto"
2. Clique em **"Configurações do projeto"**
3. Role para baixo até a seção **"Seus aplicativos"**
4. Clique no ícone **"</>"** (Web)
5. Nome do app: **nossa-casa**
6. NÃO marque "Firebase Hosting"
7. Clique em **"Registrar app"**
8. Você verá um bloco de código assim:

```javascript
const firebaseConfig = {
  apiKey: "AIza...",
  authDomain: "nome-do-projeto.firebaseapp.com",
  projectId: "nome-do-projeto",
  storageBucket: "nome-do-projeto.appspot.com",
  messagingSenderId: "12345...",
  appId: "1:12345..."
};
```

**Copie todos esses valores — você vai precisar no próximo passo.**

---

## PASSO 5 — Colocar as configurações no app

1. Abra o arquivo **index.html** que você recebeu
2. Localize a seção comentada `// INSTRUÇÃO: Substitua...`
3. Substitua os valores conforme o que você copiou:

```javascript
const firebaseConfig = {
  apiKey: "COLE_AQUI_SEU_API_KEY",
  authDomain: "COLE_AQUI_SEU_AUTH_DOMAIN",
  projectId: "COLE_AQUI_SEU_PROJECT_ID",
  storageBucket: "COLE_AQUI_SEU_STORAGE_BUCKET",
  messagingSenderId: "COLE_AQUI_SEU_MESSAGING_SENDER_ID",
  appId: "COLE_AQUI_SEU_APP_ID"
};
```

4. Salve o arquivo

---

## PASSO 6 — Publicar no Vercel (subir o app na internet)

1. Acesse: **https://vercel.com**
2. Clique em **"Sign Up"** e crie conta com seu e-mail (gratuito)
3. No painel, clique em **"Add New Project"**
4. Clique em **"Browse"** ou arraste a **pasta "nossa-casa"** para a área indicada
5. O Vercel vai detectar automaticamente que é um site estático
6. Clique em **"Deploy"**
7. Aguarde ~1 minuto
8. Você receberá um link tipo: **nossa-casa-abc123.vercel.app**

**Pronto! Esse é o link do app de vocês.**

---

## PASSO 7 — Instalar no celular

### Android:
1. Abra o link no Chrome
2. Toque no menu (3 pontinhos)
3. Toque em **"Adicionar à tela inicial"**
4. Confirme

### iPhone (iOS):
1. Abra o link no Safari (obrigatório ser Safari)
2. Toque no botão de compartilhar (quadrado com seta)
3. Toque em **"Adicionar à Tela de Início"**
4. Confirme

---

## PASSO 8 — Criar as contas de vocês dois

1. Abra o app pelo link
2. Toque em **"Cadastrar"**
3. Coloque seu nome, e-mail e senha
4. Repita o processo no celular da sua esposa com o e-mail dela

**Os dois vão ver os mesmos dados em tempo real!**

---

## ❓ Dúvidas frequentes

**O app é gratuito para sempre?**
Para o uso de vocês dois, sim. O Firebase tem limite de 50.000 leituras/dia no plano gratuito, que é bem mais do que vocês vão usar.

**E se eu esquecer a senha?**
Por enquanto a recuperação de senha é manual. Me avise que posso adicionar essa funcionalidade.

**Posso usar sem internet?**
Não no momento. O app precisa de internet para sincronizar os dados.

---

## 📞 Precisa de ajuda?

Se travar em qualquer passo, me mande uma mensagem descrevendo onde parou que te ajudo!
