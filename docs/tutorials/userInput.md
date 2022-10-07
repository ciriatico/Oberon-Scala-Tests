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

<details>
<p>
<summary><b><u>Teste unitário (em Scala)</u></b></summary>
<pre>
<code>
  test("BeeCrowd test of INTEGER banknotes with (User Input)") {
    val module = ScalaParser.parseResource("stmts/BeeBanknoteIntUser.oberon")

    assert(module.stmt.isDefined)

    assert(module.name == "BeeBanknoteIntUser")

    module.accept(interpreter)
    
    assert(interpreter.env.lookup("i") == Some(IntValue(7)))

    if (System.getProperty("os.name").split(" ")(0).contains("Windows"))
      assert(interpreter.env.lookup("path") == Some(StringValue("src\\test\\resources\\userInput\\beecrowdint")))
    else
      assert(interpreter.env.lookup("path") == Some(StringValue("src/test/resources/userInput/beecrowdint")))

    assert(evalArraySubscript("banknotesNeeded", 0) == IntValue(5))
    assert(evalArraySubscript("banknotesNeeded", 1) == IntValue(1))
    assert(evalArraySubscript("banknotesNeeded", 2) == IntValue(1))
    assert(evalArraySubscript("banknotesNeeded", 3) == IntValue(0))
    assert(evalArraySubscript("banknotesNeeded", 4) == IntValue(1))
    assert(evalArraySubscript("banknotesNeeded", 5) == IntValue(0))
    assert(evalArraySubscript("banknotesNeeded", 6) == IntValue(1))

  }
</code>
</pre>
</details>

## Funcionalidades testadas

### READFILE

Documentação já feita no teste [bee1018](bee1018.md#readfile).

### STRINGTOINT

Documentação já feita no teste [bee1018](bee1018.md#stringtoint).

### STRINGTOREAL

Documentação já feita no teste [bee1018](stringToReal.md#stringtoreal).
