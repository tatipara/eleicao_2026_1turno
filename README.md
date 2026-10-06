# Votos para Presidente — Eleições 2026 (1º Turno) por Município e Zona Eleitoral
# eleicao_2026_1turno
Dados do TSE do 1º turno da eleição de 2026

## Descrição
Script em Python, desenvolvido para o Google Colab, que coleta os dados oficiais de votação para Presidente da República no 1º turno das Eleições 2026, organizados por município e por zona eleitoral. O código acessa diretamente os arquivos JSON de divulgação de resultados do Tribunal Superior Eleitoral (TSE), processa a estrutura hierárquica dos dados (seção → zona → município) e exporta tabelas prontas para análise estatística e geoespacial.

## Dados utilizados
- **Fonte:** Tribunal Superior Eleitoral (TSE) — Sistema de Divulgação de Resultados, disponível em `https://resultados.tse.jus.br`
- **Período:** 1º turno das Eleições Gerais de 2026 (04 de outubro de 2026)
- **Região:** Todos os municípios brasileiros e localidades do voto no exterior
- **Formato:** JSON (dados brutos do TSE) → CSV (dados processados)

## Estrutura do código
- `votos_presidente_2026_municipios.py`: script principal de coleta, processamento e exportação dos dados
- `tse2026/raw/`: pasta com os arquivos JSON brutos baixados por município, para fins de auditoria e reprocessamento
- `tse2026/presidente_2026_municipios_long.csv`: uma linha por município × candidato
- `tse2026/presidente_2026_municipios_wide.csv`: uma linha por município, com uma coluna por candidato
- `tse2026/presidente_2026_zonas_long.csv`: uma linha por município × zona eleitoral × candidato
- `tse2026/presidente_2026_resumo_municipios.csv`: dados de eleitorado, comparecimento, abstenção, brancos e nulos por município

## Requisitos
- Python 3.x
- Bibliotecas: `pandas`, `requests`, `tqdm`

## Como executar
1. Abra o script no Google Colab
2. Execute a célula (Shift+Enter) e aguarde a conclusão do download paralelo dos municípios
3. Ajuste os parâmetros no início do script conforme necessário (`ELEICAO` para trocar de turno, `UFS` para filtrar estados, `THREADS` para controlar a velocidade de requisições)
4. Os arquivos de saída ficam disponíveis na pasta `/content/tse2026/`

## Autor
[Tatiana Pará] | [IFPA/UEPA/MENINASDAGEO/OSGeoBrasil]
