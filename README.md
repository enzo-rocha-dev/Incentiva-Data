# 🚀 Incentiva Data - MVP

## 📌 Descrição
Plataforma multi-sided SaaS que conecta **empresas** e **Organizações da Sociedade Civil (OSCs)** para doações direcionadas, com transparência, mensurabilidade de impacto social e comunicação de ESG.  

A proposta do MVP é validar o fluxo de **doação simplificada**, **split de pagamentos**, **emissão de comprovantes** e **dashboards de impacto**.

---

## 📁 Estrutura do Projeto


```
/
├── index.html                 # Página inicial
├── README.md                  # Documentação do projeto
├── Paginas/                   # Páginas internas
│   ├── dashboard.html         # Dashboard com Looker Studio
│   ├── painel.html           # Simulador de split de pagamento
│   ├── solicitacoes.html     # Formulários de solicitação
│   ├── editar-perfil.html    # Página de perfil
│   └── sobre.html            # Página institucional
└── Estilos/                  # Recursos estáticos
    ├── css/
    │   └── style.css         # Estilos principais
    ├── images/               # Imagens gerais
    ├── membros/              # Fotos dos membros da equipe
    │   ├── enzo.jpg
    │   ├── duda.jpg
    │   ├── taisa.jpg
    │   ├── giovanna.jpg
    │   └── giovanni.jpg
    └── logo/                 # Logos da empresa
        ├── LogoIncentivaData.png
        └── LogoIncentivaData-Simples.png

---

## 🎯 Funcionalidades do MVP

### ✅ Implementado
- Landing page responsiva com tema claro/escuro
- Sistema de autenticação **simulado**
- Dashboard inicial (Looker Studio embed)
- Painel de split de pagamento (mock)
- Página institucional com equipe
- Dados de perfil persistentes via **LocalStorage**

### 🔄 Em Desenvolvimento
- Sistema de doações reais
- Relatórios de impacto automatizados
- Gestão avançada de perfis
- API backend (Node.js / Express)

### 📋 Próximos Passos
- Integração com **gateway de pagamento** (Mercado Pago / Stripe)
- Sistema de **matching OSC/Empresa**
- Emissão de **comprovantes PDF**
- Dashboards de impacto em tempo real

---

## 🛠️ Tech Stack

### Atual (MVP estático)
- **Frontend**: HTML5, CSS3 (variáveis e gradientes), JS ES6+
- **Servidor local**: Python HTTP server (dev)
- **Deploy**: GitHub Pages / Replit

### Recomendado para evolução
- **Frontend**: React (Vite) + TailwindCSS
- **Backend**: Node.js + Express (ou NestJS para maior estrutura)
- **Banco de dados**: PostgreSQL (RDS/Cloud SQL)
- **Pagamentos**: Mercado Pago / Stripe (sandbox → produção)
- **Storage**: AWS S3 ou GCS
- **Relatórios/BI**: Looker Studio (dashboards embutidos)
- **Autenticação**: JWT (Auth0 opcional)
- **CI/CD**: Docker + GitHub Actions; deploy em Vercel + Railway/Heroku

---

## 🗄️ Banco de Dados (esquema resumido)

- `users` → id, nome, email, role [empresa/osc/admin]  
- `oscs` → id, nome, cnpj, descrição, ods_tags[], conta_bancária, trust_score  
- `companies` → id, nome, cnpj, branding_tags[]  
- `donations` → id, company_id, osc_id, valor, status, payment_provider_id, created_at  
- `bank_accounts` → id, osc_id, banco, agência, conta, tipo  
- `certificates` → id, donation_id, pdf_url, issued_at  

---

## 🔌 Endpoints principais (planejados)

- `POST /auth/login`
- `POST /osc` → cadastrar OSC
- `GET /osc/{id}` → visualizar OSC
- `POST /donations` → iniciar doação (checkout url)
- `POST /payments/webhook` → confirmação + emissão de comprovante
- `GET /dashboard/company/{id}` → relatórios de match e valores

---

## 🧪 Credenciais de Teste
- **Empresa/Pessoa:** `empresa@teste.com` / `123`  
- **OSC:** `osc@teste.com` / `123`  

---

## 🎨 Paleta de Cores
- **Azul Pastel:** `#6195C5`, `#AFCBF3`  
- **Laranja Pastel:** `#F4A460`, `#EECD86`  
- **Neutros:** `#f8fafc`, `#1e293b`  

---

## 📊 Métricas (KPI iniciais)
- Nº de doações processadas (D0)  
- Valor total arrecadado (R$)  
- Tempo médio de checkout  
- Taxa de conversão OSC → doação  
- NPS (feedback inicial das OSCs)  

---

## 👥 Equipe
- **Enzo Rocha** – Founder & CTO  
- **Giovanna Janino** – Founder & Relações com OSCs  
- **Giovanni** – Co-founder & Relações Públicas  
- **Maria Eduarda (Duda)** – PO & UX  
- **Taísa** – Marketing & Comunicação  
