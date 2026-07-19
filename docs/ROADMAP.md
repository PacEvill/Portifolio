# 🗺️ Portfólio — Roadmap Completo

## Stack Final (Aprovada)

- **Hosting:** Vercel (Gratuito, rápido, sem sleep, CI/CD nativo)
- **Banco de Dados:** Supabase (PostgreSQL, open-source)
- **Autenticação:** Supabase Auth (Magic Link, Email ou GitHub)
- **Imagens:** Supabase Storage
- **Framework:** HTML + CSS + JS puro (Frontend limpo e leve)

---

## 📋 Sprint 1 — Conteúdo base + Setup Vercel e Supabase

### Conteúdo a preparar (você faz manualmente para começar)

- [ ] Foto de perfil (formato quadrado recomendado, ex: 400×400px)
- [ ] Imagem de banner (ex: 1500×500px)
- [ ] Bio curta (2-3 linhas)
- [ ] Links reais: GitHub username, LinkedIn URL, email
- [ ] Criar repositório no GitHub, subir o código e conectar na Vercel
- [ ] Criar favicon (ícone do site)

### Supabase Setup (a fazer no código/painel)

- [ ] Criar projeto no Supabase (supabase.com)
- [ ] Criar tabelas SQL via painel
- [ ] Configurar Row Level Security (RLS)
- [ ] Ativar Supabase Auth
- [ ] Criar bucket no Supabase Storage (para imagens de posts)

### Estrutura do Banco (PostgreSQL)

```sql
-- profile
id | name | bio | location | avatar_url | banner_url

-- social_links
id | platform | url

-- posts
id | title | content | type | pinned | created_at

-- projects
id | name | description | image_url | repo_url | live_url | stack
```

---

## 📋 Sprint 2 — Modo Admin Invisível + CMS

### O que será construído no admin

- [ ] Ponto de entrada secreto (ex: `Ctrl+Shift+E` ou `/admin.html`) para abrir modal de login
- [ ] Integração Supabase Auth via JS
- [ ] Quando logado como admin:
  - Botão "Edit Portfolio" fica visível na barra
  - Textos ganham ícone de ✏️ (edição inline)
  - Botão "Novo Post" e "Novo Projeto" aparecem
- [ ] Formulários/Modais simples para inserir e editar dados no Supabase

---

## 📋 Sprint 3 — Grade de Atividade Funcional

### Fontes de dados

| Cor | Fonte | Como funciona |
| --- | --- | --- |
| 🟢 Verde | GitHub commits | API pública automática (`github-contributions-api`) |
| 🔵 Azul | Atividades Supabase | Log gerado automaticamente ao criar post/projeto |

### Funcionalidade

- Integrar as duas fontes em um único array de atividade
- Renderizar os quadradinhos baseado nos últimos 365 dias
- **Tooltip:** Ao passar o mouse, mostrar "Data: X posts, Y commits"

---

## 📋 Sprint 4 — Tabs dinâmicas com conteúdo

### O que será construído nas tabs

- [ ] **Posts** — Fetch via JS da tabela `posts` (ordenado por data)
- [ ] **Projetos** — Fetch via JS da tabela `projects`
- [ ] **Artigos** — Filtrar tabela `posts` onde `type = 'article'`
- [ ] **Sobre** — Conteúdo estático ou puxado da tabela `profile`

---

## 📋 Sprint 5 — Polimento Final

### SEO & Performance

- [ ] Meta tags (description, keywords)
- [ ] Open Graph (preview bonito no WhatsApp, LinkedIn, Twitter)
- [ ] Imagens otimizadas
- [ ] Lazy loading de imagens

### Mobile

- [ ] Revisar responsivo final em celulares reais
- [ ] Ajustar espaçamentos e fontes

---

## 🔐 Segurança (Row Level Security - RLS)

Regra fundamental de segurança no Supabase para o seu portfólio:

- **Leitura (SELECT):** Permitida para nível anônimo (visitantes vêem tudo).
- **Escrita (INSERT/UPDATE/DELETE):** Bloqueada no nível do banco. Só permitida se o `auth.uid()` for exatamente o ID do seu usuário autenticado.

---

## 📌 Status atual (após Sprint 0)

- ✅ Layout base construído (banner, avatar, 3 colunas)
- ✅ Dark/light mode funcional
- ✅ Grade de quadrados na barra (esperando dados)
- ✅ Links sociais e tabs criados visualmente
- ⏳ Aguardando: primeiro commit no GitHub e link no Vercel

---

Roadmap atualizado em: 19/07/2026 (Migração para Vercel + Supabase)
