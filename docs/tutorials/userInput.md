# User Input
<b>Situação:</b> Necessita de mais implmentações base

<b>Objetivo:</b> Testar a implemntação Oberon com alguns inputs de usuário.

<b>Funcionalidades usadas:</b> READFILE, STRINGTOINT, STRINGTOREAL.

## Descrição do problema

Queremos implementar a entrada de usuário. Para isso utilizamos o READFILE() para ler um arquivo .txt e retornar uma String, 
daí podemos tranformar a String nos tipos de valores que queremos, REAL e INTEGER.

## Código Exemplo

```
MODULE BeeBanknoteIntUser;


TYPE
	intArray = ARRAY 7 OF INTEGER

VAR
	banknotesValues, banknotesNeeded: intArray;
	value, valueUserInt1, valueUserInt2: INTEGER;
	valueUser: STRING;
	i, v: INTEGER;

BEGIN
	value := 576.73;
	i := 0;

	valueUser := READFILE("src\test\resources\userInput\beecrowdint");
	
	valueUserInt1 := STRINGTOINT(valueUser);
	
	banknotesValues[0] := valueUserInt1;
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

## Problemas

Quando o arquivo possui apenas uma variável utilizável, como se pode ver no arquivo src\test\resources\userInput\beecrowdint a seguir:

```
100
```

não possuimos problemas, já que é apenas uma variável, mas não queremos criar vários .txt apenas para uma variável.

## Possibilidades de Implementação

### Função que retorne um array de String para a implementação Oberon.

Uma função que retorne um array de Strings ou de Interios para o usuário tornaria ainda mais possível implementar algortimos em Oberon.
Tentativa de código para isso em src\main\scala\br\unb\cic\oberon\stdlib\StandardLibrary.scala

```
 /* Tentnativa de função que retorne um array de Inteiros, 
  def listInt = Procedure(
    "LISTINT",
    List(ParameterByValue("x",StringType)),
    Some(ArrayType(2, StringType)),
    List(),
    List(),
    SequenceStmt(
      List(MetaStmt(() => ReturnStmt(ArrayValue(Value, ArrayType(2, StringType))(readf(env.lookup(name = "x").get.asInstanceOf[StringValue].value   )))))
      
    )
  )
  */
```
ERRO: ArrayType e ArrayValue não é bem reconhecido.

### Input por meio do terminal

Como outras linguagens de programação, é possível de se digitar os inputs necessários para um algortimo por meio do terminal.
