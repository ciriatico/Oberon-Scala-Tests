# Teste Bee2057_TimeZone
<b>Situação:</b> Sucesso

<b>Objetivo:</b> Testar IF, ELSEIF.

<b>Funcionalidades usadas:</b> IF,ELSEIF

## Descrição no beecrowd

<b>Link:</b> [2057 - Time zone][https://www.beecrowd.com.br/judge/en/problems/view/2057]

<b>Problema:</b> 

Neste problema, você deverá ler 3 valores S o horário de origem do voo, T tempo de viagem e F horario do local destino de diferença a S. Assim, calcular o horario de chegada no horario local do destino. 


## Código-exemplo

```
MODULE bee2057Time;

VAR

    S, T, F , ans: INTEGER;

BEGIN
    S :=  22;
    T :=  6;
    F :=  -2;

    ans := S + T + F;

    IF ans > 24 THEN
        ans := ans - 24

    ELSIF ans < 0 THEN
        ans := 24 - ans
    
    ELSIF ans < 24 THEN
        ans := ans
    END
END

END bee2057Time.compile
```

## Funcionalidades testadas
### Condição if e elseif

Para aplicar condição <b>IF</b>, é necessário fornecer um valor booleano entre parênteses, seguido da operação a ser realizada com THEN. Caso a condição não seja satisfeita, deve executar o que vem após ELSE.

É possível fazer condições IF aninhadas.

```
    IF ans > 24 THEN
        ans := ans - 24

    ELSIF ans < 0 THEN
        ans := 24 - ans
    
    ELSIF ans < 24 THEN
        ans := ans
    END
```

### Teste de capacidade da linguagem para exercicios adversos do Beecrownd
