# Teste stringToInt
<b>Situação:</b> Sucesso

<b>Objetivo:</b> Tranformar um valor String em um valor Integer.

<b>Funcionalidades usadas:</b> ReturnStmt, Procedure, ParameterByValue, MetaStmt, Lits. Implementado em Scala.

## Descrição do problema

Com a possibilidade de entrada de usuário por meio do READFILE(), necessitamos do retorno das variavéis se String para Integer.
src\main\scala\br\unb\cic\oberon\stdlib\StandardLibrary.scala - File com a implementação em Scala.
src\test\resources\stdlib\STRINGTOINTTest.oberon - Arquivo de teste.

## Código-exemplo

```
MODULE STRINGTOINTTest;

VAR
  x : STRING;
  y : INTEGER;
  z : INTEGER;
  w : STRING;

BEGIN
  w := "2";
  x := "-8";
  y := STRINGTOINT(x);
  z := STRINGTOINT(w)
END
END STRINGTOINTTest.
```

## Funcionalidades testadas
### stringToInt

Função em Oberon, implementado em Scala, que retorna um Integer a partir de uma String.
