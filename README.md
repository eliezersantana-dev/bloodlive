🩸 BloodLive — Tecnologia que conecta vidas

"Uma conexão pode salvar vidas. Seja parte dessa corrente."

O BloodLive é uma plataforma web informativa e interativa voltada para o incentivo à doação de sangue na Grande São Paulo, conectando doadores a hemocentros, campanhas ativas, monitoramento automático de estoques e ferramentas personalizadas de acompanhamento de aptidão.

✨ Funcionalidades Principais

🚨 Monitoramento Automático de Estoques (Alertas):

Sincronização automática em 3 camadas: consulta a endpoint JSON dedicado (opcional), leitura direta do painel oficial da Fundação Pró-Sangue via proxy CORS e fallback inteligente com cache local (localStorage).

Atualização periódica a cada 15 minutos e botão de sincronização manual sob demanda.

Filtros por tipo sanguíneo (O−, O+, A−, A+, B−, B+, AB−, AB+), cidade e nível de criticidade (Crítico, Alerta, Estável).

📍 Mapa e Localizador Expandido de Hemocentros:

Base com 22 unidades cobrindo São Paulo (Centro/Oeste, Zona Sul, Zona Norte e Zona Leste), ABC Paulista (Santo André, São Bernardo do Campo, São Caetano do Sul e Mauá), Osasco, Barueri e Guarulhos (Fundação Pró-Sangue, Colsan e bancos hospitalares).

Mapa interativo incorporado com centralização por unidade ("Ver no mapa"), filtros por texto/cidade/região e links diretos para rotas no Google Maps.

🪪 Meu Perfil de Doador (100% Privado e Local):

Armazenamento exclusivo no navegador (localStorage), sem necessidade de cadastro, login ou envio de dados pessoais a servidores.

Calculadora de próxima doação: Calcula automaticamente o intervalo regulamentar (60 dias para homens / 90 dias para mulheres) com barra de progresso e contagem regressiva.

Lembrete de calendário (.ics): Gera e baixa um evento pronto para Google Agenda, Apple Calendar ou Outlook na data em que o doador estiver apto novamente.

Compatibilidade e impacto: Exibe para quais tipos o usuário pode doar, de quem pode receber, alertas caso seu tipo sanguíneo entre em nível crítico e estimativa de vidas impactadas (até 4 vidas por doação).

📋 Requisitos, Pré-Avaliação e Educação:

Checklist informativo de aptidão rápida, orientações pré e pós-doação, etapa a etapa do processo e seção de Mitos e Verdades.

📅 Campanhas de Doação:

Listagem categorizada em Ativas, Futuras e Encerradas, com opção de favoritar campanhas e compartilhar via Web Share API ou área de transferência.

🛠️ Tecnologias e Arquitetura

Arquitetura Single-File: Todo o HTML5 semântico, CSS3 moderno (com suporte automático a Dark Mode via prefers-color-scheme e áreas seguras safe-area para dispositivos móveis) e JavaScript Vanilla (ES6+) estão consolidados em um único arquivo index.html, sem dependências externas ou etapas de build.

Identidade Visual Vetorial: Logotipo Conexão Digital e favicon em SVG inline para nitidez em qualquer resolução.

Persistência no Cliente: Uso de localStorage para salvar o perfil do doador, campanhas favoritadas e cache da última leitura válida dos estoques.

🚀 Como Executar Localmente

Por ser uma aplicação estática autocontida, não é necessária a instalação de pacotes ou servidores complexos:

Clone o repositório:

git clone https://github.com/seu-usuario/bloodlive.git
cd bloodlive


Abra no navegador:

Clique duas vezes no arquivo index.html para abri-lo diretamente no Google Chrome, Edge, Firefox ou Safari; ou

Utilize uma extensão como o Live Server (VS Code) ou execute um servidor HTTP local simples:

npx serve .
# ou com Python:
python3 -m http.server 8080


⚙️ Configuração Opcional da API de Estoques

No bloco STOCK_CONFIG dentro de index.html, é possível apontar uma API própria ou um arquivo JSON atualizado periodicamente (ex.: via GitHub Actions ou Cloudflare Worker) para evitar depender de proxies CORS públicos:

var STOCK_CONFIG = {
  apiUrl: "https://seu-endpoint.example.com/estoques.json",
  officialUrl: "https://prosangue.sp.gov.br/reqestoque/posicao_estoque.php",
  corsProxy: "https://api.allorigins.win/get?url=",
  refreshIntervalMs: 15 * 60 * 1000,
  cacheKey: "bloodlive_stock_cache_v1"
};


Formato JSON esperado caso utilize apiUrl:

[
  { "tipo": "O−", "status": "Crítico", "cidade": "São Paulo" },
  { "tipo": "O+", "status": "Alerta", "cidade": "São Paulo" }
]


📁 Estrutura do Repositório

bloodlive/
├── index.html      # Aplicação web completa (HTML, CSS, SVG e JS)
└── README.md       # Documentação do projeto


⚠️ Aviso Legal

As informações de pré-avaliação e intervalos apresentadas no BloodLive têm caráter exclusivamente educativo e informativo, não substituindo a triagem clínica e hematológica realizada pelos profissionais de saúde nos hemocentros.

🤝 Contribuição

Contribuições são muito bem-vindas! Sinta-se à vontade para abrir uma Issue sugerindo novos postos de coleta, melhorias de acessibilidade ou atualizações de campanhas, ou enviar um Pull Request.
