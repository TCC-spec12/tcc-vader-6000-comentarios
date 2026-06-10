# Metodologia da análise VADER

## Fonte e recorte dos dados

A análise utilizou comentários públicos de três comunidades do Reddit relacionadas à área de tecnologia:

- `r/programming`;
- `r/cscareerquestions`;
- `r/devops`.

O recorte temporal compreendeu o período de 2021 a 2024. A amostra final foi composta por 6.000 comentários, distribuídos igualmente entre as três comunidades, com 2.000 comentários por subreddit.

## Coleta e seleção

A coleta foi realizada por meio de acesso histórico aos dados do Reddit. Após a obtenção dos registros, foram removidos comentários apagados, removidos, duplicados ou sem conteúdo textual suficiente.

Em seguida, foi realizada uma seleção aleatória e equilibrada de 2.000 comentários por comunidade, totalizando 6.000 textos.

## Análise de sentimentos

A análise foi realizada com o VADER (*Valence Aware Dictionary and sEntiment Reasoner*), ferramenta de análise de sentimentos adequada a textos curtos e informais de redes sociais.

Para cada comentário, foram calculados:

- `neg`: proporção de sentimento negativo;
- `neu`: proporção de conteúdo neutro;
- `pos`: proporção de sentimento positivo;
- `compound`: pontuação geral do sentimento.

A classificação final considerou:

- `compound <= -0,05`: negativo;
- `-0,05 < compound < 0,05`: neutro;
- `compound >= 0,05`: positivo.

## Resultados gerados

- `resultados_vader_6000.csv`;
- `resumo_sentimentos_6000.csv`;
- `frequencia_termos_6000.csv`;
- `grafico_sentimentos_6000.png`;
- `grafico_termos_6000.png`;
- `registro_execucao_6000.json`.

## Observação de reprodutibilidade

Esta execução representa uma reconstrução técnica posterior da metodologia descrita no TCC. Ela mantém o mesmo recorte de comunidades, período, quantidade de comentários e aplicação do VADER, mas não garante que os 6.000 comentários sejam exatamente os mesmos da amostra original, que não foi preservada.
