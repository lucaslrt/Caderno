# Caderno

# Index
- [Concurso Câmara dos Deputados](#id-section1)
    - [LÍNGUA PORTUGUESA](#id-portugues)
    - [LÍNGUA INGLESA](#id-ingles)
    - [DIREITO CONSTITUCIONAL E REGIMENTO INTERNO DA CÂMARA DOS DEPUTADOS](#id-direito-constitucional)
    - [DIREITO ADMINISTRATIVO](#id-direito-administrativo)
    - [ADMINISTRAÇÃO ORÇAMENTÁRIA E FINANCEIRA](#id-administracao)
    - [RACIOCÍNIO LÓGICO-MATEMÁTICO](#id-logica)
    - [ARQUITETURA DE SISTEMAS DA INFORMAÇÃO](#id-arq-sist-info)
    - [ARQUITETURA DE INFRAESTRUTURA DE TECNOLOGIA DA INFORMAÇÃO E COMUNICAÇÃO](#id-arc-infra)
    - [SEGURANÇA CIBERNÉTICA E DA INFORMAÇÃO](#id-sec-info)
    - [DISSERTAÇÃO](#id-dissertacao)


<div id='id-concurso-camara'/>

# Concurso Câmara dos Deputados - Analista Legislativo - Informática Legislativa

<div id='id-portugues'/>

## LÍNGUA PORTUGUESA

### Material de estudo
- https://www.youtube.com/watch?v=71HFDNbuMm0
- https://www.youtube.com/watch?v=jmndTZyHvSU

### Interpretação e compreensão de texto. Organização estrutural dos textos

- **Inferência** pode ser dividida em **duas** categorias:
    - **Pressuposto**: Informação obtida a partir de **marcas linguísticas** (pistas textuais): verbos, adjetivos, advérbios... Em resumo, Pressuposto é uma Inferência com pistas no texto

    Exemplo:

    ```
    Ana não quer mais ser professora
    ```
    **PRESSUPOSTO 1**: Ana **já quis** ser professora<br>
    **PRESSUPOSTO 2**: Ana **quer deixar** de ser professora<br>
    **Subentendido**: Informação que não está marcada no texto, mas pode ser deduzida pelo leitor a partir de sua leitura e de seu conhecimento de mundo.

    Exemplo:

    ```
    Ana não quer mais ser professora
    ```
    **SUBENTENDIDO**: Talvez pelas condições de trabalho e baixa remuneração.


### Marcas de textualidade: coesão, coerência e intertextualidade

- **Coerência** refere-se à **construção lógica** do sentido global do texto. Quando ele possui **contradições**, é um texto **incoerente**

- **Contradição** ocorre quando duas situações não podem ser verdadeiras ao mesmo tempo:

```
Hoje eu comi uma maçã, mas não comi uma fruta.
```

- **Coesão** refere-se à articulação entre as ideias e elementos textuais. Você tem duas grandes maneiras de articular coesão em um texto:
    - **Semântica**:
    ```
    Não seremos apenas fantoches que vagam, MAS guerreiros que pensam e decidem.
    ```
    - **Referencial**:
    ```
    A sala de aula virtual do professor estava cheia. Se fosse presencialmente LEE calcula que haveria um terço dos alunos.
    ```
Em outras palavras, a coesão faz a ligação entre uma frase e outra.
**OBS:** Estudar **conjunção**

### 

<div id='id-ingles'/>

## LÍNGUA INGLESA

### Material de Estudo

- https://www.youtube.com/watch?v=4eCAunVoOqQ

### Dicas para resolução de questões em inglês

- As questões geralmente são textos extensos
- Tem palavras fora do usual
- Sempre analise primeiro o título do texto para extrair o tema
- Primeiro parágrafo geralmente é o tema principal do texto
- Anote palavras chave que você não viu antes
- As soluções ou resoluções do texto geralmente estão no último parágrafo 
- Leia primeiro as questões antes de ler o texto inteiro (caso o texto seja mto grande)

### Palavras-chave

- **"In a jiffy"**: Em um instante / Rápido
- **"Hindmost"**: Último / final
- **"Fleeting"**: Rápido
- **"Although"**: Embora
- **"Forecast"**: Previsão
- **"Dodgy"**: Suspeito 
- **"Do away with it"**: Jogar fora
- **"Tackling"**: Enfrentar / lidar
- **"Hindering"**: Dificultar
- **"Arousing"**: Despertar
- **"Altogether"**: Completamente
- **"Throughout"**: Através de
- **"Notwithstanding"**: Apesar de

<div id='id-direito-constitucional'/>

## DIREITO CONSTITUCIONAL E REGIMENTO INTERNO DA CÂMARA DOS DEPUTADOS

<div id='id-direito-administrativo'/>

## DIREITO ADMINISTRATIVO

<div id='id-administracao'/>

## ADMINISTRAÇÃO ORÇAMENTÁRIA E FINANCEIRA

<div id='id-logica'/>

## RACIOCÍNIO LÓGICO-MATEMÁTICO

<div id='id-arq-sist-info'/>

## ARQUITETURA DE SISTEMAS DA INFORMAÇÃO

### Material Utilizado

- https://www.youtube.com/watch?v=8MqYRN4DnSs
- https://www.youtube.com/watch?v=Pfsmaxk0ipo

### Kubernetes Avançado

- **Cloud Native App's**: É uma junção de aplicações baseadas em **Clean Code** (Boas práticas de código), **Domain-Driven Desing** (Padrões de Códigos), **Microservices Principles** (Escalabilidade) e **Kubernetes Patterns** (Padrões baseados em containers)

- KBS (Kubernetes) != Docker: Dockers são containers, KBS é um padrão baseado em containers.

- Kubernetes Principle':
    - Desenvolvido pela Google em 2014
    - É um orquestrador de containers
    - Ele monitora sua aplicação para saber se ela está pronta ou não
    - Verifica se sua aplicação está sustentável

- Componentes básicos: **Cai bastante! Procurar material no site do Kubernetes**
    - Node: 
    - Cluster:
    - Service:
    - Pods: É um agrupamento de containers
        - Estudar container lifecycle
        - Primeiro você roda um init container
        - Fases de um pod: 
            - Pending
            - Running,
            - Succeed
            - Failed
            - Unknown
        - Labels
        - Selectors
        - Annotations
        - Deployment
        - StatefulSet
            - persistent identity
            - networking
            - storage
            - ordinality (ordered, graceful deployment, scaling, automated rolling updates)
        - DaemonSet
        - HPA (Horizontal Pod AutoScaling): Escalabilidade
    - Probes: (Estudar os parâmetros, podem cair)


- Health Probe - Liveness vs Readiness
    - Os meios para verificação da sustentabilidade da aplicação são:
        - Exec command
        - HTTP (200 a 399 - ok)
        - TCP Socket
        - gRPC
    - Liveness: Reinicia a aplicação. É possivel controlar a quantidade de tentativas e o tempo entre cada tentativa
    - Readiness: Verifica se é possível enviar trabalhos para o pod (Descobrir o que é isso)
    - Pode cair a configuraçao do yaml para suportar essas paradas

- Load Balancer
    - Service
    - Ingress
    - Ingress Controller
    - Service Discovery: Comunicação entre dois Clusters

- NameSpaces
    - Organização dos recursos de um cluster específico
    - ```<service-name>.<service-namespace>.svc.cluster.local```
    - Um pod pode se comunicar com o outro através dos namespaces
    - Tipos de namespaces:
        - default
        - kube-system
        - kube-public
    - Namespaces for multi-tenancy:
        - Em um banco de dados utilizado por uma aplicação que roda em diferentes lugares (por exemplo, um app que roda em clínicas de estética diferentes para gerenciar os produtos), é possível você utilizar um mesmo schema com várias tabelas do banco
        - Você cria um container para a aplicação e um para o banco de dados, daí você cria um gateway para um cliente A e um para um cliente B, daí você consegue manter o isolamento dos dados de cada cliente utilizando o mesmo banco de dados

- Arquitetura
    - Nodes:
    - Controllers
    - Cloud Controller
    - CRI - Container Runtime Interface
    - CGroups
    - Garbage Collection
    - Node selector
    - Node Affinity (**Já caiu em prova**)
    - Node Anti-Affinity (**Já caiu em prova**)
    - Kube Scheduler
    - Taints and Tolerations (**Tem chance de cair**)
    - Descheduler

- Scaling Pods vs Scaling Nodes
    - Karpenter

- Garbage Collections
    - Limpador de Recursos
    - Propriedades (**Já caiu em prova**)

- Storage
    - Volumes
        - PVC (Persistence Volume Claim): Requisição para armazenamento pelo usuário
        - PV (Persistence Volume): Abstração dessa requisição
        - Storage Class: 

- Predictable Demands
    - Planejamento e capacidade
    - Declarar requisitos para encontrar o melhor lugar
    - Especificando através de REQUESTS (mínimo para funcionar) e LIMITS (máximo que pode atingir)
    - Quality of Service (**Tem chance de cair**)
        - Como escolher onde rodar?
        - Como escolher qual "kill" / evict?
        - Através das Classes:
            - Best-Effort (pod não informou request e limits. 1o Evict)
            - Burstable (request e limits informados, mas não iguais. 2o Evict)
            - Guaranteed (requests == limits. 3o Evict)
    - Pod Priority
        - Definindo a importancia de um Pod em relação a outros
        - quanto maior valor, mais importante
        - Não é mto recomendado de ser usado pela doc do kubernetes.

- Declarative Deployment
    - É um gerenciador de aplicações na Kubernetes
    - É como um github para o Kubernetes, ela gerencia o versionamento da aplicação como um todo.
    - Helm hooks
    - Arquitetura:
        ```
        demo-chart/
            Chart.yaml
            template

        ```
    - Rolling Deployment
        - Rolling Update
            - Propriedades: (**Pode cair na prova**)
        - Recreate
        - Blue Green
        - Canary Release

- Containers Auxiliares
    - Integração

### ITIL4

- O que é:
    - Guia de melhores práticas para gerenciamento de serviços de TI
    - Não é uma metodologia, você adota o que faz sentido no contexto
    - Baseada em:
        - Sistema de Valor de Serviço (SVS)
        - 4 Dimensões
        - 7 Princípios Orientadores
        - 34 Práticas de Gerenciamento

- Serviço
    - É um meio que permite a cocriação de valor ao facilitar a obtenção dos resultados que os clientes desejam, sem que eles precisem gerenciar custos e riscos específicos

- Modelo de Quatro Dimensões (**Já caiu bastante em provas**)
    - Para suportar uma abordagem holística (uma visão do todo), a ITIL define 4 dimensoes que são críticas para o gerenciamento de serviços:
        - Organizaçoes e Pessoas (aspecto humano)
        - Informação e Tecnologia (aspecto técnico)
        - Parceiros e Fornecedores (ecossistema de serviços)
        - Fluxos de Valor e Processos (como o trabalho acontece)

- Princípios Orientadores
    - Foque em valor
    - Comece onde você está (não recomece do zero)
    - Progrida iterativamente com feedback
    - Colabore e promova a visibilidade
    - Pense e trabalhe de forma holística
    - Mantenha a simplicidade e praticidade
    - Otimize e automatize (libere o RH sempre que possível)

- SVS
    - Para o gerenciamento de serviço funcionar corretamente, ele precisa trabalhar como um "sistema"
    - O Sistema de Valor de Serviço descreve como os componetes e ativdades da organização trabalham juntos como um sistema: (**Procurar o esquema para entender**)
        - Oportunidade e Demanda
        - Valor
    - A cadeia de valor de serviço está dentro do Sistema de Valores de Serviço

- Práticas de Gerenciamento
    - Podem ser divididas em 3 grande áreas
        - Práticas de Gerenciamento Geral
        - Práticas de Ger. de Serviços
        - Práticas de Ger. Técnico

### Modelagem de Processos BPMN

- O que é:
    - É um padrão aberto (não uma metodologia) que permite a construção de modelos lógicos para a automação de processos 
    - A modelagem tem como objetivo criar uma representação do processo de maneira completa e precisa sobre seu funcionamento.   
- https://bpmb.de/poster (**Decorar**)
- Ordem de estudo:
    - Eventos
    - Atividades
    - Gateway
    - Fluxo de sequência
    - Fluxo de mensagens
    - Associação
    - Pool
    - Lane
    - Objeto de dados
    - Grupo
    - Anotações

<div id='id-arc-infra'/>

## ARQUITETURA DE INFRAESTRUTURA DE TECNOLOGIA DA INFORMAÇÃO E COMUNICAÇÃO



<div id='id-sec-info'/>

## SEGURANÇA CIBERNÉTICA E DA INFORMAÇÃO

<div id='id-disseracao'>

## DISSERTAÇÃO

- [Estratégias de Escrita](https://www.youtube.com/watch?v=v_naTxbWZGc) 
