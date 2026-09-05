# Roteiro do vídeo — CardioIA Fase 2

**Duração-alvo:** 3min20s a 3min50s.

## 0:00–0:20 — Abertura
“Este é o projeto CardioIA da Fase 2. O objetivo foi aplicar processamento de linguagem natural em duas etapas: primeiro, identificar sintomas e sugerir um possível diagnóstico a partir de relatos simulados; depois, classificar frases médicas entre baixo e alto risco usando machine learning.”

## 0:20–1:35 — Parte 1
Mostrar rapidamente:
- `frases_pacientes.txt`
- `mapa_sintomas.csv`
- `01_extracao_diagnostico.ipynb`

Fala sugerida:
“Criamos dez relatos simulados de pacientes e um mapa de conhecimento que relaciona expressões, sintomas e possíveis diagnósticos. O código normaliza o texto, procura os termos cadastrados e soma pesos para as doenças associadas. Dessa forma conseguimos identificar os sintomas encontrados e apresentar a hipótese com maior pontuação. A abordagem é simples, explicável e adequada ao objetivo didático.”

Execute/mostre a tabela final com os 10 resultados.

## 1:35–2:50 — Parte 2
Mostrar:
- `base_risco.csv`
- `02_classificador_risco.ipynb`

Fala sugerida:
“Na segunda parte criamos uma base simulada e balanceada com 120 frases, metade de baixo risco e metade de alto risco. Dividimos a base em treino e teste, transformamos os textos em vetores com TF-IDF e treinamos uma Regressão Logística. O modelo foi avaliado em frases que não participaram do treinamento.”

Mostrar a célula da acurácia.

“Na execução final, a acurácia foi de 100.00%. Também verificamos a matriz de confusão e o relatório de classificação.”

## 2:50–3:30 — Limitações e conclusão
“Como a base é sintética, pequena e utiliza vocabulário controlado, esse resultado não pode ser interpretado como desempenho clínico. O modelo aprende padrões lexicais e pode apresentar distorções quando recebe formas de escrita diferentes das usadas no treinamento. Em um cenário real seriam necessários dados representativos, validação médica e uma análise mais ampla de vieses.”

“Com isso, o projeto demonstra todo o fluxo solicitado: preparação dos textos, extração por regras, TF-IDF, treinamento, teste e avaliação do classificador.”

## 3:30–3:40 — Encerramento
Mostrar a página inicial do repositório/README e encerrar.
