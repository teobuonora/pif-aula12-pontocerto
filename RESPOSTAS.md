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
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |

## Desafio 6 — Haskell × C

<!-- Cite duas diferenças entre o calculaPontos em Haskell e o calculaPontos em C. -->

## Evidência de execução

Saída do `main` de `fidelidade.hs`:

```text
(cole aqui)
```

Saída do `main` de `revisao.hs` (depois de corrigido):

```text
(cole aqui)
```

Saída de `pontocerto.c`:

```text
(cole aqui)
```
