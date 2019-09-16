## Sumário
- <a href="#day1">Day 1</a> e <a href="#day2">Day 2</a>: Conjunto de [Slides](http://bit.ly/2mcVZNn) com Introdução a tópicos importantes/requisitos para treinamento.
- <a href="#day3">Day 3</a>
- <a href="#day4">Day 4</a>
- <a href="#day5">Day 5</a>
- <a href="#day6">Day 6</a>
- <a href="#importantReview">Importantes Termos / Acrónimos (para Revisar)</a>

<a id="day1"/></a>
## Day 1 - 09/09/19
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
## Day 2 - 10/09/19
- Irei sumarizar no futuro (feel free to add)

<a id="day3"/></a>
## Day 3 - 11/09/19 
### _Módulo 1: Introducing Application Networks And Api-led Connectivity_
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
- [Revisão sobre API](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide26.png): Define como acontece troca de informações entre dois ou mais sistemas. (operações, inputs, outputs)
- [Revisão sobre WebServices](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide29.png): Método de comunicação que permite que dois sistemas de software troquem dados pela internet.
- [Revisão sobre RESTful](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide33.png): O que é, princípios, verbos, estados, exemplos, etc.
- [Ao se referir a API](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide27.png), podemos estar falando sobre:  `Proxy` / `Implementação` / `Contrato`.
- **Api-led** se refere a parar de construir projeto com business goals específicos, e construir assets que podem ser reutilizados em outros contextos.

<a id="day4"/></a>
## Day 4 - 12/09/19 
### _Módulo 2: Introducing anypoint platform_
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

<a id="day5"/></a>
## Day 5 - 13/09/19 
### _Módulo 3: Design APIs_
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

### _Módulo 4: Bulding APIS_
- Módulo Totalmente Prático abordando:
	* [Criação de Aplcação no Anypoint Studio](http://bit.ly/2kNDwqi)
	 + Criação de flows 
	 + Conectores diversos como: `Logger`, `setPayload`, `Select (Banco)`, `Transform`.

<a id="day6"/></a>
## Day 6 - 16/09/19 
### _Módulo 5: Deploying And Managing Apis_
- a
- b

<a id="importantReview"/></a>
## ==Importantes Termos / Acrónimos (para Revisar)==
- LoB IT: Line of Business
- Central IT: Desenvolvedores (nós)      
- [C4E](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide18.png): Center for Enablement
- [Application Network](http://bit.ly/2mj58nO): Rede de aplicações do projeto que é criada com base em assets bem estruturados e reutilizáveis.
- [API Life Cycle](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide48.png): Fases de desenvolvimento de uma API
- Unlock your data: Expor recursos/dados
- iPaaS: Integration platform as a service. Isso é o que o Mule é

### Search Later / Review
- Governância de API (pesquisar contexto geral)

