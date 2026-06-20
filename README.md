# 🍦 Dindin Gourmet — Site Oficial

Site institucional e de vendas para a marca **Dindin Gourmet**, desenvolvido por **VR Web Solutions**.

---

## 🚀 Funcionalidades

- Cardápio dinâmico carregado do banco de dados em tempo real
- Pedidos diretos via **WhatsApp** com mensagem automática
- Sistema de **avaliações com estrelas** dos clientes
- **Painel administrativo** completo para gerenciar o negócio
- **Controle de caixa** com entradas, saídas e saldo
- Design responsivo para mobile e desktop

---

## 🛠 Tecnologias

| Tecnologia | Uso |
|---|---|
| HTML5 + CSS3 | Estrutura e estilo |
| Tailwind CSS v4 | Estilização utilitária |
| JavaScript (ES6+) | Lógica e interatividade |
| Supabase | Banco de dados e API |
| Vercel | Hospedagem |

---

## 📁 Estrutura de Arquivos

```
/
├── index.html       # Página pública do cardápio
├── admin.html       # Painel administrativo
└── README.md        # Este arquivo
```

---

## 🗄️ Tabelas no Supabase

### `produtos`
| Campo | Tipo | Descrição |
|---|---|---|
| id | uuid | Chave primária |
| nome | text | Nome do sabor |
| descricao | text | Descrição do produto |
| preco | numeric | Preço em reais |
| disponivel | boolean | Visível no cardápio? |
| imagem_url | text | Link da foto |
| created_at | timestamptz | Data de criação |

### `avaliacoes`
| Campo | Tipo | Descrição |
|---|---|---|
| id | uuid | Chave primária |
| nome | text | Nome do cliente |
| estrelas | integer | Nota de 1 a 5 |
| comentario | text | Comentário |
| created_at | timestamptz | Data de criação |

### `caixa`
| Campo | Tipo | Descrição |
|---|---|---|
| id | uuid | Chave primária |
| descricao | text | Motivo da movimentação |
| valor | numeric | Valor em reais |
| tipo | text | `entrada` ou `saida` |
| created_at | timestamptz | Data de criação |

---

## ⚙️ Como configurar

1. Crie um projeto em [supabase.com](https://supabase.com)
2. Rode o SQL de criação das tabelas no **SQL Editor**
3. Copie a **URL** e a **Chave publicável** do projeto
4. Substitua no `index.html` e `admin.html`:
```js
const SUPABASE_URL = "https://SEU-PROJETO.supabase.co";
const SUPABASE_KEY = "sua-chave-publica";
```

---

## 🌐 Como hospedar no Vercel

1. Acesse [vercel.com](https://vercel.com) e crie uma conta
2. Clique em **Add New Project**
3. Arraste os arquivos ou conecte ao GitHub
4. Clique em **Deploy** — pronto!

---

## 📞 Contato

**Dindin Gourmet** — Sobral, CE  
📱 (88) 99272-1857  
🛵 Entregas exclusivas em Sobral - CE

---

Desenvolvido com 💛 por **VR Web Solutions**
