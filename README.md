# Análise de sentimentos com VADER aplicada a comentários de comunidades de tecnologia

Este repositório apresenta a implementação computacional da metodologia descrita no trabalho **“O Papel da Inteligência Artificial na Redução do Estresse em Equipes de Desenvolvimento de Software”**.

O objetivo da análise foi identificar padrões linguísticos relacionados a estresse ocupacional, ansiedade, sobrecarga, frustração, exaustão e burnout em comentários publicados por usuários de comunidades online da área de tecnologia.

## Base de análise

A amostra utilizada contém **6.000 comentários**, distribuídos igualmente entre três comunidades do Reddit:

* `r/programming`: 2.000 comentários;
* `r/cscareerquestions`: 2.000 comentários;
* `r/devops`: 2.000 comentários.

O recorte temporal compreende o período de **2021 a 2024**.

Os comentários foram selecionados por sua relação com desenvolvimento de software, carreira em tecnologia, pressão por prazos, sobrecarga de trabalho, incidentes técnicos, ansiedade, estresse e esgotamento profissional.

## Processamento dos dados

A preparação dos textos incluiu:

* remoção de comentários apagados ou removidos;
* exclusão de registros duplicados;
* verificação do período de publicação;
* organização por comunidade;
* anonimização dos identificadores;
* seleção equilibrada de 2.000 comentários por comunidade.

Os nomes dos usuários não foram incluídos nos arquivos públicos.

## Aplicação do VADER

A análise de sentimentos foi realizada com o método **VADER — Valence Aware Dictionary and sEntiment Reasoner**, ferramenta adequada para textos curtos e informais publicados em redes sociais.

Para cada comentário, foram calculados quatro indicadores:

* `neg`: proporção de sentimento negativo;
* `neu`: proporção de conteúdo neutro;
* `pos`: proporção de sentimento positivo;
* `compound`: pontuação geral do sentimento predominante.

A classificação final considerou os seguintes critérios:

* `compound <= -0,05`: sentimento negativo;
* `-0,05 < compound < 0,05`: sentimento neutro;
* `compound >= 0,05`: sentimento positivo.

O VADER foi utilizado como ferramenta de identificação de tendências linguísticas e emocionais. Os resultados não representam diagnóstico psicológico dos usuários.

## Termos analisados

Também foram observadas expressões associadas ao contexto de estresse ocupacional, como:

* `burnout`;
* `stress`;
* `deadline`;
* `overworked`;
* `workload`;
* `tired`;
* `exhausted`;
* `anxious`;
* `pressure`;
* `incident`;
* `bug`;
* `crash`.

A frequência desses termos foi utilizada como apoio à interpretação dos padrões presentes nos comentários.

## Arquivos do repositório

* `resultados_vader_6000.csv`: pontuações individuais e classificação dos 6.000 comentários;
* `resumo_sentimentos_6000.csv`: quantidades e percentuais por comunidade e no total;
* `frequencia_termos_6000.csv`: frequência dos termos relacionados ao estresse;
* `grafico_sentimentos_6000.png`: distribuição geral dos sentimentos;
* `grafico_termos_6000.png`: frequência dos principais termos;
* `registro_execucao_6000.json`: informações técnicas da execução;
* `METODOLOGIA.md`: descrição detalhada dos procedimentos;
* `Executar_VADER_6000_Comentarios_Colab.ipynb`: notebook com o processo de coleta, seleção, análise e geração dos resultados.

## Reprodutibilidade

O notebook permite consultar o procedimento utilizado, verificar os critérios de seleção e executar novamente a análise.

A correspondência exata com a amostra individual inicialmente descrita no trabalho não pode ser confirmada, pois aquela base não foi preservada. Entretanto, esta execução mantém o mesmo recorte de comunidades, período, quantidade de comentários e aplicação do método VADER apresentados no estudo.

## Referência do VADER

HUTTO, C. J.; GILBERT, E. E. VADER: A Parsimonious Rule-based Model for Sentiment Analysis of Social Media Text. In: INTERNATIONAL AAAI CONFERENCE ON WEBLOGS AND SOCIAL MEDIA, 8., 2014.
