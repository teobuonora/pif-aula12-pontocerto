# Respostas da dupla — Atividade PontoCerto

## Dupla

| Papel | Nome completo | Usuário do GitHub |
|---|---|---|
| Integrante 1 (dono do fork) |Téo Buonora |teobuonora |
| Integrante 2 (colaborador) |João Cassimiro |joaogabrielcassiimiro-png |

## Explicação da solução
A solução utiliza funções de primeira classe para tratar regras de negócio como dados. Em vez de duplicar a lógica de cálculo para cada campanha, passamos o comportamento (a função da regra) como argumento para uma função genérica (calculaPontos) ou criamos fábricas que retornam novas funções. Isso elimina repetição e facilita a criação de novas regras.
<!-- 3 a 5 linhas: como calculaPontos e as fábricas de campanhas eliminam a repetição de código? -->

## Desafio 2
Faz sentido usar lambdas porque são promoções temporárias de uso único. Como a regra só será executada naquele momento específico, evitamos poluir o código global nomeando funções que não serão reaproveitadas.
<!-- Por que, nas duas promoções de um dia, faz sentido usar lambda em vez de função nomeada? -->

## Desafio 3
Devolve uma função (especificamente, uma função que recebe um Int e devolve um Int). O comando :t confirma isso mostrando a assinatura: Int -> Int.
<!-- O que campanhaMultiplicadora 5 devolve? Um número ou outra coisa? Como o :t confirma isso? -->

## Desafio 4

**a)** Porque a ordem matemática importa. Aplicar a multiplicação e depois a soma (150 * 5) + 200 resulta em 950. Inverter a ordem aplica a soma primeiro e multiplica o total (150 + 200) * 5, resultando em 1750.<!-- Por que as duas ordens dão resultados diferentes? -->

**b)** O sistema deve aplicar a campanha multiplicadora primeiro e o bônus por último (ordem do item 1). Assim, o bônus de 200 pontos é somado ao final e fica protegido da multiplicação.<!-- Qual ordem garante que o bônus de aniversário não seja multiplicado? Por quê? -->

## Desafio 5 — revisão de código

| Erro | Função | O que estava errado | Como o GHC avisou (resumo da mensagem) | Como corrigimos |
|---|---|---|---|---|
| 1 |aplicaRegraDuasVezes |A assinatura indicava Int -> Int -> Int, dizendo que o primeiro argumento era um número comum, mas o código tentava usar ele como função. |Ocorreu um erro dizendo que não podia aplicar um Int como se fosse uma função (Expected a function of type... Actual type: Int). |Colocamos parênteses na assinatura para agrupar o tipo da função: (Int -> Int) -> Int -> Int. |
| 2 |fimDeSemana |A seta da lambda estava desenhada como => em vez de ->. |Erro de sintaxe acusando falha no parse (parse error on input =>). |Trocamos => pela seta correta de lambdas ->. |
| 3 |natal |A fábrica campanhaBonus foi guardada na variável sem o parâmetro (o valor do bônus). |Erro de tipo informando que a função esperava um tipo e recebeu outro que pedia mais um argumento (Couldn't match expected type). |Passamos o argumento 300 para a fábrica: natal = campanhaBonus 300. |
| 4 |promocaoAtual |Foi passado o argumento 100 diretamente na criação da variável. Isso fez ela ser calculada e virar um número (Int), mas a assinatura dizia que ela deveria ser uma função. |Erro de tipo informando que esperava uma função Int -> Int, mas encontrou um Int comum. |Removemos o 100, deixando apenas a função: promocaoAtual = pontosEmDobro. |

## Desafio 6 — Haskell × C
1. Em C, é necessário usar a sintaxe de ponteiros (*regra) explicitamente na declaração, enquanto em Haskell as funções são cidadãs de primeira classe com tipos nativos (Int -> Int).
2. Em C, os tipos e a implementação ficam juntos na declaração da função int calculaPontos(int (*regra)(int), int valor), enquanto em Haskell a assinatura de tipo fica em uma linha separada da lógica.
<!-- Cite duas diferenças entre o calculaPontos em Haskell e o calculaPontos em C. -->

## Evidência de execução

Saída do `main` de `fidelidade.hs`:

```text
120
240
170
240
80
160
130
240
170
750
350
100
55
950
1750
280
```

Saída do `main` de `revisao.hs` (depois de corrigido):

```text
40
100
400
200
```

Saída de `pontocerto.c`:

```text
160
130
250
300
```
