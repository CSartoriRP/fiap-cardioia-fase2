# CardioIA — Fase 2 — Ano 2

Projeto acadêmico desenvolvido para a Fase 2 do CardioIA.


## Continuidade com a Fase 1

A Fase 1 do CardioIA estabeleceu uma base multimodal com dados clínicos estruturados, textos cardiovasculares e imagens de ECG:

https://github.com/CSartoriRP/fiap-cardioia-fase1

Nesta Fase 2, a solução preserva o mesmo domínio cardiológico e avança para NLP e classificação textual.

O dataset numérico da Fase 1 é estruturado, enquanto esta atividade solicita explicitamente **frases médicas rotuladas**. Por isso, para a Parte 2 foi criada uma base textual simulada e compatível com o domínio do projeto, opção prevista pelo enunciado. Essa decisão mantém a continuidade conceitual sem converter artificialmente registros numéricos em relatos de pacientes.

## Objetivo

A solução cobre duas etapas:

1. **Extração de sintomas e sugestão de possível diagnóstico por regras**, usando relatos simulados e um mapa de conhecimento sintoma → doença.
2. **Classificação de risco em textos médicos**, usando TF-IDF e Regressão Logística.

> **Aviso:** todos os dados são simulados e este projeto tem finalidade exclusivamente acadêmica. Não deve ser utilizado para diagnóstico ou decisão clínica real.

## Estrutura

```text
CardioIA_Fase2/
├── README.md
├── requirements.txt
├── data/
│   ├── frases_pacientes.txt
│   ├── mapa_sintomas.csv
│   └── base_risco.csv
└── notebooks/
    ├── 01_extracao_diagnostico.ipynb
    └── 02_classificador_risco.ipynb
```

## Parte 1 — Extração de sintomas

O arquivo `frases_pacientes.txt` contém 10 relatos simulados.

O arquivo `mapa_sintomas.csv` relaciona:
- expressões presentes nos relatos;
- sintoma normalizado;
- possível diagnóstico;
- peso da associação.

O notebook `01_extracao_diagnostico.ipynb`:
- lê os 10 relatos;
- normaliza o texto;
- identifica sintomas por correspondência de expressões;
- soma os pesos associados a cada diagnóstico;
- apresenta o possível diagnóstico com maior pontuação.

### Diagnósticos contemplados
- Síndrome coronariana aguda
- Angina estável
- Arritmia cardíaca
- Insuficiência cardíaca
- Hipertensão arterial

## Parte 2 — Classificação de risco

O arquivo `base_risco.csv` contém **120 frases médicas simuladas e balanceadas**:
- 60 classificadas como `baixo risco`
- 60 classificadas como `alto risco`

Pipeline utilizada:

1. divisão estratificada entre treino e teste;
2. vetorização com **TF-IDF**;
3. treinamento com **Regressão Logística**;
4. previsão no conjunto de teste;
5. avaliação por acurácia, matriz de confusão e relatório de classificação.

### Resultado obtido nesta versão

**Acurácia no conjunto de teste: 100.00%**

A acurácia elevada deve ser interpretada considerando que o conjunto é pequeno, simulado e construído com padrões lexicais controlados. Portanto, ela não representa desempenho clínico real.

## Tecnologias

- Python 3
- pandas
- scikit-learn
- Jupyter Notebook

## Como executar

### 1. Criar ambiente virtual (opcional)

```bash
python -m venv .venv
```

### 2. Ativar o ambiente

Windows:

```bash
.venv\Scripts\activate
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### 3. Instalar dependências

```bash
pip install -r requirements.txt
```

### 4. Abrir os notebooks

```bash
jupyter notebook
```

Execute primeiro:

`notebooks/01_extracao_diagnostico.ipynb`

Depois:

`notebooks/02_classificador_risco.ipynb`

## Análise de padrões e possíveis distorções

O classificador aprende principalmente padrões de vocabulário presentes no dataset. Como a base é sintética, há risco de desempenho artificialmente alto e pouca capacidade de generalização.

Entre as limitações:
- ausência de dados clínicos reais;
- vocabulário controlado;
- ausência de diversidade demográfica;
- ausência de erros de digitação e regionalismos;
- ausência de contexto clínico completo;
- rótulos didáticos, não validados por especialistas.

Uma aplicação real exigiria dados representativos, validação médica, métricas adicionais e avaliação formal de vieses.

## Integrantes

- **Nome:** PREENCHER
- **RM:** PREENCHER

## Vídeo

YouTube (não listado, até 4 minutos):

**PREENCHER_LINK_DO_VIDEO**
