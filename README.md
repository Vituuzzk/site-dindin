# 🍦 Dindin Gourmet — Site Oficial

Site institucional e de vendas para a marca **Dindin Gourmet**, desenvolvido por **VR Web Solutions**.

---

## 🚀 Funcionalidades

- Cardápio dinâmico carregado do banco de dados em tempo real
- Pedidos diretos via **WhatsApp** com mensagem automática
- Sistema de **avaliações com estrelas** dos clientes
- **Painel administrativo** protegido por senha
- **Controle de caixa** com entradas, saídas e saldo
- Animações e transições em toda a interface
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
├── admin.html       # Painel administrativo (protegido por senha)
└── README.md        # Este arquivo
```

---

## 🗄️ Tabelas no Supabase

### `produtos`

```sql
create table produtos (
  id uuid default gen_random_uuid() primary key,
  nome text not null,
  descricao text,
  preco numeric(10,2) not null,
  disponivel boolean default true,
  imagem_url text,
  created_at timestamptz default now()
);
```

### `avaliacoes`

```sql
create table avaliacoes (
  id uuid default gen_random_uuid() primary key,
  nome text not null,
  estrelas integer not null check (estrelas >= 1 and estrelas <= 5),
  comentario text not null,
  created_at timestamptz default now()
);
```

### `caixa`

```sql
create table caixa (
  id uuid default gen_random_uuid() primary key,
  descricao text not null,
  valor numeric(10,2) not null,
  tipo text not null check (tipo in ('entrada', 'saida')),
  created_at timestamptz default now()
);
```

### Políticas de acesso (RLS)

```sql
alter table produtos enable row level security;
alter table avaliacoes enable row level security;
alter table caixa enable row level security;

create policy "acesso publico produtos" on produtos for all using (true) with check (true);
create policy "acesso publico avaliacoes" on avaliacoes for all using (true) with check (true);
create policy "acesso publico caixa" on caixa for all using (true) with check (true);
```

---

## ⚙️ Como configurar

1. Crie um projeto em [supabase.com](https://supabase.com)
2. Rode o SQL acima no **SQL Editor**
3. Copie a **URL** e a **Chave publicável** do projeto
4. Substitua no `index.html` e `admin.html`:

```js
const SUPABASE_URL = "https://SEU-PROJETO.supabase.co";
const SUPABASE_KEY = "sua-chave-publica";
```

5. Para alterar a senha do painel admin, edite em `admin.html`:

```js
const SENHA_CORRETA = "sua-senha-aqui";
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
