## Sumário
- Day 1 e Day 2: 

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


## Day 2 - 10/09/19
- ...


## Day 3 - 11/09/19 
## TODO: Reestruturar Acrônimos e Sublistas
### [Módulo 1: Introducing Application Networks And Api-led Connectivity](http://bit.ly/2kAEZ3u)
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
- [ ] !!Sumarizar Notas sobre led connectivity e extrair dos acronymos!!
- [ ] !!Sumarizar Notas sobre Application Network e extrair dos acronymos!!
- [Revisão sobre API](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide26.png): O que é, princípios, etc.
- [Revisão sobre WebServices](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide29.png): O que é, princípios, etc.
- [Revisão sobre RESTful](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide33.png): O que é, princípios, verbos, estados, exemplos, etc.
- Ao se referir a [API](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide27.png) podemos estar falando sobre: Proxy / Implementação / Contrato
- Walk-Thru no Portal de Assets do MuleSoft (Exchange) 


### Important Acronymous / Terms
- LoB IT: Line of Business
- Central IT: Desenvolvedores (nós)      

- [C4E](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide18.png) (Center for Enablement): Time formado por profissionais de varias áreas, onde seu objetivo é desenvolver assets de modo a propagar a forma do API-led pela cultura da companhia.
- Application Network: Rede de aplicações do projeto, construídas tendo a relação com essas aplicações sendo construídas seguindo a API-led em conjunto com o C4E.
- [API Life Cycle](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/01_app_networks/Slide48.png): Fases de desenvolvimento de uma API
- [ ]  Unlock your data: Expor dados

### Search Later / Review
- Unlock your data (expressão)
- Governância de API (pesquisar contexto geral)



- Parar de construir projeto com business goals específicos, construir assets que podem ser reutilizados em outros contextos para ser reutilizado
- AN: Criar assets bem estruturados e reutilizáveis



## Day 4 - 12/09/19 
## TODO: Reestruturar Acrônimos e Sublistas

- Apresentado Anypoint Plataform que é: Uma plataforma empresarial para criação de APIs, integrações e redes de aplicativos.
- Pilares da abordagem MuleSoft: Business outcomes / Technology Delivery / Organization enablement
- API Designer: Escrever o RAML (Contrato da API)
- API Console: Mapeamento que reflete visualmente criado pelo RAML
- API Portal: Documentação sobre a API que é gerada dinamicamente com base no YAML (Endpoints, Possíveis Response codes, etc)
- API Notebook: Seu espaço para compartilhar seus assets de forma pública
- Flow Designer: IDE Virtual, muito limitada voltada mais para pessoas de negócio
- Anypoint Studio: Desktop IDE baseada em Eclipse
- Mule 4 é totalmente orientado a eventos. 
- O mínimo necessário que um Flow (bloco) precisa pra ser válido é ter um Mule Event Processor, sem isso a compilação falha.
- Mule Event Source: O "listener" que inicia o flow, que é ativado por um evento específico.
- Walk-thru sobre Anypoint Platform e Anypoint Exchange.
- Walk-thru sobre Flow Designer
- [Estrutura Mule Message](https://training.mulesoft.com/static/MUContent/4.2/MUFundamentals4.2/slide_images/02_anypoint_platform/Slide40.png)
	* Atributes: Metadata in Message Header
	* Payload: O dado que é processado
	* Variables: Metadata do MuleEvent


* a
	+ a a
	+ + a a

## Important Acronymous / Terms
- iPaaS: Integration platform as a service. Isso é o que o Mule é
- aa



### Search Later / Review

## Day 5 - 13/09/19 
## TODO: Revisar módulos e fazer mais anotações
### [Módulo Design APIs](https://training.mulesoft.com/user/consume/course_pathway/788a9b09-b663-3344-83d6-211080628b9f/3807/8aac83b8-c6fc-3f51-bb6d-9e70bbca086d?complete=0&tab=overview)
- RAML
	* Utilizado para documentar RESTFull APIs
	* Baseado em Indentação por nível
	* ... Escrever mais definições

- Mocking Service: 
- API Designer shelf: Auto-complete/Sugestoes que aparece durante design do RAML no Design API
- Mapeamento de exemplo(s) no RAML seguindo key "example" e "examples" (collection)
- Para criar examples sempre preferível criar em JSON por questões de como Mule converte RAML
- Sumarizar: https://training.mulesoft.com/user/consume/course_pathway/788a9b09-b663-3344-83d6-211080628b9f/3813/89fbd216-f67b-3e61-8523-3d05b004d087?complete=0&tab=overview
- Walk-thru 
- Walk-thru 
- Walk-thru 

### [Módulos Bulding APIS](https://training.mulesoft.com/user/consume/course_pathway/788a9b09-b663-3344-83d6-211080628b9f/3814/253233a5-a7d9-3f28-b0af-c1138f1bea67?complete=0&tab=overview)

- a
- b

## Important Acronymous / Terms
- Mocking Service: Testar seu serviço mokado
- a

### Walk Thru
- aa 

### Search Later / Review


