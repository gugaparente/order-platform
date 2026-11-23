# Plataforma de Pedidos Orientada a Eventos

API em Python (FastAPI) com DynamoDB, Kafka, workers e observabilidade.

## Estrutura

```
services/
  orders-api/           # API REST (FastAPI)
  order-worker/         # simula o pagamento dos pedidos
  notification-worker/  # registra notificações
schemas/v1/             # JSON Schemas dos eventos
infra/                  # configurações de infraestrutura (Prometheus etc.)
```

## Como rodar

Pré-requisito: [uv](https://docs.astral.sh/uv/getting-started/installation/) instalado.

```bash
git clone https://github.com/gugaparente/order-platform.git
cd order-platform
uv sync --all-packages
```

O `uv sync` baixa o Python 3.13 (se precisar), cria o ambiente virtual em `.venv/`
e instala as dependências de todos os serviços, exatamente nas versões do `uv.lock`.
