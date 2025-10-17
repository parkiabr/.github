# 🅿️ PARKIA

<div align="center">
  <img src="https://via.placeholder.com/200x200/2563eb/ffffff?text=PARKIA" alt="PARKIA Logo" width="200"/>
  
  ### A primeira plataforma brasileira de gestão inteligente de estacionamentos com IA
  
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
  [![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)
  [![React 18](https://img.shields.io/badge/react-18-61dafb.svg)](https://reactjs.org/)
  [![FastAPI](https://img.shields.io/badge/FastAPI-0.104+-009688.svg)](https://fastapi.tiangolo.com/)
  [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-336791.svg)](https://www.postgresql.org/)
  
  [Website](https://parkia.com.br) • [Documentação](#-documentação) • [Demo](https://demo.parkia.com.br) • [Roadmap](#-roadmap)
</div>

---

## 📖 Sobre a PARKIA

A **PARKIA** é uma plataforma completa de automação e gestão de estacionamentos que utiliza **Inteligência Artificial** para transformar operações manuais em processos 100% digitais e autônomos.

### 🎯 Missão

Revolucionar a gestão de estacionamentos no Brasil através de tecnologia de ponta, tornando operações mais eficientes, seguras e lucrativas.

### 💡 Diferenciais

- 🤖 **IA Conversacional** - Atendimento automatizado via WhatsApp
- 📊 **Tempo Real** - Dashboard com atualizações instantâneas
- 🔗 **Multi-canal** - Control, Agent, Self-Service integrados
- 🏢 **Multi-tenant** - Suporte para múltiplas empresas e unidades
- 💰 **Pagamentos Automáticos** - PIX integrado via Shipay
- 📈 **Analytics Avançado** - Relatórios e insights de negócio

---

## 🌟 Ecossistema de Produtos

### 1. **PARKIA Control** ✅ (Produção)
Sistema completo de gestão operacional diária:

- 🤖 **Agent (IA WhatsApp)** - Atendimento automatizado 24/7
- 💻 **Interface do Operador** - Gestão presencial de entrada/saída
- 📱 **Autoatendimento** - Self-service em totens/tablets
- 🎫 **Tickets Digitais** - QR Code com visualização tempo real

**Stack:** Python, FastAPI, LangChain, React, TypeScript, Evolution API

### 2. **PARKIA Central** 🔄 (Em Desenvolvimento)
Plataforma central de gestão administrativa completa:

- 👥 **Gestão de Mensalistas** - CRUD + importação em massa
- 🚗 **Movimentações** - Controle entrada/saída (mensalistas + rotativos)
- 💳 **Pagamentos** - Cobranças mensais + permanência (PIX/Cartão)
- 📊 **Dashboard** - Analytics e métricas em tempo real
- 📧 **Notificações** - Lembretes de vencimento automáticos
- ⚠️ **Inadimplência** - Controle e cobrança escalonada
- 📈 **Relatórios** - Exportação Excel/PDF
- 🏢 **Multi-tenant** - Gestão de múltiplas empresas/unidades

**Stack:** Python, FastAPI, PostgreSQL, React, TypeScript, Lovable

### 3. **PARKIA Self** 🔄 (Em Desenvolvimento)
Interface de autoatendimento para clientes:

- 🚦 **Entrada/Saída Autônoma** - Sem intervenção de operador
- 📱 **Touch-friendly** - Otimizado para tablets/totens
- 💳 **Pagamento Integrado** - PIX instantâneo
- 🎫 **Emissão de Ticket** - QR Code automático

**Stack:** React, TypeScript, Tailwind CSS

---

## 🗂️ Repositórios

### Core Platform

| Repositório | Descrição | Status | Stack Principal |
|------------|-----------|--------|----------------|
| [`parkia-central-backend`](https://github.com/parkia/parkia-central-backend) | API Central + Lógica de Negócio | 🔄 Backlog | Python, FastAPI, PostgreSQL |
| [`parkia-central-frontend`](https://github.com/parkia/parkia-central-frontend) | Dashboard Administrativo | 🔄 Backlog | React, TypeScript, Lovable |
| [`parkia-control`](https://github.com/parkia/parkia-control) | Interface do Operador | ✅ Produção | React, TypeScript |
| [`parkia-agent`](https://github.com/parkia/parkia-agent) | Agente IA WhatsApp | ✅ Produção | Python, LangChain, FastAPI |
| [`parkia-self`](https://github.com/parkiabr/parkia-autoatendimento) | Autoatendimento | ✅ Produção | React, TypeScript |
| [`parkia-ticket-view`](https://github.com/parkiabr/parkia-ticket-view) | Ticket Digital | ✅ Produção | React, TypeScript |
| [`parkia-control-api`](https://github.com/parkiabr/parkia-control-api) | API Backend Control | ✅ Produção | Python, FastAPI |

### Infraestrutura & DevOps

| Repositório | Descrição | Status |
|------------|-----------|--------|
| [`parkia-docs`](https://github.com/parkia/parkia-docs) | Documentação técnica completa | ✅ Ativo |

### Integrações

| Repositório | Descrição | Status |
|------------|-----------|--------|
| `parkia-evolution-api` | Integração WhatsApp (Evolution API) | ✅ Produção |
| `parkia-shipay-integration` | Gateway de pagamento (Shipay) | ✅ Produção |

**Legenda:**
- ✅ Produção
- 🔄 Em Desenvolvimento  
- 📅 Planejado
- ⏸️ Pausado

---

## 🏗️ Arquitetura

### Visão Geral

```
┌─────────────────────────────────────────────────┐
│         PARKIA Central (Backend Central)        │
│                                                 │
│  💾 PostgreSQL | 🔴 Redis | 🐰 RabbitMQ        │
│  📊 Dashboard | 👥 Mensalistas | 🚗 Movimentações│
│  💰 Pagamentos | 📈 Relatórios                 │
└────────────┬────────────────────────────────────┘
             │
    ┌────────┴────────┐
    │                 │
┌───▼────┐    ┌───────▼────────┐    ┌──────▼──────┐
│Control │    │ Agent (IA)     │    │    Self     │
│(Operador)   │  (WhatsApp)    │    │(Autoatend.) │
└────────┘    └────────────────┘    └─────────────┘
```

### Arquitetura: Monolito Modular

Escolhemos **Monolito Modular**:
---

## 📁 Estrutura de Pastas

### Backend (parkia-central-backend)

```
parkia-central-backend/
├── backend/
│   ├── main.py                    # FastAPI app
│   ├── core/                      # Configurações centrais
│   │   ├── config.py              # Settings
│   │   ├── database.py            # SQLAlchemy async
│   │   ├── auth.py                # JWT
│   │   ├── dependencies.py        # FastAPI Depends
│   │   └── security.py            # Password hashing
│   │
│   ├── modules/                   # Módulos de negócio
│   │   ├── auth/                  # Autenticação
│   │   ├── empresas/              # Multi-tenant
│   │   ├── unidades/              # Filiais
│   │   ├── usuarios/              # RBAC
│   │   ├── mensalistas/           # Core: Mensalistas
│   │   ├── cobrancas/             # Pagamentos mensais
│   │   ├── movimentacoes/         # Entrada/Saída
│   │   ├── tarifas/               # Preços rotativos
│   │   ├── pagamentos/            # Pagamentos permanência
│   │   ├── selos/                 # Convênios
│   │   ├── notificacoes/          # Emails/WhatsApp
│   │   ├── relatorios/            # Excel/PDF
│   │   └── dashboard/             # Analytics
│   │
│   ├── shared/                    # Código compartilhado
│   │   ├── validators.py          # CPF, email, placa
│   │   ├── utils.py
│   │   ├── enums.py               # Status, tipos
│   │   └── mixins.py              # TenantMixin, TimestampMixin
│   │
│   └── workers/                   # Background jobs
│       ├── email_worker.py
│       ├── cobranca_worker.py
│       └── relatorio_worker.py
│
├── tests/                         # Testes
│   ├── unit/
│   └── integration/
│
├── migrations/                    # Alembic
├── docker/                        # Docker configs
├── requirements.txt
└── README.md
```

### Frontend (parkia-central-frontend)

```
parkia-central-frontend/
├── src/
│   ├── components/
│   │   ├── common/                # Button, Input, Table
│   │   ├── layout/                # Header, Sidebar
│   │   ├── mensalistas/           # Componentes específicos
│   │   ├── movimentacoes/
│   │   ├── dashboard/
│   │   └── relatorios/
│   │
│   ├── pages/                     # Rotas
│   │   ├── Login.tsx
│   │   ├── Dashboard.tsx
│   │   ├── Mensalistas.tsx
│   │   ├── Movimentacoes.tsx
│   │   └── Relatorios.tsx
│   │
│   ├── services/                  # API calls
│   │   ├── api.ts
│   │   ├── mensalistas.service.ts
│   │   └── movimentacoes.service.ts
│   │
│   ├── hooks/                     # Custom hooks
│   │   ├── useAuth.ts
│   │   └── useMensalistas.ts
│   │
│   ├── types/                     # TypeScript types
│   │   ├── mensalista.types.ts
│   │   └── movimentacao.types.ts
│   │
│   ├── utils/                     # Utilitários
│   │   ├── formatters.ts
│   │   └── validators.ts
│   │
│   └── App.tsx
│
├── public/
├── tests/
├── package.json
└── README.md
```

---

## 🧩 Estrutura de Módulos

**Cada módulo segue o padrão de camadas:**

```
modules/[nome_modulo]/
├── __init__.py
├── router.py          # 🌐 Camada HTTP (FastAPI routes)
├── service.py         # 💼 Camada de Negócio (business logic)
├── repository.py      # 🗄️ Camada de Dados (queries SQL)
├── models.py          # 📊 SQLAlchemy models
└── schemas.py         # ✅ Pydantic schemas (validação)
```

## 🛠️ Stack Tecnológica

### Backend
- **Python 3.11+** - Linguagem principal
- **FastAPI** - Framework web assíncrono
- **SQLAlchemy 2.0** - ORM async
- **PostgreSQL** - Banco de dados principal
- **Redis 7** - Cache e sessões
- **RabbitMQ** - Filas de mensagens
- **Alembic** - Migrations
- **Pydantic v2** - Validação de dados
- **JWT** - Autenticação

### Frontend
- **React 18** - Framework UI
- **TypeScript** - Type safety
- **Lovable** - Desenvolvimento rápido
- **Tailwind CSS** - Estilização
- **shadcn/ui** - Componentes
- **Vite** - Build tool
- **React Router** - Navegação
- **Axios** - HTTP client
- **Zustand** - State management

### Integrações
- **Shipay** - Gateway pagamento PIX
- **Evolution API** - WhatsApp Business
- **SMTP** - Emails transacionais
- **WebSocket** - Tempo real

### DevOps
- **Docker** - Containerização
- **Docker Compose** - Orquestração local
- **GitHub Actions** - CI/CD
- **Google Cloud Platform** - Cloud (futuro)

---

## 📚 Documentação

- 📖 [Documentação Técnica Completa](https://docs.parkia.com.br)
- 🎨 [Guia de Estilo de Código](./docs/STYLE_GUIDE.md)
- 🏗️ [Arquitetura Detalhada](./docs/ARCHITECTURE.md)
- 🔌 [Referência da API](https://api.parkia.com.br/docs)
- 🧪 [Guia de Testes](./docs/TESTING.md)
---

<div align="center">
  <p>Feito com ❤️ pela equipe PARKIA</p>
  <p>© 2025 PARKIA Tecnologia. Todos os direitos reservados.</p>
</div>
