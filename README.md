# Builtt Channel

O **Builtt Channel** é a plataforma moderna, robusta e omnichannel de atendimento ao cliente da **Builtt**, projetada para unificar conversas, automatizar o suporte com Inteligência Artificial e oferecer uma experiência premium aos usuários.

Baseado em contêineres e otimizado para deploy em nuvem com suporte nativo ao **Easypanel**.

---

## 🚀 Principais Recursos

### 💬 Atendimento Omnichannel
Centralize todas as conversas em uma única caixa de entrada inteligente, independentemente do canal de origem:
- Chat em sites (widget ao vivo).
- E-mail.
- WhatsApp, Instagram, Telegram, Messenger.
- Integrações customizadas via API.

### ✨ Captain AI – Agente Inteligente de Suporte
Automatize o autoatendimento com o agente de IA integrado (**Captain AI**):
- Integração nativa com APIs da OpenAI.
- Busca inteligente e contextualizada em documentos de ajuda (FAQ).
- Transbordo inteligente (handoff) para agentes humanos quando necessário.
- Guardrails e diretrizes customizáveis para manter o tom de voz da marca.

### 📚 Portal de Ajuda e FAQ (Help Center)
Crie e publique artigos, tutoriais e guias de autoajuda. Permita que os seus clientes encontrem respostas instantâneas, reduzindo o volume de tickets repetitivos.

### 🗂️ Gestão e Produtividade
- **Notas Privadas & Menções:** Colaboração direta entre agentes nas conversas.
- **Políticas de SLA:** Prazos automáticos de primeira resposta e resolução.
- **Cargos Personalizados (Custom Roles):** Controle granular de acessos e permissões.
- **Respostas Rápidas (Canned Responses):** Atalhos para mensagens frequentes.
- **Roteamento Automático:** Distribuição de conversas com base na capacidade de cada atendente.

---

## 🛠️ Como Implantar no Easypanel (via Docker Compose)

A aplicação está totalmente configurada para ser compilada e executada diretamente no **Easypanel**.

### Passo a Passo para Implantação:

1. **Crie um Serviço Compose no Easypanel:**
   No painel do seu Easypanel, clique em **+ Service** e selecione o tipo **Compose**.

2. **Configure a Origem do Código (Source):**
   - **Repository URL**: Preencha com a URL do seu repositório Git privado ou público (ex: GitHub/GitLab).
   - **Branch**: `main`
   - **Build Path**: `/`
   - **Docker Compose File**: `docker-compose.production.yaml`

3. **Chave SSH para Repositórios Privados:**
   Se o seu repositório for privado, clique em **"Generate SSH Key"** no Easypanel e adicione a chave pública copiada como uma **Deploy Key** nas configurações do seu repositório Git.

4. **Variáveis de Ambiente:**
   Configure as variáveis essenciais diretamente na aba de variáveis de ambiente do seu serviço no Easypanel. Use as definições do arquivo [.env.example](file:///c:/Users/augus/.workspace/chatwoot/chatwoot-develop/.env.example) como base. Destaque para as chaves principais:
   - `SECRET_KEY_BASE`: Chave única segura gerada para o Rails.
   - `FRONTEND_URL`: URL pública onde a aplicação estará acessível.
   - `REDIS_PASSWORD`: Senha de conexão interna do banco Redis.

5. **Clique em Deploy:**
   O Easypanel irá clonar o repositório, compilar as imagens a partir do [Dockerfile](file:///c:/Users/augus/.workspace/chatwoot/chatwoot-develop/docker/Dockerfile) local com os seus ajustes de marca e iniciar a pilha de serviços.

---

## 💻 Desenvolvimento Local

Para rodar e testar as alterações localmente utilizando Docker Compose de desenvolvimento:

1. Renomeie o arquivo de variáveis de ambiente:
   ```bash
   cp .env.example .env
   ```
2. Configure as credenciais necessárias no arquivo `.env`.
3. Inicie os contêineres de desenvolvimento:
   ```bash
   docker compose up --build
   ```
4. A aplicação estará disponível localmente em `http://localhost:3000`.

---

## ⚖️ Licença

O *Builtt Channel* é baseado no núcleo Chatwoot, publicado sob a licença MIT. 
&copy; 2026, Builtt. Todos os direitos reservados.
