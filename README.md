# Site do Corretor de Imóveis - Mestre Alisson

Este projeto é um site dinâmico para corretor de imóveis integrado com Firebase, permitindo gerenciamento de conteúdo através de um painel administrativo.

## 🚀 Funcionalidades

- **Site Público**: Exibição dinâmica de imóveis em destaque e artigos do blog
- **Painel Administrativo**: Interface para gerenciar imóveis e blog posts
- **Autenticação**: Sistema de login seguro para acesso ao painel
- **Responsivo**: Design adaptável para desktop e mobile
- **Tempo Real**: Atualizações automáticas quando dados são modificados

## 📁 Estrutura do Projeto

```
site-corretor/
├── index.html              # Página principal do site
├── admin.html              # Painel administrativo
├── firebase-config.js      # Configuração do Firebase
├── firebase-config.json    # Chave de serviço do Firebase
├── firestore-rules.txt     # Regras de segurança do Firestore
└── README.md               # Este arquivo
```

## ⚙️ Configuração Inicial

### 1. Configuração do Firebase

O projeto já está configurado para usar o Firebase project: `alisson-x-corretor-de-imoveis`

#### Configurar Regras de Segurança:
1. Acesse o [Console do Firebase](https://console.firebase.google.com)
2. Selecione o projeto `alisson-x-corretor-de-imoveis`
3. Vá em **Firestore Database** > **Rules**
4. Copie e cole o conteúdo do arquivo `firestore-rules.txt`
5. Clique em **Publish**

#### Configurar Autenticação:
1. No console do Firebase, vá em **Authentication**
2. Clique na aba **Sign-in method**
3. Ative o provedor **Email/Password**
4. Vá na aba **Users** e adicione um usuário administrador

### 2. Estrutura do Banco de Dados

O Firestore deve ter as seguintes coleções:

#### Coleção `imoveis`:
```javascript
{
  titulo: "string",           // Ex: "Apartamento 3 Quartos, Jardim Botânico"
  descricao: "string",        // Descrição detalhada do imóvel
  preco: "string",           // Ex: "R$ 550.000"
  quartos: number,           // Número de quartos
  banheiros: number,         // Número de banheiros
  area: number,              // Área em m²
  localizacao: "string",     // Ex: "Jardim Botânico, Porto Alegre"
  imageURLs: ["string"],     // Array de URLs das imagens
  destaque: boolean          // true para aparecer na seção de destaques
}
```

#### Coleção `blogPosts`:
```javascript
{
  titulo: "string",          // Título do artigo
  conteudo: "string",        // Conteúdo completo do artigo
  autor: "string",           // Nome do autor (padrão: "Mestre Alisson")
  data: timestamp            // Data de criação (automática)
}
```

## 🖥️ Como Usar

### Site Público (index.html)
- Acesse `index.html` para ver o site público
- Os imóveis marcados como "destaque" aparecerão na seção principal
- Os artigos do blog são exibidos automaticamente
- O site atualiza em tempo real quando dados são modificados

### Painel Administrativo (admin.html)
1. Acesse `admin.html`
2. Faça login com as credenciais configuradas no Firebase Authentication
3. Use as abas para alternar entre gerenciamento de imóveis e blog
4. Clique em "Adicionar" para criar novos itens
5. Use os botões "Editar" e "Excluir" para gerenciar itens existentes

## 🌐 Deploy

### Netlify (Recomendado)
1. Faça upload dos arquivos para um repositório GitHub
2. Conecte o repositório ao Netlify
3. Configure o build:
   - Build command: (deixe vazio)
   - Publish directory: `/`
4. O site será automaticamente deployado

### GitHub Pages
1. Faça upload dos arquivos para um repositório GitHub
2. Vá em Settings > Pages
3. Selecione a branch main como source
4. O site estará disponível em `https://username.github.io/repository-name`

## 🔧 Personalização

### Alterar Cores e Estilo
- O projeto usa Tailwind CSS via CDN
- As cores principais são da paleta `teal` (verde-azulado)
- Para personalizar, edite as classes CSS nos arquivos HTML

### Adicionar Funcionalidades
- **Busca**: Implemente filtros na função de busca do `index.html`
- **Formulário de Contato**: Adicione integração com Firestore para salvar mensagens
- **Upload de Imagens**: Integre com Firebase Storage para upload direto de imagens
- **SEO**: Adicione meta tags dinâmicas baseadas no conteúdo

## 📱 Responsividade

O site é totalmente responsivo e funciona bem em:
- Desktop (1024px+)
- Tablet (768px - 1023px)
- Mobile (320px - 767px)

## 🔒 Segurança

- Apenas usuários autenticados podem acessar o painel administrativo
- As regras do Firestore protegem contra acesso não autorizado
- Dados públicos (imóveis e blog) são acessíveis para leitura por todos

## 🆘 Solução de Problemas

### Site não carrega dados:
1. Verifique se as regras do Firestore estão configuradas corretamente
2. Confirme se o projeto Firebase está ativo
3. Verifique o console do navegador para erros

### Não consegue fazer login no admin:
1. Verifique se o usuário foi criado no Firebase Authentication
2. Confirme se o provedor Email/Password está ativo
3. Verifique se as credenciais estão corretas

### Imóveis não aparecem no site:
1. Confirme se os imóveis têm a propriedade `destaque: true`
2. Verifique se os dados estão salvos corretamente no Firestore
3. Recarregue a página para forçar atualização

## 📞 Suporte

Para dúvidas ou problemas, entre em contato com o desenvolvedor ou consulte a documentação do Firebase:
- [Documentação do Firestore](https://firebase.google.com/docs/firestore)
- [Documentação do Firebase Auth](https://firebase.google.com/docs/auth)

---

**Desenvolvido para Mestre Alisson - Corretor de Imóveis**

