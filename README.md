# Fernanda Babeto | Portfólio de Inteligência Artificial

Projetos de Python, preparação de dados, visão computacional e aplicações de IA para negócios.

Sou Fernanda Caroline Babeto de Souza, pós-graduanda em Inteligência Artificial pela Universidade Tecnológica Federal do Paraná (UTFPR), cirurgiã-dentista e especialista em Ortodontia. Minha trajetória conecta planejamento, análise de problemas e desenvolvimento técnico, com foco na transição para tecnologia e empreendedorismo.

Este repositório organiza os projetos públicos e suas evidências. O código de cada projeto está no respectivo repositório; esta página funciona como índice do portfólio.

## Projetos em destaque

| Projeto | Problema e implementação | Estado e limites |
| --- | --- | --- |
| [Pré-processamento de imagens industriais](https://github.com/fernandababeto-byte/mini-projeto-visao-computacional) | Pipeline Python/OpenCV para padronizar imagens de peças fundidas, separar o objeto do fundo e realçar bordas. | Projeto acadêmico com testes e comparativo visual. Prepara imagens; não classifica defeitos. |
| [Preparação de dados de e-commerce](https://github.com/fernandababeto-byte/mini-projeto-olist-etl) | Limpeza de produtos e pedidos Olist com bibliotecas nativas de Python: CSV, expressões regulares e datas. | Projeto acadêmico de ETL. As regras refletem a atividade e precisam ser reavaliadas para outros conjuntos de dados. |
| [AI Business Agent](https://github.com/fernandababeto-byte/ai-business-agent) | Aplicação em desenvolvimento com API FastAPI, interface Streamlit e módulos para análise de negócios e integração Shopify. | Protótipo que exige configuração e validação das integrações. A existência do código não comprova operação em produção nem qualidade preditiva. |

## Comece pelo projeto de visão computacional

O projeto de imagens industriais reúne uma demonstração visual, decisões de implementação e testes que podem ser executados sem o conjunto original completo.

- [Código do pipeline](https://github.com/fernandababeto-byte/mini-projeto-visao-computacional/blob/main/preprocess.py)
- [Comparativo visual das etapas](https://github.com/fernandababeto-byte/mini-projeto-visao-computacional/blob/main/docs/comparativo_pipeline.jpg)
- [Testes automatizados](https://github.com/fernandababeto-byte/mini-projeto-visao-computacional/blob/main/tests/test_pipeline.py)
- [Relatório de validação original](https://github.com/fernandababeto-byte/mini-projeto-visao-computacional/blob/main/docs/relatorio_validacao.md)

O relatório original registra 1.300 imagens processadas e cinco testes aprovados. Esse é um resultado documentado no projeto, não uma medida de acurácia na detecção de defeitos. A reprodução do lote completo depende do conjunto de imagens original.

Para executar os testes, siga a instalação no README daquele projeto e rode:

```bash
python -m unittest discover -s tests -v
```

## Verificação técnica

Em 24/10/2026, os cinco testes existentes de visão computacional foram executados novamente com Python 3.12, NumPy 1.26.4 e OpenCV Headless 4.10.0.84: **todos passaram**. O lote de 1.300 imagens não foi repetido nesta revisão.

Veja o [relatório técnico e as próximas prioridades](docs/revisao-tecnica-2026-10-24.md).

## Direção de desenvolvimento

Meu interesse está em aplicações de IA para negócios em diferentes setores. A experiência em Odontologia e Ortodontia integra minha trajetória profissional; o desenvolvimento de produtos de IA não está restrito à saúde.

Prioridades técnicas:

1. Tornar as demonstrações reproduzíveis, com entradas de exemplo e instruções claras.
2. Documentar decisões, resultados e limitações de cada projeto.
3. Avaliar modelos em dados separados do treinamento e compará-los com referências simples.
4. Validar integrações e fluxos de usuário antes de apresentar um protótipo como produto pronto.

No AI Business Agent, o módulo `ml/sales_forecast.py` ajusta uma regressão à ordem das linhas; a seção `dashboard/sections/forecast_section.py` repete uma linha de base em seis posições. Esses componentes, isoladamente, não demonstram uma previsão temporal validada. A revisão técnica deve preceder alegações de precisão ou resultados comerciais.

## Formação e competências em desenvolvimento

- Especialização em Inteligência Artificial na UTFPR: em andamento, conforme a apresentação acadêmica deste portfólio.
- Formação em Odontologia e especialização em Ortodontia.
- Python, tratamento de dados e documentação técnica.
- OpenCV e pré-processamento de imagens.
- Aprendizado de máquina e avaliação de modelos.
- APIs e aplicações de dados para negócios.

As tecnologias utilizadas e as dependências de execução estão documentadas em cada projeto. Áreas de estudo não representam, por si só, experiência de produção.

## Perfil e publicações

- [LinkedIn](https://www.linkedin.com/in/fernanda-babeto-89146229a/)
- [Apresentação profissional](https://babetoortodontia.wordpress.com/)
- [Artigos sobre IA e Python](https://dominunventrue.blogspot.com/)
- [Repositórios no GitHub](https://github.com/fernandababeto-byte)

## Estrutura deste repositório

```text
README.md          # índice e apresentação dos projetos
requirements.txt   # dependências do esqueleto inicial
src/main.py        # ponto de partida: imprime "Hello AI Portfolio"
```

Este repositório ainda não contém uma aplicação de portfólio executável. Para executar uma demonstração, acesse o projeto específico e siga suas instruções.

---

**English summary:** Public portfolio by Fernanda Babeto, an Artificial Intelligence postgraduate student at UTFPR transitioning from Dentistry and Orthodontics to technology. Featured work covers industrial image preprocessing, e-commerce data preparation and a business AI prototype. Each project documents its scope and limitations; production readiness and predictive accuracy are not assumed.
