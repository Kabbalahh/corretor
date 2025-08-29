# Instruções de Deploy - Site Corretor de Imóveis

## 🚀 Deploy no GitHub + Netlify (Recomendado)

### Passo 1: Preparar o Repositório GitHub

1. **Criar repositório no GitHub:**
   - Acesse [GitHub](https://github.com) e faça login
   - Clique em "New repository"
   - Nome sugerido: `site-corretor-imoveis`
   - Marque como "Public" ou "Private" conforme preferir
   - NÃO inicialize com README (já temos os arquivos)

2. **Fazer upload dos arquivos:**
   ```bash
   # No terminal, dentro da pasta do projeto:
   git init
   git add .
   git commit -m "Initial commit - Site corretor de imóveis"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/site-corretor-imoveis.git
   git push -u origin main
   ```

### Passo 2: Deploy no Netlify

1. **Conectar ao Netlify:**
   - Acesse [Netlify](https://netlify.com) e faça login
   - Clique em "New site from Git"
   - Escolha "GitHub" como provedor
   - Selecione o repositório `site-corretor-imoveis`

2. **Configurar o deploy:**
   - **Branch to deploy:** `main`
   - **Build command:** (deixe vazio)
   - **Publish directory:** `/` (raiz)
   - Clique em "Deploy site"

3. **Configurar domínio personalizado (opcional):**
   - Vá em "Site settings" > "Domain management"
   - Clique em "Add custom domain"
   - Digite seu domínio (ex: `mestrealisson.com.br`)
   - Configure os DNS conforme instruções do Netlify

### Passo 3: Configurar Variáveis de Ambiente (se necessário)

Se você quiser ocultar as configurações do Firebase:

1. No Netlify, vá em "Site settings" > "Environment variables"
2. Adicione as seguintes variáveis:
   - `FIREBASE_API_KEY`: sua chave da API
   - `FIREBASE_AUTH_DOMAIN`: seu domínio de auth
   - `FIREBASE_PROJECT_ID`: ID do projeto
   - etc.

3. Modifique o arquivo `index.html` e `admin.html` para usar essas variáveis

## 🔧 Deploy Alternativo - GitHub Pages

### Configuração GitHub Pages:

1. **No repositório GitHub:**
   - Vá em "Settings" > "Pages"
   - Em "Source", selecione "Deploy from a branch"
   - Escolha a branch `main` e pasta `/ (root)`
   - Clique em "Save"

2. **Acessar o site:**
   - O site estará disponível em: `https://SEU_USUARIO.github.io/site-corretor-imoveis`
   - Pode levar alguns minutos para ficar disponível

## 📋 Checklist Pré-Deploy

Antes de fazer o deploy, verifique:

- [ ] Arquivo `firebase-config.json` está no `.gitignore` (segurança)
- [ ] Configurações do Firebase estão corretas nos arquivos HTML
- [ ] Regras do Firestore foram aplicadas no console do Firebase
- [ ] Usuário administrador foi criado no Firebase Authentication
- [ ] Site foi testado localmente e está funcionando
- [ ] Todas as URLs de imagens estão funcionando
- [ ] Responsividade foi testada em diferentes tamanhos de tela

## 🔒 Configurações de Segurança Pós-Deploy

### 1. Configurar Domínios Autorizados no Firebase:

1. Acesse o [Console do Firebase](https://console.firebase.google.com)
2. Selecione seu projeto
3. Vá em "Authentication" > "Settings" > "Authorized domains"
4. Adicione seu domínio do Netlify (ex: `amazing-site-123456.netlify.app`)
5. Se tiver domínio personalizado, adicione também

### 2. Atualizar CORS (se necessário):

Se houver problemas de CORS, configure no Firebase:
1. Vá em "Firestore Database" > "Rules"
2. Verifique se as regras permitem acesso do seu domínio

## 🚨 Solução de Problemas Comuns

### Site não carrega no deploy:
- Verifique se todos os arquivos foram enviados corretamente
- Confirme se o arquivo `index.html` está na raiz
- Verifique os logs de deploy no Netlify

### Firebase não conecta:
- Confirme se o domínio está autorizado no Firebase
- Verifique se as configurações do Firebase estão corretas
- Teste as regras do Firestore

### Painel admin não funciona:
- Verifique se o usuário foi criado no Firebase Authentication
- Confirme se o provedor Email/Password está ativo
- Teste o login com as credenciais corretas

## 📞 Suporte

Para problemas específicos:
- **Netlify:** [Documentação oficial](https://docs.netlify.com)
- **GitHub Pages:** [Documentação oficial](https://docs.github.com/pages)
- **Firebase:** [Documentação oficial](https://firebase.google.com/docs)

---

**Boa sorte com o deploy! 🚀**

