# Projeto Final - Aprendizado Nao Supervisionado

Analise nao supervisionada de atrasos de voos usando o dataset Kaggle usdot/flight-delays.

## Objetivo

Investigar padroes latentes em dados de voos sem usar rotulos como alvo de treinamento, com foco em:

- reducao de dimensionalidade;
- agrupamento de amostras;
- comparacao de metodos e metricas internas;
- interpretacao critica dos resultados.

## Dataset

- Origem: Kaggle (usdot/flight-delays), arquivo flights.csv.
- Tipo de dado: tabular (operacao de voos).
- Numero de amostras: 5.819.079 linhas no dataset bruto.
- Numero de atributos: 31 colunas no dataset bruto.
- Rotulos: ha colunas binarias (ex.: CANCELLED, DIVERTED), mas nao sao usadas como alvo supervisionado.

## O que foi implementado no notebook

- Escolha e descricao do dataset:
	- exibicao de origem, arquivo, dimensao e periodo identificado.
	- dicionario de dados (tipo, ausentes, valores unicos).
- Preparacao e organizacao dos dados:
	- selecao de colunas numericas;
	- filtro por percentual de ausentes;
	- remocao de colunas sem variacao;
	- imputacao por mediana e padronizacao;
	- amostragem para viabilizar clustering.
- Analise exploratoria inicial (EDA):
	- estatisticas descritivas;
	- faltantes;
	- distribuicoes e correlacoes.
- Metodos de aprendizado nao supervisionado:
	- PCA (95% variancia) e PCA 2D para visualizacao;
	- t-SNE para visualizacao;
	- K-Means, DBSCAN e clustering hierarquico.
- Avaliacao e comparacao:
	- Silhouette Score, Davies-Bouldin e Dunn Index;
	- busca de hiperparametros (k no K-Means e eps no DBSCAN);
	- tabela comparativa final entre algoritmos.
- Visualizacao e interpretacao:
	- projecoes em PCA e t-SNE;
	- dendrograma hierarquico;
	- discussao dos resultados no fechamento.

## Resultado sintetico da execucao atual

- DBSCAN apresentou o melhor desempenho relativo entre os metodos testados na amostra usada.
- K-Means e hierarquico tambem encontraram estrutura, com menor qualidade interna.

## Aderencia aos requisitos da disciplina

- Escolha e descricao do dataset: Atendido.
- Preparacao e organizacao dos dados: Atendido.
- Analise exploratoria inicial: Atendido.
- Aplicacao de metodos nao supervisionados: Atendido.
- Avaliacao quantitativa/qualitativa: Atendido.
- Comparacao entre metodos/configuracoes: Atendido.
- Visualizacao e interpretacao: Atendido.
- Analise critica dos resultados: Atendido.

## Limitacoes e proximos passos

- Resultados dependem da amostragem e dos hiperparametros.
- Recomendado testar estabilidade com multiplas seeds/amostras e expandir busca de parametros.
- Opcional: incluir UMAP para comparacao adicional de separacao em baixa dimensionalidade.