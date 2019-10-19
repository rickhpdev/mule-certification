#### Why we define the `http.port` in the HTTP listener to deploy on cloudHub?
- To API manager register on API Manager...
- To ClouHub changes and allows http requests to your Listener

#### No ScatterGatter, temos dois flows, um demora 10 segundos e outros 20 segundos, qual tempo de execução geral ?

#### 3 questões em cima de escopo de variáveis, tendo o mesmo endpoint `localhost/api?color=red`. Dado o contexto que temos um flow pai que chama um flow externo via HTTP request, no `mainFlow` sentamos um variável, variando as perguntas em:
- O que está acessível num logger no fim no `Main flow`, que possui um Logger no Fim? (Payload / variável / QueryParam `color`)
- O que está acessível num logger no fim no `Child flow`, que possui um Logger no Fim? (Payload / variável / QueryParam `color`)
- Nesse mesmo contexto mas **alterando para o childFlow para um Flow Reference**, O que está acessível num logger no fim no `Child flow`, que possui um Logger no Fim? (Payload / variável / QueryParam `color`)

#### Ao configurar um globalHandler, onde devemos configurar para "começar a valer"?
- Property file
- Global element
- Nothing to do, is automatic
- ...

#### Um projeto está dando erro ao buildar (erro no console mostrando erro de build por não conseguir puxar uma dependencia), essa dependencia está num repositório do Mule. Obs: Esse mesmo projeto funcionou em outra máquina, o que podemos fazer para arrumar?
- Adicionar a dependencia no "HOME/bin" (algo assim)
- Deployar dependencia no repositório privado do mule
- Editar o pom.xml
- ...

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

#### Qual path mínimo para configurar no ApiKit
- Certa: `/*`

#### Syntax para condição do Choice
- Certa: `#[XXX] == "US"`

#### Dado `RAML` exemplo, quantos métodos o APIKit gera?

#### Fluxo que lê `CSV`, em determinado ponto do flow tem um BreakPoint num Processor que é um `SELECT` no banco, em tempo de execução, o que o debug mostra?
- O arquivo `csv` todo
- O resultado da query
- ...

#### Um conector de escrita que escreve um payload JSON `{...}` num arquivo `CSV`, o que é escrito no arquivo?
- Certa: Um JSON, não importa o arquivo ser `csv`, importa a saida do TransformMessage que é um `application/JSON`

#### Como acessar URI Param no conector `HTTP Listener`?
- ${..}
- #[..]

#### Cenário: Dois times perderam tempo desenvolvendo uma API que no fim era a mesma, como isso poderia ter sido evitado:
- Se o C4E tivesse "monitorirado" isso

#### Dado um flow exemplo e feita a pergunta: O que poderia ser adicionado para persistencia de dados por esse flow?
- Setar 

#### O que acontece se o conector sde DB nao achar nada no banco?
 - Volta array vazio

#### Como definir `type` no RAML?
- A ***alternativa certa*** é `types` e não `dataTypes` (duas opções sao bem parecida mas a primeira é a certa)

#### Mínimo necessário para deployar uma aplicação no CloudHub?
- Combinações entre (Resources / Dependencias e Módulos)
	- Sendo possível selecionar os dois, nenhum dois dois, ou só um de cada
 


