# 🅿️ PARKIA

<div align="center">
  <img src="https://via.placeholder.com/200x200/2563eb/ffffff?text=PARKIA" alt="PARKIA Logo" width="200"/>
  
  ### A primeira plataforma brasileira de gestão inteligente de estacionamentos com IA
  
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
  [![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)
  [![React 18](https://img.shields.io/badge/react-18-61dafb.svg)](https://reactjs.org/)
  [![FastAPI](https://img.shields.io/badge/FastAPI-0.104+-009688.svg)](https://fastapi.tiangolo.com/)
  
  [Website](https://parkia.com.br) • [Documentação](#-documentação) • [Roadmap](#-roadmap) • [Contribuir](#-como-contribuir)
</div>

---

## 📖 Sobre a PARKIA

A **PARKIA** é uma plataforma completa de automação e gestão de estacionamentos que utiliza **Inteligência Artificial** para transformar operações manuais em processos 100% digitais e autônomos.

### 🎯 Missão
Revolucionar a gestão de estacionamentos no Brasil através de tecnologia de ponta, tornando operações mais eficientes, seguras e lucrativas.

### 🌟 Produtos

#### 1. **PARKIA Control** (MVP Concluído)
Sistema completo de gestão operacional com:
- 🤖 Agente de IA para atendimento via WhatsApp 24/7
- 💻 Interface do operador para gestão presencial
- 📱 Autoatendimento em totens/tablets
- 🎫 Tickets digitais com QR Code
- 📊 Dashboard administrativo em tempo real

#### 2. **Recorrente** (Em Desenvolvimento)
Microsaas de gestão de mensalistas com:
- 🌐 Portal de auto-cadastro para clientes
- 💳 Pagamento recorrente via Pix
- 📈 Dashboard de gestão completa
- 📥 Importação em massa de planilhas
- 📧 Notificações automáticas
- ⚠️ Controle de inadimplência

---

## 🗂️ Repositórios

### Core - PARKIA Control

| Repositório | Descrição | Status | Stack |
|------------|-----------|--------|-------|
| [`parkia-backend`](./parkia-backend) | API principal + Agente IA | ✅ Produção | Python, FastAPI, LangChain |
| [`parkia-operator`](./parkia-operator) | Interface do Operador | ✅ Produção | React, TypeScript, Lovable |
| [`parkia-ticket-viewer`](./parkia-ticket-viewer) | Visualizador de Tickets Digitais | ✅ Produção | React, TypeScript |
| [`parkia-self-service`](./parkia-self-service) | Interface de Autoatendimento | 🔄 Desenvolvimento | React, TypeScript, Lovable |
| [`parkia-admin-dashboard`](./parkia-admin-dashboard) | Dashboard Administrativo | 📅 Planejado | React, TypeScript |

### Recorrente - Gestão de Mensalistas

| Repositório | Descrição | Status | Stack |
|------------|-----------|--------|-------|
| [`recorrente-backend`](./recorrente-backend) | API de gestão de mensalistas | 🔄 Desenvolvimento | Python, FastAPI |
| [`recorrente-admin`](./recorrente-admin) | Dashboard Admin | 🔄 Desenvolvimento | React, TypeScript, Lovable |
| [`recorrente-portal`](./recorrente-portal) | Portal Público de Auto-cadastro | 🔄 Desenvolvimento | React, TypeScript, Lovable |

### Infraestrutura & DevOps

| Repositório | Descrição | Status |
|------------|-----------|--------|
| [`parkia-infra`](./parkia-infra) | Configurações Docker, Nginx, CI/CD | ✅ Ativo |
| [`parkia-docs`](./parkia-docs) | Documentação técnica completa | ✅ Ativo |
| [`parkia-scripts`](./parkia-scripts) | Scripts de automação e deploy | ✅ Ativo |

### Integrações

| Repositório | Descrição | Status |
|------------|-----------|--------|
| [`parkia-whatsapp-integration`](./parkia-whatsapp-integration) | Integração Evolution API | ✅ Produção |
| [`parkia-payment-gateway`](./parkia-payment-gateway) | Integrações Shipay, Mercado Pago | 🔄 Desenvolvimento |

---

## 🏗️ Arquitetura Geral
