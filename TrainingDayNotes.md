## Sumário
Intro
---

- <a href="#day1">Day 1</a> e <a href="#day2">Day 2</a>: Conjunto de [Slides](http://bit.ly/2mcVZNn) com Introdução a tópicos importantes/requisitos para treinamento.

Módulos
---

- <a href="#modulo1">Módulo 1: Introducing Application Networks And Api-led Connectivity</a> [OK]
- <a href="#modulo2">Módulo 2: Introducing anypoint platform</a> [OK]
- <a href="#modulo3">Módulo 3: Design APIs</a> [OK]
- <a href="#modulo4">Módulo 4: Bulding APIS</a> [OK]
- <a href="#modulo5">Módulo 5: Deploying And Managing Apis</a>
- <a href="#modulo6">Módulo 6: Accessing And Modifying Mule Events</a>
- <a href="#modulo7">Módulo 7: Structuring Mule Applications</a>
- <a href="#modulo8">Módulo 8: Consuming Web Services</a>
- <a href="#modulo9">Módulo 9: Controlling Event Flow</a>
- <a href="#modulo10">Módulo 10: Handling Errors</a>
- <a href="#modulo11">Módulo 11: Writing Data-weave Transformations</a>
- <a href="#modulo12">Módulo 12: Triggering Flows</a>
- <a href="#modulo13">Módulo 13: Processing Records</a>

Extra
---

- <a href="#possibleQuestions">Possíveis questões de prova</a>
- <a href="#importantReview">Importantes Termos / Acrónimos (para Revisar)</a>

<a id="day1"/></a>
### Day 1 - 09/09/19
- SOA (Service-Oriented Architecture)
	* Arquitetura visando sempre agregar no negócio.
	* Processo de design/desenvolvimento em mais alto nível de abstração visando ser visível para mais pessoas.
	* Desenvolver pensando em reutilização / evolução na solução como um todo.
	* Solução flexível a ponto de ser facilmente adaptável em futuras mudanças de requisitos.
	* Características técnicas: Reutilizável, Autonomia (não dependente/acoplado), Modularizado, Não manter estado, Descobrimento de serviço (priorizar soluções existentes que podem ajudar na resolução do seu problema)
- Arquitetura de Micro Serviços
	* Comparação referente ao SOA
	* Diversas Características e discussão sobre esses pontos
	* Prós e Contras relacionados
- SOAP
	* Protocolo para troca de informações estruturadas em uma plataforma descentralizada e distribuída.
	* Exemplos de request SOAP utilizando SOAP UI
- REST
	* Definição / Principios
	* Descrição e discussão sobre características

<a id="day2"/></a>
### Day 2 - 10/09/19
- EIP Patterns
	- Request-reply: two way communication
	- Message Router: decisão de roteamento não está relacionada ao conteúdo da mensagem
	- Content-Based router: examina o conteúdo da mensagem e com base nisso, faz o roteamento
	- Publish and Subscribe
	- Dead Letter Channel
AnypointMQ é o serviço de mensageria Mule

- Guaranteed Delivery:
	* Protocolo que garante a entrega da mensagem: TCP
	* Protocolo que não garante a entrega: UDP

- Como é feita a troca de mensagens entre os componentes Mule: event-driven architecture;
	* Cada componente já espera receber mensagens e enviar mensagens, tudo orquestrado pelo java runtime, a troca de mensagens entre componentes é síncrona.
	* A forma de envio vai depender do padrão adotado (vide EIP Patterns)


- Introducing a new IT operating model
	* As primeiras duas camadas são destinadas ao negócio;
	* Business layer depende do Business goal
	* Process API: processos de negócio que podem ser reaproveitados entre projetos, encapsulados de business rules;
	* Experience API: projetos diferentes;
	* System API: expor recursos da aplicação (quando eu tenho system APIs que possuem funções similares, eu promovo a funcionalidade a um business Process para encapsular essa regra similar, onde meus System API consomem esse process API)
	* A única camada que fica exposta é a Experience API, as outras duas camadas ficam dentro de uma VPC (Virtual Private Cloud)
	* Não preciso das 3 camadas para ter uma API-led, preciso necessariamente de Experience e System APIs.
	* Process APIs são criadas para linhas de negócios, não so funcionalidades;
	* Unlock na System; Agregação de negócio na Process e exposição de dados na Experience, onde geralmente as camadas Process e system são privativas. 
	* New way of working: ao invés de criar novos projetos para cada problema, criar assets que possam ser reutilizados futuramente para diferentes necessidades.


<a id="modulo1"/></a>
### _Módulo 1: Introducing Application Networks And Api-led Connectivity_ [OK]
- [Modelo que prioriza o consumo](http://bit.ly/2mdqxyA): Envolvidos focados em desenvolver com base em feedbacks e métricas de uso, criando Assests reutilizáveis seguindo o conceito de Modern API.
- [Modern API](http://bit.ly/2khRUa9)
	* É discoverable e projetada para fácil consumo.
	* Facilmente gerenciado para segurança, escalabilidade e desempenho.   
- [API-led connectivity](http://bit.ly/2mfkr0F)
	* **Experience API** [`Expor API`]: Fornecer insumos que um projeto precisa para se tornar realidade. 
	* **Process API** [`Agregação de negócio`]: Processos de negócio que podem ser reaproveitados entre projetos, encapsulados de business rules. Essa camada pode não ser necessária. 
		+ Exemplo: Criar uma API para consumir 2 system APIs
	* **System API** [`Expor dados`]: Expõe recursos de sistemas (Unlock your data). 
		+ Exemplo: CRUD de funcionários de duas bases diferentes se tornando 2 SystemAPIs
- [C4E](http://bit.ly/2kLAwee): Time formado por profissionais de varias áreas, onde seu objetivo é planejar/desenvolver assets seguindo API-led e propagar isso na cultura da empresa.
- Application Network: Rede de aplicações do projeto, construídas seguindo a API-led em conjunto com o C4E.
- [Revisão sobre API](http://bit.ly/32l2Zbf): Define como acontece troca de informações entre dois ou mais sistemas. (operações, inputs, outputs)
- [Revisão sobre WebServices](http://bit.ly/31kHwxK): Método de comunicação que permite que dois sistemas de software troquem dados pela internet.
- [Revisão sobre RESTful](http://bit.ly/2IUJVZX): O que é, princípios, verbos, estados, exemplos, etc.
- [Ao se referir a API](http://bit.ly/2ozaDjP), podemos estar falando sobre:  `Proxy` / `Implementação` / `Contrato`.
- **Api-led** se refere a parar de construir projeto com business goals específicos, e construir assets que podem ser reutilizados em outros contextos.

<a id="modulo2"/></a>
### _Módulo 2: Introducing anypoint platform_ [OK]
- Apresentado Anypoint Plataform que é: Uma plataforma empresarial para criação de APIs, integrações e redes de aplicativos.
- [Pilares da abordagem MuleSoft](http://bit.ly/2lS1G3c)
  * Business outcomes: Alinhamento com stakeholders.
  * Technology Delivery: Utilizar Anypoint Platform para desenvolver as soluções.
  * Organization enablement: Capacitação da organização.
- **API Designer**: Construir toda a especificação API como por exemplo, escrevendo o RAML (Contrato da API). Dentro dele tem recursos como `Shelf`, `Criar Mapeamento de Dados`, `Criar Examples`, etc.
- **API Console**: Mapeamento que reflete visualmente o que criado pelo RAML (Endpoints, Exemplos de Entradas e Saidas, etc). Basicamente é o API Portal durante desenvolvimento.
- **API Portal**: Documentação sobre a API que é gerada dinamicamente com base no YAML (Endpoints, Possíveis Response codes, etc). Basicamente é o API Console publicado.
- **API Notebook**: Maneira de criar tutoriais e exemplos com exemplos de código executáveis. (Não cobrado na prova, recurso pouco utilizado).
- **Flow Designer**: IDE Virtual, muito limitada voltada mais para pessoas de negócio
- Anypoint Studio: Desktop IDE baseada em Eclipse
- ==Mule 4 é totalmente orientado a eventos.== 
- ==O mínimo necessário que um Flow (bloco) precisa pra ser válido== é ter um Mule Event Processor, sem isso a compilação falha.
- **Mule Event Source**: O "Listener" que inicia o flow, que é ativado por um evento específico.
- [Estrutura Mule Message](http://bit.ly/2mbTIC7)
	* `Atributes`: Metadata no Header da Mensagem
	* `Payload`: O dado que é processado (corpo)
	* `Variables`: Metadata do MuleEvent

<a id="modulo3"/></a>
### _Módulo 3: Design APIs_ [OK]
- RAML
	* Utilizado para documentar RESTFull APIs
	* Baseado em Indentação por nível
- API Designer shelf: Auto-complete/Sugestões que aparecem durante design do RAML no Design API.
- Mapeamento de exemplo(s) no RAML seguindo key "example" e "examples" (collection).
- Para criar examples sempre preferível criar em JSON por questões de como Mule converte RAML.
- Módulo Totalmente Prático abordando:
	* [Criação de RAML](http://bit.ly/2lPXelG)
	 + Criação de Endpoints para todos verbos com algumas variações
	 + Mapeamento de Exemplos de Input / Output
	 + Mapeamento para Status Code específicos
	 + Campos required ou não (tag `?` pra não ser required)
	* Utilização de Mock Service
	* Publicação da API no Exchange, conceito de ser Discoverable (forma pública e privada)
- [Exemplo de design de RAML com Inputs/Outputs exemplos](http://bit.ly/2lPWX28)

	
<a id="modulo4"/></a>
### _Módulo 4: Bulding APIS_ [OK]
- Módulo Totalmente Prático abordando:
	* [Criação de Aplcação no Anypoint Studio](http://bit.ly/2kNDwqi)
	 + Criação de flows 
	 + Conectores diversos como: `Logger`, `setPayload`, `Select (Banco)`, `Transform`.
- [DataWeave 2.0](http://bit.ly/2mf27Vq): Linguagem para acessar, pesquisar e transformar dados.
- [API Kit Router](http://bit.ly/2kzIRBL): 
	* Le RAML importado e cria toda estrutura abstraindo em `conectores` / `fluxos` / `validações`.
	* Faz match para criar flows usando `Verbo` e `Path`, criando somente um Event Source (Api KitRouber) que redireciona corretamente para respectivo flow. 
	* Cria toda estrutura de validação de atributos (required, tipo, etc)
- Parte prática:
	* Transformação de dados (mapeamento) com DataWeave
	* Importar nosso projeto do Anypoint para o Studio
	* Feito endpoints dos verbos GET (byId e geral) / POST
	* Apontado Interface (projeto importado) paras Implementações no Anypoint Studio.

<a id="modulo5"/></a>
### _Módulo 5: Deploying And Managing Apis_ [OK]
- CloudHub (`PaaS`): Ambiente de cloud da Mulesoft que roda na `AWS` para hospedar aplicações, conta com uma ótima estrutura já pronta.
- Customer-hosted Mule runtimes: Caso a empresa queira hospedar por contra própria utilizando o próprio ambiente ou outro serviço de cloud.
- [CloudHub Worker](http://bit.ly/2lSXS1E): Instância dedicada do Mule que executa **UMA aplicação**, sendo que cada um:
	* Roda num container separado
	* Deployado e monitorado separadamente
	* Roda em uma específica região do mundo
- [API Manager](http://bit.ly/2ISZjpq): Lugar para gerenciar acesso a aplicação como:
	* Criar e deployar proxies
	* Definir níveis de SLAs (categorias de quantidade de acessos por minuto por exemplo) 
	* Aprovar, Rejeitar e Revogar acessos as APIs para os clientes (Tokens)
	* Ver dados analíticos das APIs
- [API Proxy](http://bit.ly/2kBDJwZ): Controla o acesso a um serviço, restringindo o acesso e o uso pelo uso de um gateway. Responsável por garantir que políticas para acesso sejam aplicadas, tendo benefícios
	* Segurança: Ter camada para filtrar chamadas não autorizadas.
	* Evitar onerar serviço: Possibilidade de limitar/filtrar quantidade de requisições.
- [API Gateway](http://bit.ly/2lSGjio): Ponto central de controle, faz com que as políticas aplicadas no API Proxy sejam aplicadas. O que ele também faz:
	* Determina quais tráfegos estão autorizados para passar pela API
	* Mede o tráfico
	* Loga todas transações
- Unidade de Medida no Mule: Mule Message (Evento)
- API Manager: Ferramenta para gerenciar Governança e Métricas
- Parte prática:
	* Criado proxies para um API Gateway runtime
	* Analisados dados analíticos com API Manager
	* Restringindo acesso a API utilizando o API Manager (gerenciar acesso)
	* Criação de Policies simples (tempo de request por SLAs específicos) para exemplificar
	* Deployada aplicação no CloudHub
	* Monitoração da API através to `Runtime Manager` ao efetuar requisições para aplicação.


<a id="modulo6"/></a>
### _Módulo 6: Accessing And Modifying Mule Events_
- [DataWeave](http://bit.ly/2lVBUuY): Linguagem Mule para transformação e manipulação de dados

	* Standalone scripts
		+ Gerados usando o editor gráfico do componente Transform Message
	* Inline expressions
		+ Implementação em código do DataWeave 
- [Parte prática](http://bit.ly/2lX7hFD): 
	* Definido valores de Header/QueryParams no próprio componente de HTTP Listerner/Request
	* Utilizada funções do DataWeave (upper) e operator (++ para concatenar Strings)
	* Acessado valores do Mule Message (Headers, QueryParams) com o DW
	* Manipulada a variável `payload` que tem o contexto de tráfego do Body entre os conectores
	* Implementado a funcionalidade de `default value` para evitar NullPointers, também discutido entre quando usar `required` ou `default value` para contornar essa situação.
	* Utilizando `variables` para armazenar e acessar valores
- Parte prática:
	* Visto informações do data-sense nas em `design time` e `run time`
	* Visto como depurar aplicação e ver informações
	* Contexto de manter variáveis ao realizar chamada externa


<a id="modulo7"/></a>
### _Módulo 7: Structuring Mule Applications_
- Parte prática:
	* Introdução a Subflows
	* Contexto dos parametros no subflow e flow (variables, attributes)
	* Contexto de variáveis persistem dentro do contexto da aplicação (não persistida em chamadas internas)
- Filas
	* Persistente: Mensagens são persistidas pelo serviço de mensageria, mais lento porém mais segundo
	* Transiente: O ciclo de vida da mensagens ficam a cargo do Publisher/Consumer, caso algum dos serviços caiam, as  mensagens "se perdem"
- Arquivo `xml` que transcreve o flow do canvas é denominado  de `configuration file`
- Contexto de parâmetros/variareis mudam (não são acessíveis) ao ir para um fluxo assíncrono pois se assemelha a uma chamada externa
- Projetos Mule 4 são baseados em Maven obrigatoriamente
- [Parte prática](http://bit.ly/2ksZGy8):
	* Desenvolvimento da aplicação utilizando Filas Transientes
	* Publicados e consumidos eventos na fila de forma sincronía e asíncrona 
	* Organização de arquivos para seguir "boas práticas de organização", separando arquivos de propriedades, configuração, separação de flows em outros arquivos, etc.
	* Criação de configurações globais de conectores em um arquivo específico para "herdar" para todo projeto
	* Criação de manipulação de properties files
	* Review sobre Maven, estrutura de pastas, resources, etc


<a id="modulo8"/></a>
### _Módulo 8: Consuming Web Services_ [Reforçar]
- Connectors and Modules
	* Modules: São componentes que executam ações mas não conectam nada (não fazem chamadas externas)
	* Connectors: Todo conector é um módulo, com a diferença que de fato se conecta a algo. 
	* Um componente pode englobar Modulo e Conectores, exemplo: HTTP, SalesForce, etc
- Níveis de componentes do Exchange: Tem [vários levels de conectores](http://bit.ly/2kTOBGo) que refletem em nível de suporte, sendo eles: `Premium`, `Select`, `MuleSoft Certified`, `Community`. Que são refletidos [nesses 3 Tiers](http://bit.ly/2krt4ES).
- ...


<a id="modulo9"/></a>
### _Módulo 9: Controlling Event Flow_ [Reforçar]
- Scatter-Gather: Execute vários flows ao mesmo tempo de forma paralela, o retorno é sempre um Objeto de Objetos.
	* Retorno do componente é Objeto de Objetos 
- Flatten: Agrega saída de cada flow se utilizado junto com Scatter-Gather, no geral é para manipular e juntar dados
- Módulo Validator: Para validação de dados, diversos processadores pré-prontos para validações diversas
- Ao não atender requisitos do Validator, comportamento default é retornar erro na Request interrompendo a sequencia do flow.
- Parte Prática:
	* Utilizado Scatter-Gather
	* Utilizado `Flatten` para mudar retorno do componente
	* Utilizado módulo `Validator` com operações para validações de dados: isNumber, isNull, etc

	<a id="modulo10"/></a>
### _Módulo 10: Handling Errors_ [Reforçar]
- ..


<a id="modulo11"/></a>
### _Módulo 11: Writing Data-weave Transformations_ 
- Módulo destinado a se aprofundar em escrever expressões DataWeave sem Interface gráfica
- Ao converter o payload de `json` para `java` sem definir um tipo específico, o Mule vai tentar representar da melhor forma utilizando estruturas do Java (classes, collections, etc).
- Data Model: É o lugar onde aplicamos nossas expressões/transformações em Dataweave
- Ao trabalhar com transformações manipulamos os [seguintes tipos de data](http://bit.ly/2M3YY5x):
	* Objetos
	* Listas
	* Literais
- Mime Types: Possíveis outputs que definimos para nosso script, ex: `application/java`, `...xml`, `...json`.
	* O `aaplication/dw`
- No Dataweave temos [2 tipos de erros](http://bit.ly/2IFA5uN):
	* Scripting errors: Problema com syntax
	* Formatting erros: Erros de transformação de um tipo para outro
- Modelo Canônico: Forma que usa pra representar modelo do nosso domínio
- Para output em `XML` temos algumas tratativas específicas, por exemplo:
	* [Ter um elemento pai](http://bit.ly/2B0Mi96)
	* [Referenciar atributos com `@`](http://bit.ly/2IEFe6p)
- Para de transformação de dados com DataWeave utilizando função `map`. Podemos referenciar o key/value do lambda de [forma implícita](http://bit.ly/324B3IC) com os valores `$$` e `$` respectivamente ou declarar de [forma explícita](http://bit.ly/2OC2HJc).
- A transformação em `XML` é feita de [forma diferente em questão de syntax](http://bit.ly/2nyqmPs)
- Ao converter para `application/java`:
	* Podemos converter os tipos de uma [forma genérica para um tipo](http://bit.ly/35oIvQR) (com palavras reservadas)
	* Podemos também converter [especificando a package/classe java](http://bit.ly/33m2q12) 
	* Ao realizar conversões, podemos especificar máscaras utilizando a tag `format`
- A tag **format**: 
	* Pode ser utilizada ao manipular alguns atributos que tem outputs específicos, como: String, Date, etc. 
	* Utilizando o `#` a formatação é opcional, já utilizando o `0` a formatação se torna obrigatória.
- Podemos criar tipos de dados específicos, [externalizando a formatação para reutilização](http://bit.ly/2MBnAlb)
- Também podemos [criar nossos tipos de conversões específicos (mascaras)](http://bit.ly/2B0X66X) que são [baseados em classes POJO](http://bit.ly/2q7bWa9) por exemplo e [utilizar da mesma forma que tipos default](http://bit.ly/32bEwoM)
- Ao utilizar [funções do DataWeave](http://bit.ly/2q7gJs9), temos as ja herdadas por default (já estão no core), para [as demais devemos importar](http://bit.ly/2Vz2Heh)
- [==== REVER SUMMARY ====](https://training.mulesoft.com/user/consume/course_pathway/788a9b09-b663-3344-83d6-211080628b9f/3879/948665de-6863-3155-9472-6223a10ff718?complete=0&tab=overview)

<a id="modulo12"/></a>
### _Módulo 12: Triggering Flows_ [Reforçar]
- a
- b

<a id="modulo13"/></a>
### _Módulo 13: Processing Records_ 
- Foreach
	* Não altera o Payload após a interação e retorna a mesma entrada (payload) para o próximo componente, ou seja, **toda alteração dentro do foreach sem escopo local**
	* Possui uma variável específica (um counter) para armazenar temporariamente o índice do Loop
	* Componente de processamento síncrono, utilizam a mesma thread para processamento de todos os items
	* Itera **somente sobre arrays**, qualquer outro tipo de estrutura de dados lançaria uma excessão
- The Batch Scope
	* A principal diferença do `foreach` é esse componente **ser assíncrono**, quebrando dados em blocos para processamento paralelo
	* Controla excessão a nível de bloco de processamento
	* Principais usos:
		+ Processamento Paralelo
		+ ETL 
		+ Integrações próximos a runtime
		+ Lidar com grande quantidade de entrada de dados
	* [O processo possui 3 passos](http://bit.ly/317MXAc)
		+ **Load and dispatch** (Implicito): Agrupa registros em blocos (records) e envia para fila
		+ **Process** (Required): Processa records de forma assíncrona, supondo que tenhamos `3 batch steps`, nada garante que o registro que acaba de ser processado no `1o step` vai diretamente para o `2o step`, ao ser processado ele vai novamente para fila esperando as próximas fases de processamento 
		+ **On complete** (Optional): Sumário dos registros processados, mostra report de quais registros tiveram erros ao processar
	* Escopo de variáveis
		+ Variáveis declaradas fora do escopo do batch:
			+ São acessíveis dentro do batch processor mas a variável em si é imutável, ou seja, mesmo que altere dentro desse contexto, o valor original da variável é mantida ao fim do processamento do batch 
			+ Cada record (grupo de registros), faz uma "cópia" dessa variável, portanto a alteração de um record não interfere em outro, e as alterações feitas são mantidas somente no contexto daquele record
		+ Variáveis declaradas dentro do escopo dos batch steps:
			+ O escopo também é por record (bloco)
			+ Uma variável declarada num batch step anterior é acessível aos steps posteriores, também levando em conta o contexto de record
			+ São somente visíveis dentro dos batch steps, fora desse contexto a variável não existe
			+ As etapas (Load / Process / Complete) não compartilham contexto de variável
		+ [Estratégia de tratamento de erros](http://bit.ly/2MdxASl): *Sempre feitos a nível de blocos*
			+ Stop processing: Para todo o batch, não levando em conta os blocos
			+ Continue processing: Ao ocorrer erro, definir tratativa para continuar processamento nos próximos steps
			+ Continue until a max number o failures: Configurar numero X de falhas, indo para a fase `On Complete`
	- Saída da fase `On Complete`: O valor do `payload` é um relatório de processamento por bloco, um objeto com N informações referentes ao processamento 
	- [Filtering](http://bit.ly/31dgkRH): Para aplicar N filtros para, por exemplo, definir as condições para ir pro próximo `batch step` ou não
	- [Agregator](http://bit.ly/2nPugDS)
		+ Cria uma regra para "juntar registros do bloco" para ser processados em conjunto, o número de registros é configurável
		+ "Juntar registros" no Agregator não bloqueia próximos passos de serem executados, é uma espécie de processo paralelo

<a id="importantReview"/></a>
## ==Importantes Termos / Acrónimos (para Revisar)==
- VPC: Virtual Private Cloud
- LoB IT: Line of Business
- Central IT: Desenvolvedores (nós)      
- [C4E](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide18.png): Center for Enablement
- [Application Network](http://bit.ly/2mj58nO): Rede de aplicações do projeto que é criada com base em assets bem estruturados e reutilizáveis.
- [API Life Cycle](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide48.png): Fases de desenvolvimento de uma API
- Unlock your data: Expor recursos/dados
- iPaaS: Integration platform as a service. Mule se encaixa nessa categoria.
- API Kit: Valida requests com relação às especificações do RAML e as direciona para implementações da API, criando toda estrutura com base nisso (conectores, validações, etc)
- CloudHub: Ambiente de cloud da Mulesoft
- SLA (Service Level Agreement): Define a quantidade de solicitações que podem ser feitas por período a uma API, podendo ser feito por grupo


<a id="possibleQuestions"/></a>
## Possíveis questões de prova:
- Com base em que o API Kit Router cria os flows ao ser importado? 
	* Para fins de prova, cada HTTP Method.
- Qual é a configuração mínima necessária em um fluxo para uma aplicação Mule compilar? 
	* Event Processor
- Quantas aplicações um CloudHub worker roda?
	* Somente UMA 
- Quem é responsável por aplicar/fazer enforce das políticas de segurança?
	* API Gateway (que faz enforce das policies)
- Qual serviço é relacionado a Governancia/Gerencia/Métricas?
	* API Manager
- Perguntas em geral em relação a DataWeave:
	* Como fazer conversões
	* Como manipular datas
	* Em relação a operators, como utilizar em situação X
- Como acessar valores de [contextos específicos](http://bit.ly/2lSOdYZ) como por exemplo: Server, Mule Instance, Mule Application, etc. Também se atentar ao contexto da variável, se é acessível do ponto que está sendo chamado.
- Muitas perguntas em relação a supostos fluxos e contextos da Mule Message (Variáveis, Headers, Payload, etc), como isso muda ao ir para contexto um serviço externo, subflow, etc.
- Como lidar com XML no processo de manipulação/transformation utilizando Dataweave (tags específicas, etc)
- Escopos de variáveis/funções no escopo das expression do Dataweave (global, local), exemplos práticos em relação a isso
- Questões referentes a transformation, vão vir no [formato input/transformation/output](http://bit.ly/317e9iu)
- Questões referentes a funções aninhadas, [vai ter o script do lado esquerdo e a pergunta será referente a saída](http://bit.ly/2AZU6b4)

========== [REVER Parte do JESUS](https://training.mulesoft.com/user/consume/course_pathway/788a9b09-b663-3344-83d6-211080628b9f/3780/cd916a52-1fd0-3420-b170-ce2b4bfeced0?complete=0&tab=overview) ========
- var / fun / using (reforçar bem) e também ver `..*` 


### Search Later / Review
- Governância de API (pesquisar contexto geral)

