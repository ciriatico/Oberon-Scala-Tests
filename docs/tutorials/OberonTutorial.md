# Oberon Tutorial

<b>Objetivo:</b> Tutorias introdutório que explique .

<b>Funcionalidades implementadas até a criação deste tutorial:</b> INC, DEC, ABS, ODD, CEIL, 
FLOOR, ROUND, INTTOFLOAT, POWER, SQRROOT, CEIL, READFILE, WRITEFILE, APPENDFILE, STRINGTOINT, STRINGTOFLOAT.

<b>Link para um vídeo explicativo(inglês)<b>: https://www.youtube.com/watch?v=IyYRzpxJaaE

## Código Exemplo

```
MODULE BeeBanknoteInt;


TYPE
	intArray = ARRAY 7 OF INTEGER

VAR
	banknotesValues, banknotesNeeded: intArray;
	value: INTEGER;
	i, v: INTEGER;

BEGIN
	value := 576.73;
	i := 0;

	banknotesValues[0] := 100;
	banknotesValues[1] := 50;
	banknotesValues[2] := 20;
	banknotesValues[3] := 10;
	banknotesValues[4] := 5;
	banknotesValues[5] := 2;
	banknotesValues[6] := 1;

	FOREACH v IN banknotesValues
		banknotesNeeded[i] := FLOOR(value/v);
		value := value - v*banknotesNeeded[i];
		INC(i)
	END
END

END BeeBanknoteInt.
```

## Como implementar um algoritmo em Oberon

### MODULE

Primeiro é necessário criar o ```MODULE``` . Com o mesmo nome do arquivo em está o algoritmo. como ```MODULE BeeBanknoteInt;```

### TYPE

Caso queira arrays ou variavéis tipo ```RECORD``` é necessário criar o procedimento ```TYPE``` e iniciliazar as variavéis necessárias. como 

```
TYPE
	realArray = ARRAY 12 OF REAL
  intArray = ARRAY 12 OF INTEGER
  type4 = RECORD
    v1, v2: INTEGER;
  END
  p : POINTER TO INTEGER;
```

### VAR

Para inicialização de variavéis, cria-se o procedimento ```VAR```. Como em 

```
VAR
	banknotesValues, banknotesNeeded: intArray;
	value: INTEGER;
	i, v: INTEGER;
```

### BEGIN END

Os dois procedimentos ```BEGIN``` e ```END```. começam e finalizam o algoritmo, respectivamente. Como é possível ver no código exemplo. O ```END```
também é utilizado para finalizar expressões como o ```FOR EACH```. Note que a expressão ou variavel que vier antes do ```END``` não
pode possuir ```;``` no final, como se pode ver no Código-exemplo acima.

## Funções em Oberon atuais

```INC(x)``` Função que incrementa em 1 a variavél escolhida. Exemplo: BeeBanknoteIntUser.

```DEC(x)``` Função que decrementa em 1 a variavél escolhida. Exemplo: DECTest.

```ABS(x)``` Função que retorna o valor absoluto da variavél. Exemplo: ABSTest.

```ODD(x)``` Função que retorna caso o valor seja ímpar. Exemplo: ODDTest.

```CEIL(x)``` Função que obtém um número inteiro maior ou igual a um determinado número, arredondando o número fornecido. Exemplo: CEILTest.

```FLOOR(x)``` Função que retorna um número float que é menor ou igual ao número float fornecido. Exemplo: FLOORTest.

```RND(x)``` Função que arredonda o número escolhido para um número inteiro. Exemplo: RNDTest.

```FLT(x)``` Função que tranforma um valor INTEGER em um valor FLOAT. Exemplo: FLTTest.

```POW(x, y)``` Função que retorna x elevado a y. Exemplo: POWTest.

```SQR(x)``` Função que retorna a raiz quadrada da variavél. Exemplo: SQRTest.

```READFILE(x)``` Função que retorna em uma STRING o contéudo de um arquivo .txt. Exemplo: READFILETest.

```WRITEFILE(x, y)``` Função que escreve no arquivo com path (x) o contéudo (y). Exemplo: WRITEFILETest.

```APPENDFILE(x, y)``` Função que adiciona o mqruivo com path (x) o contéudo (y). Exemplo: APPENDFILETest.

```STRINGTOINT(x)``` Função que tranforma um valor STRING em um valor INTEGER. Exemplo: STRINGTOINTTest.

```STRINGTOREAL(x)``` Função que tranforma um valor STRING em um valor FLOAT. Exemplo: STRINGTOREALTest.



