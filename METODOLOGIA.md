# Metodologia da análise VADER

## Fonte e recorte dos dados

A etapa empírica utilizou dados históricos públicos do Reddit relacionados ao Pushshift Reddit Dataset.

Foram consideradas as comunidades `r/programming`, `r/cscareerquestions` e `r/devops`, no período de 2021 a 2024.

A amostra final foi composta por 6.000 comentários, distribuídos igualmente entre as três comunidades, com 2.000 comentários por subreddit.

## Seleção e preparação

Foram considerados comentários com conteúdo textual disponível, pertencentes ao período e às comunidades definidas no estudo.

O procedimento de preparação incluiu:

* exclusão de comentários apagados ou removidos;
* eliminação de registros duplicados;
* verificação do período de publicação;
* organização por comunidade;
* anonimização dos identificadores;
* seleção equilibrada dos comentários.

## Aplicação do VADER

A análise de sentimentos foi realizada com o método VADER, desenvolvido para avaliar a polaridade emocional em textos curtos e informais.

Para cada comentário, foram produzidos os indicadores `neg`, `neu`, `pos` e `compound`.

A classificação final adotou:

* `compound <= -0,05`: negativo;
* `-0,05 < compound < 0,05`: neutro;
* `compound >= 0,05`: positivo.

## Análise complementar

Além da polaridade geral, foram observadas expressões associadas a estresse, sobrecarga, ansiedade, exaustão, prazos, incidentes técnicos e burnout.

A frequência dos termos foi utilizada como apoio à interpretação qualitativa dos padrões linguísticos encontrados.

## Limitações

O VADER identifica polaridade linguística e não realiza diagnóstico psicológico. Os resultados devem ser interpretados como tendências presentes nos textos analisados.
