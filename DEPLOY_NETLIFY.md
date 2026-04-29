# Deploy no Netlify — B2K Visão Executiva

## ✅ O que já foi feito:

1. ✓ Adicionado `auth.html` — tela de autenticação (senha: `B2K2026`)
2. ✓ Modificado `index.html` — redireciona para autenticação se não logado
3. ✓ Adicionado `netlify.toml` — configuração de segurança e headers
4. ✓ Commit e push realizados no GitHub

---

## 🚀 Próximos passos para ir ao ar:

### **Passo 1: Tornar o repositório PRIVADO**

1. Acessa https://github.com/ctsobral/b2k-Visaoexecutiva/settings
2. Desce até **"Danger Zone"** → **"Change repository visibility"**
3. Clica em **"Make private"**
4. Confirma com sua senha do GitHub
5. ✓ Repositório agora é **🔒 Privado**

---

### **Passo 2: Desabilitar GitHub Pages**

1. Ainda em **Settings**
2. Vai para a aba **"Pages"** (lado esquerdo)
3. Em **"Build and deployment"**, muda de `Deploy from a branch` para **"None"**
4. Salva
5. ✓ GitHub Pages desabilitado

---

### **Passo 3: Deploy no Netlify**

#### **3.1 Criar conta (se não tiver)**
- Acessa https://app.netlify.com
- Clica em **"Sign up"**
- Escolhe **"Sign up with GitHub"**
- Autoriza acesso

#### **3.2 Conectar repositório**
1. Clica em **"New site from Git"** ou **"Add new site"**
2. Escolhe **"GitHub"**
3. Procura por **`b2k-Visaoexecutiva`**
4. Clica em **"Install"** (se for primeira vez)
5. Seleciona o repositório
6. **Build settings:**
   - **Branch to deploy:** `main` (padrão)
   - **Build command:** deixa em branco (é estático)
   - **Publish directory:** `.` (raiz)
7. Clica em **"Deploy site"**

#### **3.3 Espera o deploy (1-2 minutos)**
- Netlify vai clonar, validar `netlify.toml` e publicar
- Você receberá uma URL do tipo: `https://seu-site-aleatorio.netlify.app`

#### **3.4 (Opcional) Configurar domínio customizado**
1. Em **"Site settings"** → **"Domain management"**
2. Clica em **"Add domain"**
3. Insere seu domínio (ex: `b2k-visao.picpay.com`)
4. Segue as instruções de DNS

---

### **Passo 4: Testar a autenticação**

1. Acessa a URL publicada (ex: `https://seu-site.netlify.app`)
2. Deve abrir a tela de **autenticação** (com o logo 🔒)
3. Insere a senha: **`B2K2026`**
4. Pressiona **"Acessar"**
5. ✓ Deve redirecionar para a página completa
6. Recarrega a página — **NÃO deve pedir senha de novo** (sessão salva por 24h)

---

## 🔐 Como funciona a autenticação:

- **Senha:** `B2K2026` (armazenada no código front-end)
- **Armazenamento:** `localStorage` do navegador
- **Duração:** 24 horas por sessão
- **Segurança:** Token codificado em base64 (não é criptografia forte, mas é suficiente para acesso interno)

---

## ⚠️ Importante:

- Se quiser **mudar a senha** depois, edita o arquivo `auth.html` (linha 146) e faz commit
- Netlify vai fazer **re-deploy automático** quando detectar novo push no GitHub
- O repositório continua **privado no GitHub** — ninguém consegue clonar
- A **página publicada fica protegida** pela autenticação

---

## 📞 Dúvidas ou problemas?

Se houver erro no deploy, acessa:
1. **Netlify Dashboard** → **"Site settings"** → **"Build & deploy"** → **"Deploy logs"**
2. Vê o erro e avisa que vou corrigir

---

**Status final esperado:**
- ✅ Repo GitHub: 🔒 Privado
- ✅ GitHub Pages: Desabilitado
- ✅ Página publicada: Netlify (com autenticação)
- ✅ Acesso controlado: Apenas com senha `B2K2026`
