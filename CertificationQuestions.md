#### Why we define the `http.port` in the HTTP listener to deploy on cloudHub?
- To API manager register on API Manager...
- *Certa*: To ClouHub changes and allows http requests to your Listener receive external requests...

#### Dentro do ScatterGatter, temos dois flows, um demora 10 segundos e outros 20 segundos, qual tempo de execução geral ?
- *Certa*: 20 segundos (porque o flow só segue quanto o ultimo termina e ambos são processados em paralelo)

#### 3 questões em cima de escopo de variáveis, tendo o mesmo endpoint `localhost/api?color=red`. Dado o contexto que temos um flow pai que chama um flow externo via HTTP request, no `mainFlow` sentamos um variável, variando as perguntas em:
![](http://bit.ly/35SUkir)
- O que está acessível num logger no fim do `Main flow` (Payload / variável / QueryParam `color`)
- O que está acessível num logger no fim do `Child flow` (Payload / variável / QueryParam `color`)
- Nesse mesmo contexto mas **alterando o childFlow para um Flow Reference**, O que está acessível num logger no fim no `Child flow`, que possui um Logger no Fim? (Payload / variável / QueryParam `color`)

#### Ao configurar um globalHandler, onde devemos configurar para "começar a valer"?
- Property file
- Global element
- Nothing to do, is automatic
- ...

#### Um projeto está dando erro ao buildar (erro no console mostrando erro de build por não conseguir puxar uma dependencia), essa dependencia está num repositório do Mule. Obs: Esse mesmo projeto funcionou em outra máquina, o que podemos fazer para arrumar?
- Baixar a dependencia localmente
- Adicionar a dependencia no "HOME/bin" (algo assim)
- Deployar dependencia no repositório privado do mule
- Editar o pom.xml

#### Saida de um Scatter-Getter com 2 flows pararelos que setam variáveis?:
```
{
	`0` :{
		atributes...
		payload:
	},
	`1` :{
		atributes...
		payload:
	}
}
```

#### Qual path mínimo para configurar no ApiKit Router
- Certa: `/*`

#### Syntax para condição do Choice
- Certa: `#[XXX] == "US"`

#### Dado `RAML` exemplo, quantos métodos o APIKit gera?
- Fazer conta por endpoints, as opções mostram possíveis quantidades

#### Fluxo que lê `CSV`, em determinado ponto do flow tem um BreakPoint num Processor que é um `SELECT` no banco, em tempo de execução, o que o debug mostra?
- O arquivo `csv` todo
- O resultado da query
- ...

#### Um conector de escrita que escreve um payload JSON `{...}` num arquivo `CSV`, o que é escrito no arquivo?
- Certa: Um JSON, não importa o arquivo ser `csv`, importa a saida do TransformMessage que é um `application/JSON`

#### Como acessar URI Param no conector `HTTP Listener`?
- ${..}
- #[..]
- ...

#### Cenário: Dois times distintos perderam um tempo de 2 meses desenvolvendo uma API que no fim era a mesma, como isso poderia ter sido evitado:
- Se o C4E tivesse "monitorirado" isso

#### Dado um flow exemplo e feita a pergunta: O que poderia ser adicionado para adicionar persistencia de dados nesse flow?
- Apontar ObjecStore para a columa do Ultimo ID
- Configurar o WaterMark para a coluna com o Ultimo ID 

#### O que acontece se o conector sde DB nao achar nada no banco?
 - **Certa:** Volta array vazio

#### Como definir `type` no RAML?
- A ***alternativa certa*** é a que contem `types` no exemplo e **NÃO** `dataTypes` (essas duas opções são bem parecida mas a primeira é a certa). **Obs**: Import de arquivos externos no RAML é feito com `!include`

#### Mínimo necessário para deployar uma aplicação no CloudHub?
- Dependencias (e módulos) e Resources
- Só dependencias (e módulos)
- Só resources
- Nenhum dos dois
 
#### Qual vai ser a saida de `type of (payload)` se passarmos um xml em valor literal?
- *Certa*: String, porque apesar do valor ser em `XML`, não setamos o Mymmetype
 
#### Como importar/usar um módulos externo no `DW`?
```java
%dw 2.0
import modules::MyModule
output application/json
---
MyModule::myFunc("dataweave") ++ "name"
```

#### Syntax de como declarar/usar uma função no DW (fun)
```java
%dw 2.0
output application/json
fun toUpper(aString) = upper(aString)
---
toUpper("hello")
```

#### Qual a saída da função `map` no dataWeave
- Objeto
- Array
- ...

#### Se alterarmos a implementação da nossa API, não a nossa interface, o que as APIS que consumiam devem fazer pra se adaptrem as mudanças?
- *Certa*: Nada (porque o contrato não foi alterado, que é a interface)

#### Segundo a MuleSoft, qual as caracteristicas de uma modern api?
- *Certa*: ..."Alguma coisa"... para rápido feedback

#### Supondo que setamos 3 variáveis no nosso flow, qual estrutura podemos usar para acessar esses valores?
- Mule Event
- Mule Message
- Mule Event Attributes

#### Num exemplo temos 4 HTTP listeners que usam alguns Port and Host Name iguais e algumas propriedades são puxadas de um arquivo de config global, qual a quantidade Mínima de "algumas coisa, acho que é recurso" precisamos configurar nesse arquivo global para usar corretamente nos 4 HTTP Listeners?
- 1
- 2
- 3
- 4


## Questões de forma geral
- Todos os casos possíveis de erro Handler como:
	- Propagação/Tratamento do erro nos níveis: Try/Flow/Global e DefaultMule
	- Mapeamento de um erro X para um erro Y
	- Ao erro ser tratado num nivel abaixo (num flow por exemplo) com `On Continue`, a partir de qual parte ele volta a executar
- Transformações de `JSON` para `XML` e o inverso também, lembrar synxtax para ambos os casos (criar / acessar atributos XML)


5232 8417 2592 9794
RICARDO H PEREIRA
08/26
376.955.628-31

