<div align="center">

# `> Sync.Resources`
### Ecosystem & Premium Store for MTA:SA

![Version](https://img.shields.io/badge/version-1.0.0-6B8CAE?style=for-the-badge&logo=git)
![Node](https://img.shields.io/badge/Node.js-18.x-339933?style=for-the-badge&logo=nodedotjs)
![Database](https://img.shields.io/badge/MySQL-8.0-00758F?style=for-the-badge&logo=mysql)
![License](https://img.shields.io/badge/license-Proprietary-FF4D4F?style=for-the-badge)
![Status](https://img.shields.io/badge/System-OPERATIONAL-52C41A?style=for-the-badge)

<p align="center">
  <i>"Seu servidor, nossa missão. Do código à experiência."</i>
</p>

[🌐 Website](https://syncresourcesmta.store) • [📚 Documentação](#) • [💬 Discord](https://discord.gg/syncresources)

</div>

---

## // system.about

A **Sync Resources** é uma plataforma completa de e-commerce e gerenciamento de direitos digitais (DRM) desenvolvida especificamente para o ecossistema **MTA:SA (Multi Theft Auto)**. 

Este projeto integra três pilares fundamentais:
1.  **Web Store:** Interface moderna para venda de scripts com entrega automática.
2.  **Protection API:** Sistema de licenciamento e ofuscação para proteger o código Lua.
3.  **Discord Bot:** Automação de suporte, entrega de cargos e notificações.

## // core.features

### 🛒 Web Store (`/website`)
*   **UI/UX Premium:** Design responsivo, dark mode nativo, animações fluidas e identidade visual "Cyberpunk/Clean".
*   **Carrinho Unificado:** Gerenciamento de estado local, suporte a múltiplos itens e cupons de desconto.
*   **Pagamentos:** Integração transparente com **Mercado Pago (Pix)** e **Stripe**.
*   **Segurança:** Proteção CSRF, Rate Limiting, Helmet e validação rigorosa de inputs.
*   **Painel do Usuário:** Histórico de compras, download de produtos e gerenciamento de licenças.
*   **Modo Manutenção:** Sistema robusto de manutenção via middleware com retenção de SEO (HTTP 503).

### 🛡️ Protection API (`/protection-api`)
*   **Licenciamento em Tempo Real:** Validação via IP, Hardware ID e validade da licença.
*   **Heartbeat:** Monitoramento contínuo de servidores ativos.
*   **Anti-Leak:** Bloqueio automático de IPs suspeitos e alertas de violação.
*   **Analytics:** Coleta de dados de uso e performance dos scripts.

### 🤖 Discord Bot (`/discord-bot`)
*   **Sync Auth:** Vinculação de contas Site <-> Discord.
*   **Ticket System:** Sistema de suporte com atendimento inicial via IA.
*   **Notificações:** Logs de vendas, alertas de segurança e atualizações de produtos em tempo real.

## // tech.stack

<div align="center">

| Frontend | Backend | Database | DevOps/Tools |
| :---: | :---: | :---: | :---: |
| ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white) | ![NodeJS](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white) | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) |
| ![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white) | ![Express](https://img.shields.io/badge/Express.js-000000?style=flat-square&logo=express&logoColor=white) | ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) | ![PM2](https://img.shields.io/badge/PM2-2B037B?style=flat-square&logo=pm2&logoColor=white) |
| ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) | ![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white) | | ![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white) |

</div>

## // installation.guide

### Pré-requisitos
*   Node.js v18+
*   MySQL 8.0+
*   Conta de Desenvolvedor Discord
*   Credenciais Mercado Pago / Stripe

### 1. Configuração do Ambiente
Clone o repositório e configure as variáveis de ambiente:

```bash
git clone https://github.com/syncresources/project.git
cd syncresources-projeto
```

### 2. Instalação das Dependências
Execute o comando em cada módulo (`website`, `protection-api`, `discord-bot`):

```bash
npm install
```

### 3. Banco de Dados
Importe o schema inicial localizado em `website/src/database/schema.sql`.

### 4. Configuração `.env` (Exemplo `website`)
```env
# Server
PORT=3001
NODE_ENV=development
MAINTENANCE_MODE=false

# Database
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=sua_senha
DB_NAME=sync_resources

# Security
JWT_SECRET=sua_chave_super_secreta_32_chars
SESSION_SECRET=sua_session_secret

# Payments (Mercado Pago)
MP_ACCESS_TOKEN_PROD=seu_token_mp
MP_PUBLIC_KEY_PROD=sua_public_key

# Discord
DISCORD_CLIENT_ID=seu_client_id
DISCORD_CLIENT_SECRET=seu_client_secret
```

### 5. Inicialização
```bash
# Iniciar Website
cd website && npm start

# Iniciar Protection API
cd protection-api && npm start

# Iniciar Bot
cd discord-bot && npm start
```

## // project.structure

```bash
syncresources/
├── 📁 website/              # E-commerce Frontend & Backend API
│   ├── public/             # Assets estáticos (CSS, JS, Images)
│   ├── src/                # Lógica do servidor (Routes, Services)
│   └── server.js           # Entry point
├── 📁 protection-api/       # API de Licenciamento (DRM)
│   ├── src/routes/         # Endpoints de validação
│   └── services/           # Criptografia e lógica de proteção
└── 📁 discord-bot/          # Bot de Automação
    ├── commands/           # Slash commands
    └── events/             # Event listeners
```

## // security.protocol

A segurança é prioridade máxima na Sync Resources.
*   **Sanitização:** Todos os inputs passam por validação Zod/Joi e sanitização SQL.
*   **Logs:** Registro detalhado de ações administrativas e tentativas de violação (`/api/enhanced-logs`).
*   **IP Blocking:** Bloqueio automático de IPs maliciosos na API de proteção.

---

<div align="center">

**Sync Resources &copy; 2025**<br>
Desenvolvido com 💜 e Código Limpo.

</div>
