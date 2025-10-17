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
| [`parkia-central-backend`](https://github.com/parkia/parkia-central-backend) | API Central + Lógica de Negócio | 🔄 Desenvolvimento | Python, FastAPI, PostgreSQL |
| [`parkia-central-frontend`](https://github.com/parkia/parkia-central-frontend) | Dashboard Administrativo | 🔄 Desenvolvimento | React, TypeScript, Lovable |
| [`parkia-control`](https://github.com/parkia/parkia-control) | Interface do Operador | ✅ Produção | React, TypeScript |
| [`parkia-agent`](https://github.com/parkia/parkia-agent) | Agente IA WhatsApp | ✅ Produção | Python, LangChain, FastAPI |
| [`parkia-self`](https://github.com/parkia/parkia-self) | Autoatendimento | 🔄 Desenvolvimento | React, TypeScript |

### Infraestrutura & DevOps

| Repositório | Descrição | Status |
|------------|-----------|--------|
| [`parkia-central-dev`](https://github.com/parkia/parkia-central-dev) | Docker Compose (ambiente dev) | 🔄 Setup |
| [`parkia-infra`](https://github.com/parkia/parkia-infra) | Terraform, Nginx, CI/CD | 📅 Planejado |
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

Escolhemos **Monolito Modular** ao invés de Microsserviços porque:

- ✅ **MVP 3x mais rápido** (2-3 semanas vs 6-8)
- ✅ **Time pequeno** (5 pessoas)
- ✅ **Debug simplificado** (stack trace completo)
- ✅ **Deploy único** (1 comando)
- ✅ **Custos 3x menores** (1 servidor vs múltiplos)
- ✅ **Transações ACID** nativas
- ✅ **Escalável até 100+ clientes**

Empresas que provam que funciona:
- **Shopify**: 50+ devs no monolito, 1M+ lojas
- **GitHub**: 100+ devs no monolito
- **Stack Overflow**: 200M+ usuários/mês

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

### Exemplo: Módulo Mensalistas

```python
# router.py - Rotas FastAPI
@router.post("/", response_model=MensalistaResponse)
async def criar_mensalista(
    data: MensalistaCreate,
    empresa_id: UUID = Depends(get_current_empresa),
    db: AsyncSession = Depends(get_db)
):
    service = MensalistaService(db)
    return await service.criar(empresa_id, data)
```

```python
# service.py - Lógica de Negócio
class MensalistaService:
    async def criar(self, empresa_id: UUID, data: MensalistaCreate):
        # Validações
        if not validar_cpf(data.cpf):
            raise CPFInvalidoError()
        
        # Verifica duplicidade
        if await self.repository.buscar_por_cpf(empresa_id, data.cpf):
            raise MensalistaJaExisteError()
        
        # Cria no banco
        return await self.repository.criar(empresa_id, data)
```

```python
# repository.py - Queries no Banco
class MensalistaRepository:
    async def criar(self, empresa_id: UUID, data: MensalistaCreate):
        mensalista = Mensalista(empresa_id=empresa_id, **data.dict())
        self.db.add(mensalista)
        await self.db.commit()
        await self.db.refresh(mensalista)
        return mensalista
```

**Benefícios:**
- ✅ Separação clara de responsabilidades
- ✅ Fácil de testar (cada camada isoladamente)
- ✅ Reutilização de código
- ✅ Manutenção simplificada

---

## 🛠️ Stack Tecnológica

### Backend
- **Python 3.11+** - Linguagem principal
- **FastAPI** - Framework web assíncrono
- **SQLAlchemy 2.0** - ORM async
- **PostgreSQL 15** - Banco de dados principal
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

## 🚀 Quick Start

### Pré-requisitos

- Python 3.11+
- Node.js 18+
- PostgreSQL 15
- Redis 7
- RabbitMQ
- Docker (opcional)

### Setup com Docker (Recomendado)

```bash
# Clone o repositório dev
git clone https://github.com/parkia/parkia-central-dev.git
cd parkia-central-dev

# Clone backend e frontend
git clone https://github.com/parkia/parkia-central-backend.git
git clone https://github.com/parkia/parkia-central-frontend.git

# Sobe tudo
docker-compose up -d
```

**Acessar:**
- Backend API: http://localhost:8000
- Frontend: http://localhost:3000
- API Docs: http://localhost:8000/docs
- RabbitMQ UI: http://localhost:15672

### Setup Manual

#### Backend

```bash
cd parkia-central-backend

# Criar ambiente virtual
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate   # Windows

# Instalar dependências
pip install -r requirements.txt

# Configurar .env
cp .env.example .env
# Editar .env com suas configurações

# Rodar migrations
alembic upgrade head

# Rodar servidor
uvicorn backend.main:app --reload
```

#### Frontend

```bash
cd parkia-central-frontend

# Instalar dependências
npm install

# Configurar .env
cp .env.example .env
# Editar .env com URL da API

# Rodar
npm run dev
```

---

## 👥 Equipe

| Nome | Papel | Foco |
|------|-------|------|
| **Gabriel** | CEO | Tech Leadership, Product, Code Reviews |
| **Mariana** | Product Owner | Produto, Prioridades, UX/UI, Requisitos |
| **Gustavo** | Full Stack Pleno | Tech Lead Backend, Arquitetura |
| **José** | Full Stack Jr | Frontend, CRUD, Aprendizado |
| **Cauã** | Engenheiro IA Jr | PARKIA Agent, OCR, Autoatendimento |

---

## 📅 Roadmap

### ✅ Fase 1: Fundação (Semana 1-2) - Concluído
- Setup arquitetura
- Autenticação JWT
- Multitenancy (Empresas + Unidades)
- RBAC (Perfis de Acesso)
- CRUD Usuários

### 🔄 Fase 2: Mensalistas (Semana 3-4) - Em Andamento
- CRUD Mensalistas
- Importação massa (Excel)
- Integração Shipay (PIX)
- Sistema de Cobranças
- Notificações automáticas

### 📅 Fase 3: Movimentações (Semana 5-6) - Planejada
- Sistema de Movimentações (entrada/saída)
- Cálculo de Tarifas
- Pagamentos Permanência
- WebSocket tempo real
- API para Control/Agent/Self

### 📅 Fase 4: Avançado (Semana 7-8) - Planejada
- Selos/Convênios
- Dashboard Analytics completo
- Relatórios (Excel/PDF)
- Otimizações de performance
- Testes E2E

### 🔮 Futuro
- Portal do Mensalista (área do cliente)
- App Mobile nativo
- OCR para documentos
- IA preditiva de inadimplência
- Integração com ERPs
- API pública

---

## 📊 Métricas de Sucesso

### Técnicas
- ✅ Uptime > 99.5%
- ✅ Tempo de resposta API < 200ms
- ✅ Cobertura de testes > 80%
- ✅ Zero perda de dados

### Negócio
- 📈 5-10 clientes até Q4 2025
- 📈 1000+ tickets processados/mês
- 📈 NPS > 70
- 📈 Churn < 5%

---

## 📚 Documentação

- 📖 [Documentação Técnica Completa](https://docs.parkia.com.br)
- 🎨 [Guia de Estilo de Código](./docs/STYLE_GUIDE.md)
- 🏗️ [Arquitetura Detalhada](./docs/ARCHITECTURE.md)
- 🔌 [Referência da API](https://api.parkia.com.br/docs)
- 🧪 [Guia de Testes](./docs/TESTING.md)

---

## 🤝 Como Contribuir

1. Fork o repositório
2. Crie uma branch (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -m 'Add: nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

**Padrões:**
- Seguir [Conventional Commits](https://www.conventionalcommits.org/)
- Código deve passar em todos os testes
- Cobertura de testes > 80%
- Code review obrigatório

---

## 📝 Changelog

Ver [CHANGELOG.md](./CHANGELOG.md) para histórico completo de mudanças.

---

## 📄 Licença

Este projeto está sob a licença MIT. Ver [LICENSE](./LICENSE) para mais detalhes.

---

## 📞 Contato

- **Website:** [parkia.com.br](https://parkia.com.br)
- **Email:** contato@parkia.com.br
- **LinkedIn:** [PARKIA](https://linkedin.com/company/parkia)
- **GitHub:** [@parkia](https://github.com/parkia)

---

<div align="center">
  <p>Feito com ❤️ pela equipe PARKIA</p>
  <p>© 2025 PARKIA Tecnologia. Todos os direitos reservados.</p>
</div>
