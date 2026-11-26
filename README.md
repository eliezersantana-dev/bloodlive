# 🩸 BloodLive — Tecnologia que conecta vidas

Plataforma web leve, responsiva e acessível dedicada à conscientização sobre doação de sangue, localização de hemocentros na Grande São Paulo, acompanhamento de campanhas e monitoramento dos níveis de estoque sanguíneo.

> *"Uma conexão pode salvar vidas. Seja parte dessa corrente."*

---

## ✨ Funcionalidades Principais

* **Painel Inicial & Urgência de Estoques:**
  * Exibe em destaque os tipos sanguíneos em estado **Crítico** na Grande São Paulo logo na página inicial.
  * Cartão de acesso rápido ao status individual do doador.
* **Meu Perfil de Doador (100% Privado / `localStorage`):**
  * Armazenamento local no navegador do usuário (sem necessidade de cadastro, senha ou servidor).
  * **Calculadora de Próxima Doação:** Contagem regressiva e barra de progresso baseadas no intervalo regulamentar (90 dias para mulheres / 60 dias para homens).
  * **Lembrete de Calendário (`.ics`):** Exportação direta de evento para Google Agenda, Apple Calendar ou Outlook na data exata em que o doador estiver apto novamente.
  * **Compatibilidade Sanguínea & Impacto:** Mostra para quais tipos o usuário pode doar, de quais pode receber e a estimativa de vidas impactadas (até 4 vidas por bolsa).
* **Mapa e Localizador de Hemocentros (Grande SP):**
  * 22 unidades cadastradas na Capital, ABC Paulista, Osasco, Barueri e Guarulhos (Fundação Pró-Sangue, Colsan e bancos hospitalares).
  * Busca por texto, filtro por cidade e região, mapa interativo incorporado e link direto para rotas no Google Maps.
* **Monitoramento Automático de Estoques (Alertas):**
  * Sincronização periódica (a cada 15 minutos) com os níveis da **Fundação Pró-Sangue**, com fallback em cache local e modo offline.
  * Filtros por tipo sanguíneo, cidade e nível de criticidade (`Crítico`, `Alerta`, `Estável`).
* **Campanhas & Pré-Triagem Informativa:**
  * Listagem de campanhas ativas, futuras e encerradas com opção de favoritar e compartilhar via Web Share API / área de transferência.
  * Questionário de pré-avaliação rápida dos requisitos básicos e seção educativa com mitos, verdades e etapas da doação.
* **Acessibilidade e Tema Adaptativo:**
  * Suporte automático a **Modo Claro e Modo Escuro** (`prefers-color-scheme`), navegação por teclado com indicadores de foco visíveis e layout adaptado para dispositivos móveis.

---

## 🗂️ Estrutura do Projeto

```text
bloodlive/
├── index.html      # Aplicação Single-Page completa (HTML5, CSS3 e JavaScript puro)
└── README.md       # Documentação do repositório
