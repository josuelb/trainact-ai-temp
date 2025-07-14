# 📦 Estrutura do Projeto

```
backend/
├── requirements.txt                # Lista de dependências do projeto
├── Dockerfile                      # Containerização do backend (FastAPI)
├── README.md                       # Documentação inicial
└── src/
    ├── main.py                     # Inicialização e montagem da aplicação FastAPI
    ├── core/                       # Configuração central
    │   ├── config.py              # Carregamento de variáveis de ambiente e settings globais
    │   ├── middlewares.py        # CORS, Tenant, Logging e outros middlewares
    │   ├── security.py           # Criptografia, geração de tokens, validações
    │   └── logging_config.py     # Configuração de logs (formato, destino, níveis)
    │
    ├── auth/
    │   ├── dependencies.py       # Funções para validar JWT nos endpoints
    │   ├── jwt.py                # Funções para criar e validar tokens JWT
    │   ├── models.py             # Modelos ORM (usuários, permissões)
    │   ├── routes.py             # Endpoints de login, registro e autenticação
    │   └── schemas.py            # Schemas Pydantic para login, user, etc.
    │
    ├── db/
    │   ├── base.py               # Base declarativa do SQLAlchemy
    │   ├── session.py            # Conexão com o banco de dados
    │   └── utils.py              # Utilitários para migrations, criação de schemas, etc.
    │
    ├── tenants/
    │   ├── models.py             # Modelo de Tenant (empresa/cliente)
    │   ├── routes.py             # Endpoints para criação e gestão de tenants
    │   └── services.py           # Regras de negócio para tenants
    │
    ├── ai/
    │   ├── gpt/
    │   │   ├── service.py        # Comunicação com API GPT-4o
    │   │   └── prompts.py        # Templates e personalização de prompts
    │   ├── whisper/
    │   │   └── transcriber.py    # Lógica de transcrição local (Whisper)
    │   ├── translation/
    │   │   └── deepl.py          # Funções para tradução usando DeepL API
    │   ├── tts/
    │   │   └── azure_tts.py      # Integração com Microsoft Azure TTS
    │   └── heygen/
    │       └── video_gen.py      # Integração com HeyGen API para geração de vídeos
    │
    ├── sim/
    │   ├── logic/
    │   │   └── engine.py         # Núcleo da lógica de simulação
    │   ├── flow/
    │   │   └── controller.py     # Geração adaptativa de perguntas com base nas respostas
    │   └── scoring/
    │       └── evaluator.py      # Avaliação automática das respostas
    │
    ├── lms/
    │   ├── models.py             # Mapeamento das integrações com LMS
    │   ├── webhook.py            # Receptor de webhooks ou notificações
    │   └── services.py           # Lógica para envio de notas e relatórios
    │
    ├── reports/
    │   ├── pdf.py                # Geração de relatórios em PDF
    │   ├── json.py               # Geração de relatórios em JSON
    │   └── exporter.py           # Exportações para Excel, CSV
    │
    ├── analytics/
    │   ├── metrics.py            # KPIs e métricas do sistema
    │   └── filters.py            # Filtros para dashboard analítico
    │
    ├── media/
    │   ├── storage.py            # Upload, exclusão e organização de arquivos
    │   └── paths.py              # Definição de diretórios e caminhos
    │
    └── utils/
        ├── cache.py              # Redis, memorização de resultados e sessão
        ├── tasks.py              # Tarefas assíncronas (Celery ou BackgroundTasks)
        └── helpers.py            # Funções genéricas de apoio
```
