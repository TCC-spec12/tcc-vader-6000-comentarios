# Análise de sentimentos com VADER em comunidades de tecnologia

Este repositório apresenta os procedimentos computacionais e os resultados da análise de sentimentos desenvolvida no trabalho **“O Papel da Inteligência Artificial na Redução do Estresse em Equipes de Desenvolvimento de Software”**.

## Base de análise

A análise utilizou dados históricos públicos do Reddit, relacionados ao conjunto de dados Pushshift Reddit Dataset, considerando comentários publicados entre 2021 e 2024.

A amostra foi composta por 6.000 comentários, distribuídos igualmente entre as seguintes comunidades:

* `r/programming`: 2.000 comentários;
* `r/cscareerquestions`: 2.000 comentários;
* `r/devops`: 2.000 comentários.

Os registros foram organizados de acordo com o período, a comunidade de origem e a disponibilidade do conteúdo textual. Identificadores pessoais não foram incluídos nos arquivos públicos.

## Análise de sentimentos

A análise foi realizada por meio do método VADER — *Valence Aware Dictionary and sEntiment Reasoner* — adequado à interpretação de sentimentos em textos curtos e informais publicados em ambientes digitais.

Para cada comentário, foram calculados os seguintes indicadores:

* `neg`: proporção de sentimento negativo;
* `neu`: proporção de conteúdo neutro;
* `pos`: proporção de sentimento positivo;
* `compound`: pontuação geral do sentimento predominante.

A classificação considerou os seguintes critérios:

* `compound <= -0,05`: negativo;
* `-0,05 < compound < 0,05`: neutro;
* `compound >= 0,05`: positivo.

O VADER foi empregado para identificar tendências linguísticas e emocionais nos textos. Os resultados não representam diagnóstico psicológico dos usuários.

## Recorte temático

A interpretação dos resultados considerou manifestações relacionadas a:

* estresse ocupacional;
* sobrecarga de trabalho;
* pressão por prazos;
* ansiedade;
* exaustão;
* frustração técnica;
* burnout;
* incidentes e falhas em sistemas.

Também foram observados termos como `stress`, `burnout`, `deadline`, `overworked`, `tired`, `anxious`, `pressure`, `incident`, `bug` e `crash`.

## Arquivos disponíveis

* `resultados_vader_6000.csv`: pontuações e classificações dos comentários;
* `resumo_sentimentos_6000.csv`: quantidades e percentuais dos sentimentos;
* `frequencia_termos_6000.csv`: frequência dos termos selecionados;
* `grafico_sentimentos_6000.png`: distribuição das classificações;
* `grafico_termos_6000.png`: frequência dos termos;
* `registro_execucao_6000.json`: informações técnicas da execução;
* `METODOLOGIA.md`: descrição dos procedimentos metodológicos;
* `Executar_VADER_6000_Comentarios_Colab.ipynb`: notebook em Python utilizado no processamento.

## Reprodutibilidade

O notebook disponibilizado permite verificar os critérios empregados, executar novamente os procedimentos e gerar os arquivos de resultados.

A análise mantém o recorte metodológico apresentado no trabalho: comunidades de tecnologia, período de 2021 a 2024, amostra de 6.000 comentários e aplicação do método VADER.

## Referência

HUTTO, C. J.; GILBERT, E. E. VADER: A Parsimonious Rule-based Model for Sentiment Analysis of Social Media Text. In: INTERNATIONAL AAAI CONFERENCE ON WEBLOGS AND SOCIAL MEDIA, 8., 2014.

