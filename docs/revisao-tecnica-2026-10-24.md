# Revisão técnica do portfólio — 24/10/2026

## Escopo

Leitura da estrutura dos repositórios públicos, do README do portfólio e dos módulos selecionados do AI Business Agent; execução local dos cinco testes existentes do projeto de visão computacional. Esta revisão não é uma auditoria completa nem uma validação das integrações comerciais.

## Visão computacional: execução reproduzida

Foram obtidos os arquivos do GitHub e executados em ambiente virtual separado:

- Python 3.12.
- NumPy 1.26.4.
- opencv-python-headless 4.10.0.84.
- Comando: `python -m unittest discover -s tests -v`.
- Resultado: **5 testes executados, 5 aprovados**.

Verificações: extração das classes esperadas e repetição da extração; processamento de ambas as classes com registro de imagem corrompida; formato da saída e preservação de bordas internas; rejeição da saída dentro da entrada; fallback sinalizado para revisão.

A mensagem de erro relativa a uma imagem corrompida é esperada no teste que verifica o tratamento dessa falha.

Arquivos usados, identificados pelos hashes dos blobs do GitHub:

| Arquivo | SHA do blob |
| --- | --- |
| `preprocess.py` | `a4aa43b5023902a161c6381848a3d2594cabcd86` |
| `prepare_dataset.py` | `12952cd1f28e8219df977e3dae24bde34e24818d` |
| `tests/test_pipeline.py` | `0df7aa6bc1aff9fd4442ae934cec9a23ea623b2a` |
| `requirements.txt` | `2d34d055477468ac78decb7984f09ed640707d84` |

**Limite:** os testes usam entradas sintéticas e temporárias. O lote original de 1.300 imagens não foi executado nesta revisão. Não foram medidas acurácia de classificação, IoU de segmentação nem preservação de microdefeitos.

## AI Business Agent: evidências e pendências

### 1. Previsão baseada na ordem das linhas

Em [ml/sales_forecast.py](https://github.com/fernandababeto-byte/ai-business-agent/blob/main/ml/sales_forecast.py), blob `b734528ac4611c48540698e1be64ad4081bc92e5`, o método cria `periodo = df.index + 1` e ajusta uma regressão linear à coluna `vendas`. Não exige datas, frequência temporal nem avaliação fora da amostra.

A mudança da ordem das linhas pode alterar a extrapolação. Dados por categoria não devem ser interpretados como períodos temporais. Antes de divulgar previsão de vendas validada, definir a unidade temporal, ordenar e agregar o histórico, separar treino e avaliação e comparar com uma referência simples.

### 2. Linha de base apresentada como previsão inteligente

Em [dashboard/sections/forecast_section.py](https://github.com/fernandababeto-byte/ai-business-agent/blob/main/dashboard/sections/forecast_section.py), blob `663c5c9982d485962b3654139289198fc537d06b`, a função repete `average_revenue` seis vezes. O gráfico usa o rótulo “Forecast IA” e a seção “Previsão Inteligente de Receita”.

Esse cálculo é uma linha de base constante. A interface deve explicar a hipótese e a unidade do valor antes de exibi-lo como projeção mensal. A revisão leu a função; não executou a interface nem confirmou todos os caminhos que a chamam.

### 3. Recursos existentes e roteiro futuro

A árvore contém módulos de autenticação, banco de dados, cobrança, Shopify e arquivos Docker. O README ainda inclui vários desses temas no roteiro futuro. Corrigir a documentação por estado: implementação presente, configuração necessária, validação realizada e melhoria planejada.

A presença de arquivos não confirma que os fluxos funcionem de ponta a ponta. Não foram usados serviços pagos, credenciais de clientes, cobranças reais ou lojas reais nesta revisão.

### 4. Validação automatizada

Não foi encontrada uma suíte de testes ou configuração de CI na árvore examinada do AI Business Agent. Isso se refere aos arquivos versionados consultados, não a testes que possam existir fora do repositório.

Prioridades: validação de dados de entrada; isolamento entre clientes; autenticação e autorização; assinatura e repetição de eventos de cobrança; rotas Shopify; comportamento dos cálculos com dados ausentes.

## Portfólio

A estrutura real de `ai-portfolio` contém README, requisitos e um `src/main.py` que imprime “Hello AI Portfolio”. A revisão substitui a descrição de uma aplicação extensa por um índice dos projetos reais, com links e limites explícitos.

## Próximas entregas

1. Gravar ou preparar uma demonstração do pipeline de imagens usando dados com permissão de divulgação.
2. Acrescentar uma avaliação de segmentação com máscaras anotadas e um método de referência.
3. Validar a semântica temporal do AI Business Agent antes de alegar desempenho preditivo.
4. Atualizar os artigos e páginas profissionais a partir dessas evidências.
