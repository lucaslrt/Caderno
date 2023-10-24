# ARQUITETURA DE SISTEMAS DA INFORMAÇÃO

## O que falta

- Comandos Linux
- Comando Windows
- Serviço em nuvem
    - PaaS, SaaS, IaaS
- Backups
    - Completo e parcial
    - Incremental e diferencial
- VMware
- Nginx
- HTML / CSS
    - Web responsivo
- Javascript
    - Map, reduce, filter..
- Python
    - dunder methods
- Java
    - Thread Pool
    - Executor
- SpringBoot
- JPA
    - Hibernate
    - Estados
- Docker
    - Comandos
- Serveless Computing (Caiu bastante na SEFAZ MG)
- Kubernetes
    - YAML
- Swift (Básico)
- Web Services
    - HTTP, SMTP e FTP
- Qualidade de software
- Desenvolvimento de interfaces de usuários
- Cobit 2019 (Buscar mais material)
- ITIL4
    - Gerenciamento de Problemas
    - Controle de Mudanças
- Planejamento de TI
    - SWOT
    - Ciclo PDCA
    - Tipos de estrutura organizacional
    - Escritório de Projetos (PMO)
- Machine Learning
    - Model Fitting
    - Lemmatization
    - Transfer learning

## Material Utilizado

- https://www.youtube.com/watch?v=8MqYRN4DnSs
- https://www.youtube.com/watch?v=Pfsmaxk0ipo
- https://www.youtube.com/playlist?-list=PLBKXa8XfK1igcc6FbGh_zBP8NssIPtVWd
- https://www.youtube.com/watch?v=2kTs_D22q6E&t=17s
- https://www.youtube.com/watch?v=zDt6FZvKDpQ
- https://www.youtube.com/watch?v=U1Sweidt0Vs

## Modelagem de Dados

**Dicas de Questões:**
- Sempre que tiver as frases: 
    - "com o banco de dados já implementado"
    - Nível
    - Camada ou esquema
    - Arquitetura de 3 esquemas
    - Arquitetura de 3 camadas
    - Arquitetura ANSII / Spark
Significa que o banco já está implementado

- Sempre que tiver as frases:
    - Projeto
    - Modelo
    - Modelagem
Significa que vai ocorrer a criação de um banco

Exemplo:
    - Modelo de visão = novo projeto de banco de dados que você está alinhando com o cliente a informação que o banco de dados vai conter
- As `linhas` da tabela de BD pode ter o nome de `registro` ou `entidade` ou `tupla`
- As `colunas` da tabela de BD podem ter o nome de `atributo`
- As `tabelas` do BD podem ter o nome de `Relação`
- Clausulas check: é uma clausula de validação, se um dado está dentro de um domínio específico  
- collation strings: São descriçoes específicas
- **Abstração:** se refere à supressão de detalhes da organizaç~ao e do armazenamento de dados, descartando par um melhor conhecimento desses dados os recursos essenciais.
- **Modelo de dados:** se refere a uma coleção de conceitos que podem ser utilizados para descrever a estrutura de um banco de dados, oferencedo os meios necessários para alcançar essa abstração.
- **Instância**: refere-se aos dados e metadados e usuários presentes no servidor de dados em um determinado instante.
- **Domínio**: Domínio representa o tipo de dado (se é número, se eh data, se é string, etc) e qual o tamanho desse dado

### Dados x Informação

`Dados` são fatos em uma forma primária que podem ser armazenados em algum meio.

`Informação` são os fatos organizados de maneira a produzir um significado, ou seja, dados colocados em contexto. 

`Metadados` são dados sobre dados, permitem efetuar a representação e identificação dos dados, garantindo sua consistência e persistência. Os metadados são mantidos no `Dicionário de Dados` (ou `Catálogo` de dados)

### Banco de Dados

- Um Banco de Dados (BD) é uma coleção organizada de dados. Esses dados são organizados de modo a modelar aspectos do mundo real, para que seja possível efetuar processamento que gere informações relevantes para os usuários a partir desses dados.
- Um BD é composto por diversos objetos como:
    - tabelas
    - esquemas
    - visões
    - consultas
    - relatórios
    - procedimentos
    - triggers

### SGBD (Sistema de Gerenciamento de Banco de Dados)

- Um SGBD é uma coleção de softwares que permite aos usuários criarem e manterem um ou mais bancos de dados.
- São usados nas tarefas de definição, construçao, manipulação e compartilhamento dos bancos de dados entre aplicações e usuários
- Permitem proteger o banco de dados e mantê-lo ao longo do tempo
- Alguns exemplos são:
    - SQL Server
    - SQLite
    - MongoDB

### Sistema de Bancos de Dados

O Sistema de Banco de Dados eh composto, em ordem, por:
- Usuários
- Aplicativos de Acesso
- SGBD para gerenciamento
- Banco de dados + Metadados

### Modelo de dados

É o conjunto de ferramentas conceituais usadas para descrição dos dados, relacionamentos entre eles, semântica dos dados e regras de consistência. Podem ser dividos em:

- **Modelo Conceitual:** É um projeto que realiza um alinhamento perfeito entre uma área de TI/BD e a área cliente. É o momento de elicitação de requisitos e afins voltado exclusivamente para BD
    - Ele deve ser 100% independente do banco de dados de onde ele está sendo implementado
- **Modelo Lógico:** É a implementação do BD
- **Modelo Físico:** Como os dados estão efetivamente armazenados.
    - Não é algo que dê para ser implementado, é somente como os dados estão armazenados em bits e bytes
- **OBS:** Os dois modelos de dados considerados em um projeto de banco de dados são os modelos `conceitual` e `lógico`.

### **Arquitetura de 3 esquemas/camadas - ANSI / Sparc**

- **Nível físico ou Nível Interno:** descreve `como` os dados estão de fato armazenados dentro do SGBD.
- **Nível lógico ou Nível conceitual:** descreve quais `dados` estão armazenados no banco de dados e seus relacionamentos, tem utilização para quem estrutura o BD.
- **Nível de visão ou Nível externo:** subconjunto de um banco de dados que contem uma `visão virtual` dos dados, derivados dos arquivos do banco de dados, mas não, explicitamente, armazendados. Em resumo, os `apps` que são usados para visualizar o banco de dados (? verificar)

(**Add print aqui**)

**OBS:** 
- **Esquemas:** contêm as descrições dos dados armazenados. São divididos também como os `níveis ou instâncias`, que são os dados de fato armazenados 

Ainda sobre a parte conceitual dos níveis de arquitetura existe um conceito chamado `Independência de dados` que é a capacidade de trabalhar com uma camada inferior do banco de dados sem a necessidade de alterar o que está sendo trabalhado nas camadas superiories. Existem dois tipos:

- **Independência física de dados:** capacidade de modificar o esquema físico sem ter de reescrever os programas de aplicação. Em resumo, alterar o `nível físico` sem passar pelos outros níveis
- **Independência lógica de dados:** capacidade de modificar o esquema lógico sem que qualquer programa de aplicação precise ser reescrito. Em resumo, alterar o `nível lógico`, sem alterar os outros níveis
- **OBS:** não existe `independência interna`, ou `independência conceitual`

**Regras para o modelo Relacional**

Essas regras servem como referência para estruturação de um Sistema de Bancos de Dados Relacionais.

- **Regra 0:** Uso de recursos relacionais para seu gerenciamento (só usar relacional com relacional, não mesclar com orientação a objetos, por exemplo)
- **Regra 1:** Todo dado deve ser representado em tabelas com linhas e colunas
- **Regra 2:** Se um dado está armazenado você precisa garantir que seus usuários terão acesso a ele 
- **Regra 3:** Tratamento sistemático de dados nulos.
- **Regra 4:** Catálogo Online Dinâmico com base no Modelo Relacional. Seus metadados precisam estar armazenados em formato de catálogo
- **Regra 5:** Sublinguagem ampla de dados (SQL)
- **Regra 6:** Atualização de visualização
- **Regra 7:** Inserção, atualização e exclusão de alto nível
- **Regra 8:** Independência Física de Dados
- **Regra 9:** Independência Lógica de Dados
- **Regra 10:** Independência de Integridade
- **Regra 11:** Independência de Distribuição. Os usuários finais e aplicativos não devem conhecer nem serem afetados pela localização de dados
- **Regra 12:** Não transposição das Regras

### Chaves

Uma chave é um `atributo` que você tem na tabela que define `univocamente` um registro, ou seja define a `identidade` de um dado. O conceito é um pouco diferente de `índice` pois o índice serve para realizar pesquisas na tabela, mas consequentemente uma chave tende a ser um índice.
Alguns tipos de chaves são:

- **Super-chave:** Um atributo ou conjunto de atributos que seja identificado como único. (CPF, ou o conjunto da sua data e hora de nascimento com o nome da sua mãe, por exemplo)
- **Chave-candidata ou chave alternativa:** Todo e qualquer atributo ou conjunto de atributos dos quais não fazem sentido virarem super-chaves. Ela é candidata a ser uma chave primária
- **Chave primária:** Também identifica `univocamente` um registro assim como uma super-chave
    - Não pode ser nula
    - Pode ser formado por qualquer tipo de dado
    - Pode ser formada por qualquer quantidade de atributos
    - **Ela é escolhida preferencialmente para referenciar o respectivo registro**
- **Chave-estrangeira:** É um atributo utilizado por uma outra tabela que está referenciando a tabela atual, ou seja, está preferencialmente referenciando a chave primária, mas pode estar referenciando chaves candidatas também.
    - Uma chave estrangeira pode apontar para a chave primária da própria tabela, o que é chamado de `auto relacionamento` ou `relacionamento unário`
    - O conceito de `integridade referencial` é usualmente implementado por meio das chaves estrangeiras que servem como restrições (constraints)
- **Chave Composta**: Chave que é composta de dois ou mais atributos (colunas)
    - Geralmente empregada quando não é possível utilizar uma única coluna de uma tabela para identificar de forma exclusiva seus registros
- **Chave Surrogada (Substituta)**: Valor numérico, único, adicionado a uma relação para servir como chave primária
    - Não possui significado para os usuários e geralmente fica escondida nas aplicações
    - As chaves substitutas são frequentemente usadas no lugar de uma chave primária composta

### Cardinalidade

- Diz respeito ao número de itens que se relacionam nas entidades.
- A cardinalidade pode ser máxima ou mínima, significando respectivamente os número mínimo e máximo de instâncias de cada entidade associadas no relacionamento
- **Cardinalidade Máxima**: Trata-se do número máximo de instâncias de entidade que podem participar em um relacionamento. Pode ser 1 ou N.
- **Cardinalidade Mínima**: Número mínimo de instâncias de entidade que devem obrigatoriamente particpar em um relacionamento; zero é participação opcional e um é obrigatória

**Add imgs aqui**

### Integridade de Dados

- Manutenção e garantia da consistência e precisão dos dados, sendo um aspecto crítico no design, implementação e uso de sistemas de armazenamento de dados
- A integridade é atingida por meio da aplicação de `Restrições de Integridade`. As restrições são:

    - **Integridade Referencial**: Uma restrição de Integridade Referencial assegura que valores de uma coluna em uma tabela são válidos baseados nos valores em uma outra tabela relacionada
        - Ex: Se um produto de ID 524 foi cadastrado em uma tabela de Vendas, então um produto com ID 523 deve existir na tabela de Produtos relacionada
        - **Atualização e Exclusão**: Se um registro for excluído em uma tabela, então os registros relacionados em outras tabelas que o referenciam talvez precisem ser excluídos. O mesmo se dá com a atualização de registros

    - **Integridade de Domínio**: Valores inseridos em uma coluna devem sempre obedecer à definição dos valores que são permitidos para essa coluna - os valores do `domínio`.
        - Ex: em uma coluna que armazena preços de mercadorias, os valores admitidos são do domínio numérico - ou seja, apenas números

    - **Integridade de Vazio**: Este tipo de integridade informa se a coluna é obrigatória ou opcional - ou seja, se é possível não inserir um valor na coluna.
        - Uma coluna de chave primária, por exemplo, sempre deve ter dados inseridos, e nunca pode estar vazia, para nenhum registro
        - **Valores Nulos (NULL)**

    - **Integridade de Chave**: Os valores inseridos na coluna de chave primária (PK) devem ser sempre únicos, não admitindo-se repetições nesses valores.
        - Desta forma, as tuplas (registros) serão sempre distintas.
        - Os valores de chave primária também não podem ser nulos

    - **Integridade Definida pelo Usuário**: Diz respeito às regras de negócio específicas que são definidas pelo usuário do banco de dados.

### MER (Modelo Entidade-Relacionamento)

Trata-se de um `modelo conceitual` usado para descrever objetos envolvidos no domínio de um sistema a ser construído, incluindo seus atributos e relacionamentos. É uma maneira sistemática de descrever e definir um processo de negócio.

O MER permite representar de forma abstrata a estrutura que irá constituir o banco de dados.

É composto pelos seguintes objetos:

- **Entidades**: São os `componentes` modelados no banco, elas são ligadas uams às outras por `relacionamentos` que indicam as dependências entre elas.
    - Representa um tema, tópico ou conceito de negócio do mundo real
    - Cada objeto de uma entidade é denominado de `Instância de Entidade`
        - Ex: A `Entidade` Carro pode possuir as `Instâncias de Entidade` Ford, Citroen, etc
    - Uma entidade pode ter existência física ou abstrata
    - Ex: Empregados, Livros, vendas, produtos...
    - OBS: para nomear a entidade, deve ser usar um substantivo no singular (Empregado, Livro, Venda, etc)

- **Atributos**: São as propriedades que estão nas entidades. Ex: fabricante, modelo, cor, placa, etc.
    - Os atributos possuem um tipo de dados (domínio) nome e valor específico
    - Os atributos podem ser de vários tipos:
        - Simples: Não possui características especiais e são indivisíveis. Ex: CPF, Nome
        - Composto: Pode ser subdividido em outros atributos. Ex: Endereço (Rua, Cep, Bairro)
        - Multivalorado: Quando ele pode ter mais de um valor para um mesmo registro (informação). Ex: Telefone (casa, celular)
        - Determinante: Define as instâncias de entidade de uma entidade. Não podem existir duas instâncias de entidade desse tipo com o mesmo valor. Ex: CPF
        - Identificador (Chave): Uma chave identifica uma instância específica na classe de entidade. Ex: CPF

- **Relacionamentos**: É um `conjunto de registros` (`tuplas`) que represetam um modelo de uma entidade.
- Cada `registro` representa uma instância de entidade, e o conjunto de todas as instâncias, com seus atributos, é chamado de `Relação`
- São as relações entre as entidades, que indicam as dependências entre elas 
- Toda `relação` possui:
    - `Linhas`: Contém dados sobre intâncias de uma entidade (registros)
    - `Colunas`: Contém dados sobre atributos da entidade (campos)
    - Cada célula da tabela armazena um único valor
    - Todos os valores em uma coluna são do mesmo tipo (domínio)
    - Cada coluna possui um nome único
    - Não há duas linhas idênticas. Caso isso aconteça, há duplicação de dados.
    - As relações geralmente geram tabelas no banco
    - Toda Relação é uma tabela, mas nem toda tabela é uma relação

**Add Img aqui**

- As Entidades podem ser conectadas entre si por meio de `Relacionamentos`, que é uma estrutura que indica a associação de elementos de uma ou mais entidades
- Como os dados de diferentes entidades são armazenados em tabelas distintas, geralmente precisamos combinar duas ou mais tablelas para responder às perguntas específicas dos usuários
- Por exemplo, quero saber quais produtos um usuário x comprou, pra isso eu preciso de um relacionamento entre a entidade Usuário e a entidade Produto

**Grau de Relacionamento**:
- O grau de um relacionamento defino número de entidades que participam do relacionamento. Assim, um relacionamento pode ser:
    - Unário (Auto relacionamento, ou Recursivo)
    - Binário
        **Add img aqui**
    - Ternário

**Efetuando relacionamento entre múltiplas tabelas**
- Cada linha de dados em uma tabela deve ser identificada de forma única usando-se uma Chave Primária
- Usamos uma Chave Estrangeira para relacionar os dados entre múltiplas tabelas
- Usamos para isso o relacionamento entre chave primária de uma tabela com a chave estrangeira em outra tabela

Diagramas são criados para representar graficamente entidades, atributos e relacionamentos, denominados `DER (Diagramas Entidade-Relacionamento)`.
Os componentes do DER são:

- **Retângulos**: Representam entidades
- **Elipses**: Represetam atributos
- **Losangos**: Representam relacionamentos
- **Linhas**: Ligam atributos a entidades e entidades a relacionamentos

### Dicionário de dados

- Um dicionário de dados é um documento usado para armazenar informações sobre o conteúdo, formato e a estrutura de um banco de dados, assim como os relacionamentos entre os seus elementos.
- É importante manter um dicionário de dados para limitar erros ao criar a estrutura física do banco de dados no computador.
- Também chamado de `Repositório de Metadados`

**Add img aqui**

### Dependências

**Dependência Funcional**
- Seja E uma entidade, e X e Y dois atributos quaisquer de E. Dizemos que Y é funcionalmente dependente se X se e somente se cada valor de X tiver associado a ele exatamente um valor de Y.
Simbolicamente: `X -> Y` (Lê-se: X determina funcionalmente Y)

Ex: O prazo de entrega de um pedido depende do número do pedido considerado:

```Numero_Pedido -> Prazo_Entrega_Pedido```

O atributo que determina o valor é chamdo de `Determinante`. O outro atributo é chamado de `Dependente`.
Uma chave primária em uma relação determina funcionalmente todos os outros atributos não-chave na linha

- **Dependência Funcional Total**: Em uma relação com uam PK composta, um atributo não-chave que dependa dessa PK como um todo, e não somente de parte dela, é dito como possuindo Dependência Funcional Total.

**Add img aqui**

- **Dependência Fucional Parcial**: Uma dependência funcional é parcial quando os atributos não-chave não dependem funcionalmente de toda a PK quando esta for composta. Ou seja, existe uma dependência funcional, mas somente de uma parte da chave primária.

**ADD img aqui**

- **Dependência Fucional Transitiva**: Ocorre quando um campo não depende diretamente da chave primária da tabela (nem mesmo parcialmente), mas depende de um outro campo não-chave

**Add img aqui**

- **Dependência Funcional Trivial**: Dependência que não pode deixar de ser satisfeita. Uma DF é trivial se o lado direito da expressão é um subconjunto do lado esquerdo.
    - `A -> B` é uma DF trivial se B for um subconjunto de A
    - Ex: `{ID_Func, Nome_Func} -> ID_Func`

**Dependência Multivalorada**
- Ocorre quando, para cada valor de um atributo A, existe um conjunto de valores para outros atributos B e C que estão associados a ele, mas são independentes entre si.
Simbolicamente é representada assim: `A ->> B` (Lê-se: B depende de A)

**Add img aqui**

### Normalização

**Anomalias de Atualização**

- Anomalias são problemas que ocorrem em bancos de dados mal planejados e não-normalizados, geralmente ocorrendo por excesso de dados armazenados em uma mesma tabela.
- São causadas pelas dependências parciais e transitivas.
- As anomalias de atualização são classificadas em anomalias de `inserção`, de `exclusão` e de `modificação`

- **Anomalia de Inclusão**: Não deve ser possível adicionar um dado a não ser que outro dado esteja disponível. Por exemplo, não deve ser permitido cadastrar um novo livro sem que um autor já esteja cadastrado
- **Anomalia de Exclusão**: Ao excluirmos um registro, dados referentes em outra tablea são excluídos. Por exemplo, se excluirmos um autor, os livros desde autor devem ser excluídos também.
- **Anomalia de Modificação**: Ao alterar um dado em uma tabela, dados em outras tabelas precisam ser alterados.
Por exemplo, se o código de um autor for modificado, esse código deve ser modificado na tabela de autrores e na de livros também, para manter o relacionamento entre livros e seus autores corretos.

Para eliminar essas anomalias, é utilizada a `Normalização`

**Normalização**
- Normalização consiste em um processo de análise de uma relação para assegurar que seja `bem formada`.
- Decompor relações com anomalias para produzir relações menores e bem-estruturadas. 
- Ou seja, em uma relação normalizada, podemos inserir, excluir ou modificar registros sem criar anomalias.
- O processo de normalização aplica a um esquema de relação uma série de testes para certificar que ele satisfaá uma `Forma Normal` (FN)
- Existem 3 formas normais

**Objetivos da Normalização**
- Analisar esquemas de relação (tabelas) com base em suas dependêncais funcionais e chaves primárias para:
    1. Minimizar redundâncias
    2. Minimizar anomalias de inserção, exclusão e modificação
- As relaçoes são decompostas em esquemas de relação menores que tendem aos testes de forma normal.
- O ideal é que o projeto do banco de dados relacional alcance a FNBC ou a 3a FN para cada tabela
- Não é adequado normalizar apenas até a 1a FN ou à 2a FN, pois na verdade essas formas normais são usadas para se chegar à 3a FN ou FNBC

**Primeira Forma Normal (1FN)**
- Definida historicamente para reprovar atributos multivalorados, compostos e suas combinações.
- O domínio de um atributo deve incluir apenas valores atômicos (indivisíveis), e o valor de qualquer atributo em uma tupla deve ser único valor do domínio desse atributo.
- Uma tablea está na 1a FN quando:
    - Somente possui valores atômicos
    - Não há grupos de atributos repetidos (há apenas um dado por coluna nas linhas)
    - Existe uma chave primária
    - Relação não possui atributos multivalorados ou relações aninhadas (tabelas dentro de tabelas)
- Exemplo, um campo de Endereço possui subdomínios (Rua, número, CEP). Esses itens devem ser separados no processo e normalização.
- Cada informação deve ser colocada em um campo diferente

**add img aqui**
**add img aqui**

**Segunda Forma Normal (2FN)**
- Baseada no conceito de Dependência Funcional Total
- Um esquema de relação R está na 2FN se cada atributo não-chave de R for total e funcionalmente dependente da PK de R
- Para testar a 2FN, testamos as dependências funcionais cujos atributos fazem parte da chave primária
- Caso a PK tenha um único atributo, esse teste não precisa ser aplicado
- Uma tabela está na 2FN se:
    - Está na 1FN
    - Todos os atributos não-chave são funcionalmente dependentes de todas as partes da chave primária
    - Não existem dependências parciais
    - Caso contrário, deve-se gerar uma nova tabela com os dados
    - Deve-se criar uma nova relação para cada chave PK ou combinação de atributos que forem determinantes em uma dependência funcional
    - Esse atributo será a PK na nova tabela
    - Mova os atributos não-chave dependentes desta PK para a nova tabela

**Add img aqui**
**Add img aqui**

**Terceira Forma Normal (3FN)**
- Baseada no conceito de `Dependência Transitiva`
    - Uma dependência transitiva em uma tabela é uma dependência funcional entre dois ou mais atributos não-chave
- A relação não deve ter um atributo não-chave determinado funcionalmente por outro atributo não-chave (ou conjunto)
- Não deve haver dependência transitiva de um atributo não-chave sobre a PK
- Deve-se decompor e montar uma nova relação que inclua os atributos não-chave que determinam funcionalmente outros atributos não-chave
- Uma tabela está na 3FN se:
    - Estiver na 2FN
    - Não existirem dependências transitivas
    - Uma tabela está na 3FN se ela estiver na segunda forma normal e se nenhuma coluna não-chave depender de outra coluna não-chave
- Para cada atributo (ou grupo) não-chave que for um determinante na relação, crie uma nova tabela
- Esse atributo será a PK na nova relação.
- Mova então todos os atributos que são dependentes funcionalmente do atributo chave para a nova tabela
- O atributo (PK na nova relação) fica também na tabela original, e servirá como uma chave estrangeira para associar as duas relações

**Add img aqui**
**Add img aqui**
**Add img aqui**

**FN de Boyce-Codd**
- A definição original da 3FN de Codd não lidava adequadamente com uma relação que:
    - Tivesse duas ou mais chaves candidatas
    - Essas chaves candidatas fossem compostas
    - Elas tivessem superposição (atributos em comum)
- Caso a combinação das condições acima não ocorra em uma tabela, basta aplicar a 3FN
- Uma relação está em FNBC se e somente se os únicos determinantes são `chaves candidatas`
- Cada relação na FNBC também está na 3FN, mas uma relação na 3FN não necessariamente está na FNBC
- Quando uma tabela possui mais de uma chave candidata, podem ocorrer anomalias
- Na FNBC as chaves candidatas não possuem dependências parciais por outros atributos
- Uma relação (tabela) R está na FNBC sempre que uma dependência funcional não-trivial `X -> A` se mantiver em R, assim X é uma `superchave` de R.

**Add img aqui**

- Para normalizar uma tabalea até a FNBC devemos decompor a tabela com os passos a seguir:
    - Encontrar uma dependência funcional não-trivial `X -> Y` que viole a condição de FNBC. X não deve ser uma superchave.
    - Dividir a tabela em duas: Uma com os atributos XY, ou seja, todos os atributos da dependência
    - Outra com os atributos X juntamente com os atributos restantes da tabela original.

**Add img aqui**
**Add img aqui**
**Add img aqui**

#### Operações de BD

- INSERT: 
- Triggers: Serve para monitorar e registrar operações de INSERT e UPDATE
- Cursores: Demarcadores específicos na base de dados
- Stored procedures: Procedimentos de armazenamento, como procedimento de looping
- DELETE CASCADE: Deleta todos os dados da coluna (atributo) juntamente com as colunas que estão sendo referenciadas pelas chaves estrangeiras que estão nessa coluna 

## Arquitetura Orientada a Serviços (SOA) [baseada em serviços]

A Arquitetura Baseada em Serviços (SOA) é um paradigma de design de sistemas de software que enfatiza a criação de serviços independentes e interoperáveis que podem ser reutilizados e combinados para atender a várias necessidades de negócios. Essa abordagem arquitetônica é amplamente usada na construção de sistemas de TI escaláveis, flexíveis e orientados a serviços. Vamos explorar os principais aspectos da Arquitetura Baseada em Serviços:

1. Serviços:

No contexto da SOA, um serviço é uma unidade de funcionalidade ou lógica de negócios que está disponível na rede e pode ser acessada e invocada remotamente. Cada serviço deve ter um conjunto bem definido de interfaces, que especificam como o serviço pode ser utilizado.

2. Princípios da SOA:

A SOA é baseada em alguns princípios fundamentais:

- Reutilização: Os serviços são projetados para serem reutilizados em diferentes partes de uma aplicação ou em diferentes aplicações.
- Interoperabilidade: Os serviços devem ser capazes de se comunicar com outros serviços, independentemente da plataforma ou tecnologia usada.
- Descoberta: Os serviços podem ser descobertos e consumidos dinamicamente por meio de diretórios de serviços.
- Granularidade: Os serviços devem ser granulares o suficiente para serem úteis, mas não tão pequenos a ponto de tornar a administração complicada.
- Abstração: A complexidade dos serviços deve ser ocultada dos consumidores por meio de interfaces bem definidas.

3. Componentes-Chave da SOA:

Os principais componentes de uma arquitetura SOA incluem:
Serviços: As unidades funcionais que encapsulam a lógica de negócios.
- Registro de Serviços: Um diretório onde os serviços são registrados e podem ser descobertos.
- Orquestração: A capacidade de compor serviços para criar processos de negócios complexos.
- Coreografia: A coordenação de serviços independentes para atender a necessidades de negócios.
- Padrões de Comunicação: Protocolos e padrões que permitem a comunicação entre serviços.

4. Vantagens da SOA:

A SOA oferece várias vantagens, incluindo:
Reutilização de código e funcionalidade.
- É uma arquitetura fracamente acoplada, ou seja, qualquer módulo pode ser facilmente trocado sem que isso quebre a aplicação como um todo
- Maior flexibilidade e agilidade para as organizações.
- Facilita a integração de sistemas heterogêneos.
- Melhora a escalabilidade e a manutenibilidade de sistemas.
- Suporta a exposição de funcionalidades para parceiros e clientes por meio de APIs.

5. Desafios da SOA:

Implementar uma arquitetura SOA também apresenta desafios, como:
- Gerenciamento de serviços e versões.
- Garantir a segurança dos serviços.
- Abordar questões de desempenho e latência.
- Planejamento e governança adequados.

6. Observações

- Webservice não é a única maneira de implementar o SOA

## Arquiteturas de Web Services (+Material)

1. Enterprise Service Bus (ESB)

- Permite que consumidores de serviço consigam acessar os serviços oferecidos por um provedore sem conhecer seu endpoint (OpenESB, Mule, Microsoft Big Talk, etc)

2. Orquestração

- Composição de processo de negócio
- Nó central que coordena os demais processos (Orchestrator)
- Só o processo mestre sabe que faz parte de uma composição de processos

3. Coreografia

- Composição de processo de negócio, só que sem a figura de um processo central

## Modelagem de Processo de Negócio (BPM) (+Material)

0. Conceito de Processo

- Conjunto definido de atvs executadas para alcançar metas
- Podem ser executados por humanos ou máquinas

1. O que é Modelagem de Processo de Negócio?

- Conhecimento e análise dos processo e seu relacionamento com os dados
- Estruturado em uma visão top down
- O mapeamento começa com o levantamento da situação atual (as is)
- Otimização e modelagem do estado desejado dos processo (TO BE )

## Kubernetes

### Conceitos (+Material)

- Containers: É uma espécie de máquinas virtuais simples, configurados para rodar o ambiente para uma aplicação específica e que você pode ter vários rodando em um mesmo computador
    - Um container é um isolamento, pode ser de recursos, de processos.
    - Esses isolamentos são feitos através dos **namespaces** e dos **Cgroups** que fazem o gerenciamento de memória
    - Existem dois tipos de containers: os engines, e os runtime
    - Container engine: é responsavel por fazer o container estar em execução, por adicionar storage ao container, fazer o gerenciamento do container
    - Container runtime: Serve para ligar e desligar containers. São dividos em dois tipos, baixo nível e alto nível. 
        - Baixo nível(runC): Fala diretamente com o kernel
        - Alto nível(containerD para o Kubernetes): Fala com o container engine

- Pods: É a mínima unidade de um Kubernete
    - Ele pode ter um ou mais containers

- Kubernetes: É um orquestrador de containers
    - O Kubernetes só precisa do container engine

- Cluster: Um conjunto de computadores com uma aplicação Kubernetes rodando. Serve para manter a aplicação rodando, caso um nó (máquina) caia, tem o outro
    - Pode ser dividido em duas partes:

    - Control Plane: A parte de controle, gerenciamento do Kubernetes, pode ser uma ou várias máquinas para manter a redundância e preservar a saúde do Kubernete
        - No Control Plane possui um ambiente chamado ETCD, que é um banco de dados que guarda todos os status do cluster
            - Sua porta, chamada etcd Server é a 2379 ou a 2380
        - Scheduler: eh um agendador, que gerencia os recursos do cluster
            - Sua porta eh 10251
        - Controller Manager: Responsável por gerenciar os controladores
            - Sua porta é 10252
        - API Server: Ele interage com todos os outros controladores e os Workers, porém o ETCD interage somente com ele
            - Sua porta é a 6443, do tipo TCP

    - Workers: São os nós com as execuções do containers, dentro dele estão:
        - Kubelet: É um gerenciador de nó do Kubernete. Caso o seu cluster tenha 3 computadores, haverão 3 Kubelets
            - Ele conversa com o container runtime de alto nível (containerD)
            - Sua porta é a 10250
        - Kube Proxy: Responsável por fazer com que o cluster consiga acessar os PODs que estão no nó 
        - Pod: é a menor parte da Kubernet
        - Replica set: Eh o responsável por gerenciar os Pods em execução. Ele é gerenciado pelo Deployment
        - Deployment: Define a quantidade de réplicas dos pods que serão criadas
        - Service: Ele é responsável por estabelecer a conexão dos pods. Ele cria os IPs dos Pods. Podem ter 3 tipos:
            - NodePort
            - Load Balancer
            - Cluster IP

    - Se você está em um servidor (AWS por exemplo), você não consegue controlar o Control Plane, somente os Workers

## Kubernetes Avançado (+Material) (Rever vídeo)

### Material Utilizado

-

### Conteúdo

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

## ITIL4 (+Material)

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

## Modelagem de Processos BPMN (+Material)

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

## Design Patterns (GOF) (+Material) (Fazer questões pra ver se precisa de mais material)

Os Design Patterns (Padrões de Projeto) são soluções reutilizáveis para problemas comuns que surgem durante o desenvolvimento de software. Eles fornecem diretrizes e abstrações que ajudam a estruturar e organizar o código de maneira eficaz. Existem três categorias principais de Design Patterns: Padrões de Criação, Padrões Estruturais e Padrões Comportamentais. Vamos explorar cada uma delas:

### **Padrões de Criação:**
Esses padrões se concentram na maneira de criar objetos ou classes. Eles ajudam a tornar a criação de objetos mais flexível e independente do sistema.

1. **Singleton Pattern:** Garante que uma classe tenha apenas uma instância e fornece um ponto de acesso global para essa instância.

2. **Factory Method Pattern:** Define uma interface para criar objetos, mas permite que as subclasses escolham as classes concretas a serem instanciadas.

3. **Abstract Factory Pattern:** Fornecer uma interface para criar famílias de objetos relacionados ou dependentes sem especificar suas classes concretas.

4. **Builder Pattern:** Separa a construção de um objeto complexo de sua representação, permitindo a criação de diferentes representações do mesmo objeto.

5.**Prototype Pattern:** Cria novos objetos duplicando um objeto existente, conhecido como protótipo.


### **Padrões Estruturais:**
Esses padrões se concentram na composição de classes e objetos para formar estruturas maiores. Eles ajudam a definir a estrutura de um sistema de maneira flexível e eficiente.

- Dica de decoração:
    - A ponte (Bridge)
    - Adaptada (Adapter)
    - é Composta (Composite)
    - de Decorações (Decorator)
    - na Fachada (Facade)
    - para o Peso Mosca (Flyweight)
    - se Aproxymar (Proxy)

1. **Adapter Pattern:** Permite que objetos com interfaces incompatíveis trabalhem juntos, convertendo a interface de um objeto em outra esperada pelo cliente.
- Resumidamente é criar uma classe intermediária que unifica uma classe previamente criada de outra que você já está desenvolvendo
- Dica de questões:
    - Sempre que tiver a palavra "incompatível" provavelmente vai ser Adapter a solução

2. **Composite Pattern:** Permite que você componha objetos em estruturas de árvore para representar hierarquias de partes-todo.
- É usado onde precisamos manipular um ou mais objetos similares de forma similar
- Essas estruturas são trabalhadas como se elas fossem objetos individuais
- Dica de questões:
    - Sempre que tiver a palavra "hierarquia" ou "coexistem objetos" ou "agregados de objetos da mesma espécie" ou "partes-todo" provavelmente eh Composite.

3. **Proxy Pattern:** Fornece um substituto ou intermediário para controlar o acesso a um objeto.

4. **Decorator Pattern:** Anexa responsabilidades adicionais a um objeto dinamicamente. É uma alternativa flexível à herança para estender a funcionalidade de classes.
- Dica de questões:
    - Sempre que tiver a frase "resposabilidades adicionais a um objeto dinamicamente" ou "extensão de funcionalidades" geralmente é Decorator

5. **Bridge Pattern:** Separa uma abstração (interface) de sua implementação, permitindo que ambas evoluam independentemente.
- Permite que se divida uma classe grande ou um conjunto de classes intimamente ligadas em duas hierarquias separadas (Abstração e interpretação)
- Resumindo é só criar uma abstração com uma interface e aí você cria a classe que herda essa abstração.

6. **Facade Pattern:** Representa uma única classe que representa um subsistema inteiro
- Fornece uma interface simplificada para bibliotecas, frameworks ou qualquer conjunto complexo de classes
- Dicas de questoes:
    - Quando tiver a palavra "subsistema" ou "interface unificada" geralmente é Facade

7. **Flyweight Pattern:** Representa uma instância refinada usada para compartilhamento eficiente
- Permite colocar mais objetos na uqantidade de RAM disponível ao compartilhar partes comuns de estado entre os múltiplos objetos ao invés de manter todos os dades em cada objeto


**Padrões Comportamentais:**
Esses padrões se concentram na comunicação e colaboração entre objetos. Eles definem como os objetos interagem e distribuem responsabilidades.

Existem 11 padrões:

1. **Observer Pattern:** Define uma dependência um-para-muitos entre objetos para que quando um objeto mude de estado, todos os seus dependentes sejam notificados e atualizados automaticamente.
- Propagação reativa: É um paradigma de programação declarativa relacionado aos fluxos de dados e à propagação da mudança nesses fluxos
- É uma versão estendida e mais poderosa que o Observer
    - Tem os observables (emitem os dados) e os Observers (respondem aos dados emitidos)
- Dicas de questão:
    - Sempre que tiver a frase "um-para-muitos" ou "notificação de objetos" ou "mudança de estado de um objeto atualiza outro", geralmente é Observer
- Um dos padrões mais importantes do `MVC`

2. **Strategy Pattern:** Define uma família de algoritmos, encapsula cada um deles e os torna intercambiáveis. Isso permite que o algoritmo varie independentemente dos clientes que o usam.

3. **Command Pattern:** Encapsula uma solicitação como um objeto, permitindo que você parametrize clientes com solicitações, enfileire-as, registre solicitações e forneça funcionalidades de desfazer.

4. **State Pattern:** Permite que um objeto altere seu comportamento quando seu estado interno muda. O objeto parecerá ter mudado sua classe.

5. **Chain of Responsibility Pattern:** Passa solicitações ao longo de uma cadeia de manipuladores. Cada manipulador decide processar a solicitação ou passá-la para o próximo manipulador na cadeia.

6. **Mediator:** Define a comunicação simplificada entre classes. Permite reduzir dependências caóticas entre objetos. Restringe as comunicações diretas entre os objetos. Força-os a colaborar apenas por meio de um objeto mediador. 
- Dicas de questões:
    - Sempre que a frase "prove baixo acoplamento" e "evitar que haja referências diretas entre objetos" geralmente é Mediator

7. **Memento:** Captura e restaura o estado interno de um objeto. Permite salvar e restaurar o estado anterior de um objeto sem revelar os detalhes de sua implementação 
- Dicas de questões:"
    - Sempre que tiver as palavras "capturar e externalizar um estado interno" ou "restaurar o estado de um objeto" geralmente é Memento

## GRASP (General Responsibility Assisgnment Software)

Os padrões GRASP consistem de um conjunto de práticas para atribuição de responsabilidades a classes e objetos em projetos orientados a objeto.
Os padrões são:

1. Controller (MVC)
2. Criator (Factory Method)
3. Indirection
4. Information Expert
5. High Cohesion
6. Loose Coupling
7. Polymorphism
8. Protected Variations
9. Pure Fabrication

## Gestão de Projetos (PMBOK)

### Dicas de Questões

- Saber as siglas:
    - `PMI`: Organização Internacional de Gestão de Projetos
    - `PMBOK`: Guia publicado pelo PMI 
    - `PMP`: Profissional com certificado de gerente de projeto
    - `PMO`: Escritório de projetos

### Gestão de Projetos

- A aplicaçao de conhecimentos, habilidades, ferramentas e técnicas às atividades do projeto para cumprir os requisitos definidos, O gerenciamento de projetos refere-se a orientar o trablaho do projeto para entregar os resultados pretendidos.
- Pode ser dividido em 3 categorias:

**Projeto**

- É um esforço `temporário` empreendido para criar um produto, serviço ou resultado `único`
- Não significa que é `curto prazo`
- Projetos impulsionam mudanças e devem auxiliar na `implantação da estratégia`
- Projetos possuem algum nível de restrição sempre
- Projetos desenvolvem-se em fases ou ciclos de vida
- Projetos são diferentes de `processos`, pois tratam-se `agregação de atividades` e comportamentos executados para alcançar um ou mais resultados

**Programa**

- Um grupo `relacionado de projetos`, subprogramas e atividades de programa gerenciados de forma coordenada para a obtenção de benefícios que não estariam disponíveis se eles fossem gerenciados individualmente

**Portfólio**

- Projetos, programas, subportfólios e operações gerenciadas em grupo para alcançar objetivos estratégicos

### Restrições presentes na gestão de projetos

- As restrições são `circunstâncias que afetam as entregas de um projeto`. As restrições podem assumir a forma de datas de entrega fixa, conformidade com códigos regulatórios, orçamentos predeterminados, políticas de qualidade, considerações sobre o tripé da sustentabilidade, dentre outras. Algumas restrições são:
    - Escopo (Conjunto de entregas de um projeto)
    - Tempo
    - Custo
    - Recursos
    - Riscos
    - Critérios de governança organizacional

### Gerindo riscos em projetos

**Risco**

- É um evento ou condição `incerta` que, se ocorrer, provocará um efeito `positivo ou negativo` em um ou mais objetivos do projeto
- O risco ao longo do projeto vai `diminuindo`

Existem 4 estratégias para prevenção de riscos:

- **Prevensão**: É uma estratégia de resposta ao risco em que a equipe do projeto age par `eliminar a ameaça` ou `proteger o projeto` contra seu impacto
- **Transferência**: É uma estratégia de resposta ao risco em que a equipe do projeto `transfere o impacto` de uma ameaça para terceiros, juntamente com a resposabilidade pela sua reposta
- **Mitigação**: É uma estratégia de resposta ao risco em que a equipe do projeto age para `reduzir a probabilidade de ocorrência, ou impacto do risco`
- **Aceitação**: É uma estratégia de resposta pela qual a equipe do projeto `decide reconhecer a existência do risco e não agir`, a menos que o risco ocorra.

### Gerindo o escopo e mudanças nos projetos

- Controlar o escopo é o processo de monitoramento do progresso do escopo do projeto e do escopo do produto e `gerenciamento das mudanças` feitas na linha de base do escopo. O principal benefício deste processo é permitir que a linha de base do escopo seja mantida ao longo de todo o projeto.
- O custo de mudança vai `aumentando` ao longo do projeto
- Os `níveis de influência` dos stakeholders `diminuem` à medida que os custos de mudança aumentam

#### Ciclo de vida de um projeto

- Ciclo de vida do projeto é uma série de fases pelas quais um projeto passa desde seu início até sua conclusão
- Um projeto passa por 4 fases dentro de um ciclo de vida:
    - Início
    - Organização / Preparação
    - Execução
    - Término do projeto

**Grupos de processos de gerenciamento de projetos**

No PMBOK 6a edição, temos 49 processos de gestão de projetos divididos em 5 grupos de processos:
- **Iniciação**: Ocorre no ínicio do ciclo de vida
    - **Termo de abertura do projeto (TAP)**: documento emitido pelo patrocinador do projeto que autoriza formalmente a sua existência e fornece ao gerente de projetos a autoridade para aplicar recursos organizacionais nas atividades do projeto.
- **Planejamento**: Ocorre no período de organizaçao do ciclo de vida.
    - **Estrutura Analítica do Projeto (EAP)**: O processo de subdividir as entregas e o trabalho do projeto em componentes menores e mais facilmente gerenciáveis. Todo o trabalho nos níveis mais baixos tem que escalar aos níveis mais altos para que nada seja omitido e nenhum trabalho extra seja executado.
- **Execução**: Ocorre no período de execução do ciclo de vida
- **Monitoramento e controle**: Ocorre ao londo de todo o ciclo de vida
- **Encerramento**: Ocorre no término do projeto

### PMBOK 7 (+Material)


## Scrum (Fazer questões +Material)

- Os 3 `pilares empíricos do Scrum` são:
    - Transparência
    - Inspeção
    - Adaptação

- Framework para desenvolver, entregar e manter produtos complexos
- Consiste de times Scrum associados a papéis, eventos, artefatos e regras
- Ideal para times pequenos
- Ele não é somente uma metodologia ágil de `desenvolvimento`, ele serve para gerenciar projetos de maneira geral

**Time Scrum**
- Consiste em um Product Owner, o Time de Desenvolvimento e um Scrum Master
- Auto-organizáveis e multifuncionais
- Entregam produtos de forma iterativa e incremental

### Sprints
- Os processos são divididos em ciclos chamados de `sprints`
- Eh o intervalo de tempo em que será criado um incremento de produto
- Cada sprint possui prazos e objetivos específicos
- Cada sprint contem: planejamento da Sprint, reuniões diárias, desenvolvimento, revisão da Sprint e retrospectiva da Sprint
- O escopo pode ser clarificado e renegociado entre o Product Owner e o Time de Desenvolvimento quanto mais for aprendido
- Somente o `Product Owner` tem a autoridade para cancelar a Sprint
- A sprint poderá ser cancelada se o objetivo da sprint se tornar obsoleto
- Todos os itens de Backlog do Produto incompletos são reestimados e colocados de volta no Backlog do Produto

**Planejamento da Sprint**

- Define o trabalho a ser realizado na Sprint
- *time-boxed* com no máximo 8 horas para uma Sprint de um mês de duração
- O que pode ser entregue como resultado do incremento da próxima Sprint?
- Como o trabalho necessário para entregar o incremento será realizado?
- O `Backlog da Sprint`, resultado do Planejamento da Sprint, é composto pelos `itens seleciondos do Backlog do Produto`, a `meta da Sprint` e um `plano de entrega` para cada um dos ítens.

**Reunião Diária**

- Evento de 15 min para o time de desenvolvimento
- Planeja o trabalho para as próximas 24 hrs
- O que eu fiz ontem que ajudou o Time de Dev a atingir a meta da Sprint?

**Ciclo Scrum**

Product backlog -> Sprint backlog -> 2-4 semanas (dailies) -> Incremento entregável do produto

**Revisão da Sprint**

- Realizada no final da Sprint para inspecionar o incremento e adaptar o Backlog do Produto se necessário
- O time Scrum e as partes interessadas colaboram sobre o que foi feito
- O resultado da Revisão da Sprint é um Backlog do Produto revisado que define os prováveis itens de Backlog do Produto para a próxima Sprint

**Retrospectiva da Sprint**

- Oportunidade para Time Scrum inspecionar a si próprio e criar um plano para melhorias a serem aplicadas na próxima Sprint
- Ocorre depois da Revisão da Sprint e antes do planejamento da próxima Sprint
- Ao final da Retrospectiva da Sprint, o Time Scrum deverá ter identificado melhorias que serão implementadas na próxima Sprint

### Papéis

**Product Owner**

- Expressar claramente os itens do Backlog do Produto
- Ordenar os itens do Backlog do Produto para alcançar melhor as metas e missões
- Otimizar o valor do trabalho que o Time de Desenvolivmento realiza
- Garantir que o Backlog do Produto seja visível, tranparente, claro para todos, e mostrar o que o Time Scrum vai trabalhar a seguir
- Garantir que o Time de Desenvolvimento entenda os itens do Backlog do Produto no nível necessário

**Scrum Master**

- Servidor líder
- Garante que as cerimônias sejam realizadas

**Time de Desenvolvimento**

- Auto-organizados
- Multifuncionais
- Não reconhece títulos para os integrantes
- Não reconhece sub-times
- Responsabilizaçao do time como um todo

## CObiT 2019 (+Material)

### Material Utilizado

### Cascata de Objetivos

- A cascata de obetivos traduz necessidades de stakeholders em objetivos corporativos, que, por sua vez, são traduzidos em objetivos de alinhamento e, finalmente, em objetivos de governança e gerenciamento.

### Governança Corporativa de Tecnologia e Informação (EGIT)

- Os 3 benefícios principais da Governança de TI são:
    - Criação de Valor (Realização de Benefícios): Manter ou aumentar o valor derivado de investimentos de TI
    - Otimização de Riscos: Visa a preservar o valor gerado
    - Otimização de Recursos: Garante que os recursos necessários estão disponíveis para executar os planos estratégicos
- A governaça de informação e tecnologia (I&T) pode estar fora do departamento de TI também
- I&T corporativos engloba toda a informação e tecnologia que:
    - A organização gera;
    - Processa;
    - Usa para alcançar seus objetivos

**Papel da Informação e Tecnologia (I&T)**
- Fundamental para sustentar a empresa (sustentabilidade)
- Crucial no suporte
- Essencial para o cresimento das organizações
- Hoje as organizações dependem cada vez mais da "digitização" e transformação digital e de um modelo de governaça corporativo alinhado à de I&T

**O que o Cobit faz:**
- Define e descreve todos os componentes que você precisa para tomada de decisões e quem deve tomar essa decisão

**Add img aqui**
**Add img aqui**

- O cobit não contradiz orientação nas normas relacionadas

## Testes de Software

### Material de Estudo

- https://www.youtube.com/watch?v=xuzcp7_1orM

### Verificação x Validação

- **Verificação**: Avaliar se as funções estão corretas
    - Se o produto está sendo criado corretamente de maneira técnica

- **Validação**: Se o produto está em conformidade com os requisitos
    - Se está criando o produto certo

### Medidas de teste

- **Cobertura**: É a `abrangência do teste` e é expressa pela `cobertura dos requisitos e casos de teste` ou pela `cobertura do código` executado
    - O quanto o teste é completo?

- **Qualidade**: É a `confiabilidade`, de estabilidade e de desempenho do objetivo do teste (sistema ou aplicativo em teste)
    - O quanto o teste é confiável?

### Métricas (+Material)

- Complexidade Ciclomática

### Estratégia de Testes x Processo de Software

Os `tipos de testes` em ordem de mais alto nível para mais baixo nível são:

- **Teste de sistema**: Testes de software e outros elementos como um todo
    - Exercita totalmente o sistema
    - Teste de recuperação
    - Teste de segurança
    - Teste por esforço (Stress)
    - Teste de sensibilidade
    - Teste de disponibilização (ou de configuração)
    - Teste de percurso cognitivo:
        - Baseado na engenharia cognitiva, avalia, através da exploração da interface, a facilidade de aprendizado por exploração de um sistema
        - As tarefas dos usuários são decompostas em ações, sequência de passos necessários para realizar a tarefa.
        - O avaliador analisa cada ação tentando se colocar no lugar do usuário
        - Anota-se as características de usabilidade problemáticas

- **Teste de validação**: Teste de requisitos
    - Garantia final de que o software satisfaz aos requisitos informativos, funcionais, comportamentais e de desempenho
    - Ele é dividido em:
        - **Revisão da configuração**: Verificar se os elementos de configuração são adequados
        - **Teste alfa**: Instalações do desenvolvedor em um ambiente controlado onde o dev registra os erros
        - **Teste beta**: instalações do cliente em um ambiente controlado onde o cliente relata os erros
        - **Teste de de aceitação do cliente**: Variação do beta onde o cliente executa testes específicos para descobrir erros


- **Teste de integração**: Teste de projeto e construção da arquitetura
    - Testa a integraçao dos componentes e garante a confiabilidade do software

    - As `abordagens convencionais` são:
        - **Big Bang**:
            - Todos os componentes ao mesmo tempo
        - **Incremental Descendente (top-down)**:
            - Integração em pequenos incrementos começando com os módulos de controle principais e indo para os atômicos
        - **Incremental Ascendente (bottom-up)**:
            - Integração em pequenos incrementos começando com os módulos atômicos e indo para os principais

    - As `abordagens especiais` são:
        - **Teste de regressão**: Reexecução de um subconjunto de testes para verificar efeitos colaterais
        - **Teste de fumaça (smoke)**: Expor erros em uma build

- **Teste de unidade**: Teste de cada unidade do software
    - Focaliza no funcionamento de cada componente individualmente
    - Enfoca a lógica interna de processamento e as estruturas de controle
    - Pode começar antes ou depois da codificação (TDD)
    - Considerado um auxiliar na etapa de codificação

### Teste de caixa branca x Teste de caixa preta

- **Teste de caixa branca**: Verifica o `funcionamento interno do sistema`, eh um `teste estrutural`
    - Teste de caminho básico
    - Teste de condição
    - Teste de fluxo de dados
    - Teste de ciclo (loop)

- **Teste de caixa preta**: Verifica a `função sem conhecer internamente`, é um `teste comportamental ou funcional`
    - Métodos de teste com base em grafo
    - Particionamento de equivalência
    - Análise de valor limite (ou limítrofes)
    - Teste de matriz ortogonal
    - Teste baseado em modelos

- **Teste de caixa cinza**: Caixa Branca + Caixa Preta

### TDD

Primeiro você escreve o teste para depois implementar a funcionalidade

1. Adicione um teste
2. Execute o teste e observe o resultado
3. Escreva o código
4. Execute os testes automatizados
5. Refatore o código

---

## Machine Learning

### Material de Estudo

- https://www.youtube.com/watch?v=L8mbZzoqxCo

### Introdução

- O que é inteligência:
    - Lógica
    - Compreensão
    - Aprendizado (É o mais focado atualmente)
    - Consciência
    - Raciocínio
    - Planejamento ...

- Machine Learning vs Programação Clássica:
Em machine learning, você fornece dados e exemplos de resultados para a máquina e ela é capaz de gerar as regras para a criação desses dados, com uma certa porcentagem de acerto

```
Dados    ___
            |
             ---> Regras
Exemplos ___|
de resultados
```

- Diferente da programação clássica, onde você fornece os dados e as regras para a máquina e a partir disso ela gera os resultados

```
Dados  ___
          |
           ---> Resultados
Regras ___|
```
- Os custos de regras aprendidas é alto na programação clássica, entao, utilizando Machine Learning você consegue produzir as regras de maneira mais rápida

### Definições

- **Inteligência Artificial (IA)**: Sistemas computacionais que podem aprender e raciocinar com autonomia
- IA > Machine Learning (ML) > Deep Learning (DL)
- **Machine Learning ou Aprendizado automático**: Desempenho em uma tarefa aumenta com experiência extraída de novos dados

### Aprendizado: Supervisionado vs Não Supervisionado

- O que irá guiar o processo de aprendizagem?
- **Supervisionado**: Conhecemos exemplos daquilo que queremos prever.
- **Não Supervisionado**: Não temos um alvo apra guiar o aprendizado, então procuramos agrupar dados similares. `Agrupamentos` (clustering: k-means, hierárquico) ou `regras de associação` (Apriori)
- **Por reforço**: Periodicamente recebemos uma recompensa quanto à qualidade das ações passadas. Ex: placar de um jogo.

### Categorias de Aprendizado

- **Supervisionado**: Existem dois tipos de categorias
    - **Classificação**: Quando há alvos definidos e você aumeja treinar seu algoritmo para determinar se seus dados pertencencem a quais alvos
    - Aquilo que eu tento prever é uma variável categórica, com um número limitado de possíveis valores
        - Exemplo 1: Existem dois gêneros, masculinos e femininos. A partir de dados, quais dados são classificados como masculinos e quais são classificados como femininos?
        - Exemplo 2: A partir de uma série de dados fornecidos do eleitor, qual eh o estado ao qual ele pertence?
    - **Avaliando Classificação**:
        - Principal métrica: taxa de acerto ou acurácia
        - **Acurácia**: número de acertos / número total de predições
        - **Classificação binária**: só duas possíveis classes: (0 ou 1), (V ou F)
        - **Matriz de confusão**: matriz de número de ocorrências. Cada linha representa ocorrências da classe verdadeira e cada linha de ocorrências da classe predita

    - **Regressão**: Existem ao invés de alvos, níveis ou percentuais que seus dados podem conter. O algoritmo precisa determinar qual a porcentagem ou o nível de determinado dado.
    - Aquilo que eu tento prever é uma variável contínua de infinitos valores
        - Exemplo 1: Qual o nível de masculinidade de determinada foto?
        - Exemplo 2: Prever a renda média que uma pessoa declarou no imposto de renda a partir dos seus dados

- **Não Supervisionado**:
    - **Agrupamento**
    - **Redução de Dimensionalidade**
    - **Regras de Associação**
    - **Sistemas de recomendação**

### Matriz de Confusão

**Add img aqui**
**Add img aqui**
**Add img aqui**

## Javascript

### Material Utilizado

- https://www.youtube.com/watch?v=5T1PJrStSME&list=PLBKXa8XfK1igcc6FbGh_zBP8NssIPtVWd&index=4
- https://questoes.grancursosonline.com.br/aluno/filtro/concursos?banca=102&desatualizada=0&anulada=0&query=Javascript (Principal)

### Introdução

- É uma linguagem de programação
- Adiciona interatividade a uma página web
- Permite criar aplicações web ricas
- Funciona tipicamente no front-end
- Não é obrigatório o uso de `;` no fim de cada linha mas é recomendado


### Básicos

- Para alterar um elemento no HTML usando javascript você precisa primeiramente `buscar esse elemento`
- `document`: responsável por acessar o `DOM` (Modelo de Objeto de Documento) da página um elemento na árvore de elementos
    - A árvore de elementos contém todos os elementos da página e está dentro do DOM

No HTML temos:

```HTML
<body>
Exemplo: <p id="exemplo"></p> <!-- O que queremos alterar -->
<script src="">main.js</script> <!-- Onde o código javascript está inserido -->
</body>
```

Queremos alterar o elemento com o id 'exemplo' (pode ter aspas duplas ou simples, tanto faz). Para isso utilizamos:

```Javascript
// main.js
var exemplo = document.getElementById('exemplo')
exemplo.innerHTML = "Hello World"; //innerHTML pega somente o elemento interno do objeto, ao invés do elemento todo (<p id="exemplo"></p>) 

/* Output:
/ Exemplo: Hello World
*/
```

## Microsserviços

### Material Utilizado

- https://www.youtube.com/watch?v=tjJuM1r5AFM 
- https://www.youtube.com/watch?v=i-NuIdXPZCA (Principal)

### Introdução

- **Sistema Típico (Arquitetura Monolítica)**
    - Arquitetura com 3 camadas distintas
        - Front-end: Interface com o cliente, recebe as requisições do usuário
        - Back-end: Efetua a lógica de negócio
        - Database: Repositório de dados, banco de dados
    - A escalabilidade é mais difícil de ser implementada dessa forma, para isso existe a `Arquitetura em Microsserviços`

- **Arquitetura de Microsserviços**
    - Os serviços são
      - Pequenos
      - Autônomos
      - Isolados e altamente coesos
      - Trabalham em conjunto
      - Escaláveis
      - Tecnologicamente diversos
    - O barramento de comunicação não possui lógica
      - Dumb pipes, smart endpoints
    - A comunicação pode ser `Síncrona` e `Assíncrona`
    - Possuem um `escopo de aplicação`
    - Deploy de cada serviço é independente
    - É possivel escalar um serviço mais que o outro caso esse serviço tenha uma demanda maior
    - **Desafios**
      - Espalhamento de informações
      - Dependência entre serviços na hora de compilá-los
      - Teste de integração mais custosos
      - Controle de versão: cuidar com a compatibilidade entre os serviços
      - Implantação: Deve-se investir em automação
      - Geração de logs: Logs centralizados
      - Monitoramento: Ter uma visão centralizada para identificar problemas
      - Depuração: Como realizar depuração remotamente com muitos serviços
      - Conectividade: Manter os serviços on-line
      - Acompanhamento de transações de uma única sessão
  
- **Ecossistema de Microsserviços**: É dividido em 4 camadas
  - **Hardware**
    - Máquinas, computadores físicos
    - Núvem: AWS, Azure, Google Cloud
    - Sistema Operaciona: geralmente Linux
    - Conteinerização: para isolamento de recursos, como Docker
  
  - **Comunicação**
    - Contém a rede: DNS, RPCs, Endpoints de API
    - Descoberta de Serviços
    - Registro de Serviços
    - Balanceamento de carga
    - Comunicação entre microsserviços
      - **Emissor da mensagem**: microsserviço que gera a mensagem (produtor, publicador)
      - **Receptor da mensagem**: microsserviço que recebe e processa a mensagem (consumidor, assinante)
      - A comunicação pode se dar de 2 maneiras: HTTP+REST ou Mensageria
      - **HTTP+REST**:
        - Acesso a endpoints REST de outros microsserviços
        - Fácil de implementar
        - Síncrono, bloqueante
        - Emissor espera o Receptor retornar
        - Mesmo que o processamento seja feito com Threads, o emissor precisa esperar a resposta do receptor
      - **Mensageria**:
        - Troca de mensagens assíncronas, não bloqueante
        - Emissor não espera o Receptor retornar
        - Dev ter uma camada intermediária: `*broker* de mensagem`
          - O emissor envia uma mensagem (dados) pela rede (HTTP ou outro protocolo) e não fica esperando a resposta
          - A mensagem é tratada e enfileirada em uma fila específica
          - O *broker* roteia a requisição para os receptores, que respondem à requisição
        - Ex: RabbitMQ
        
  - **Plataforma de Aplicação**
    - Ferramentas e serviços internos independentes dos microsserviços
    - Bibliotecas, módulos gerais
    - Sistema de build, release centralizado e automatizado
    - Testes automatizados
    - *Deploy* padronizado e centralizado
    - *Logging* e monitoramento a nível de microsserviços
  
  - **Microsserviços**
  
- Padrões de Projeto
    - Soluções genéricas para problemas recorrentes
    - Ajudam a resolver problemas com a arquitetura de microsserviço
        - Como manter o banco de dados?
        - Como uma aplicação acessa os microsserviços?
        - Como efetuar transações distribuídas?

### Arquitetura de Aplicações

- **Arquitetura Monolítica**: 
    - Simples de desenvolver
    - Simples de mplantar
    - Simples de escalar: aumentando o número de cópias da aplicação atrás de um balanceador de carga
    - Problemas
        - Código do monolito é muito grande
        - Produtividade no desenovlvimento é baixa: IDEs não rodam bem
        - Conteiner Web sobrecarregado pelo tamanho do monolito
        - Implantação contínua difícil: reimplantar a aplicação inteira toda vez
        - Dificuldade para escalar: somente em uma dimensão. Pode-se resolver a quantidade de acessos (mais cópias rodando), mas para o aumento no volume de dados é complicado. Cada cópia acessa todos os dados
        - Dificuldade para escalar o desenovlvimento: monolito dificulta que times desenvolvam de forma independente
        - Requer um compromisso de longo prazo com a tecnologia

- **Arquitetura de Microsserviços**
    - Resolve os problemas da arquitetura monolítica
    - Aplicação é um conjunto de serviços fracamente acoplados
    - Serviços são colaborativos
    - Altamente manuteníveis e testáveis: permite desenvolvimento e entregas frequentes
    - Fracamente acoplados: os times podem trabalho independentemente
    - Permite entregas independentes: permite a entrega de um serviço sem precisar coordenar com outros times
    - Serviços capazes de serem desenvolvidos por times pequenos: melhora a produtividade e evita muita comunicação em times grandes
    - Se comunicam via protocolos síncronos (como HTTP-REST) ou assíncronos (como AMQP)
    - Permite entrega e implantação contínuas de aplicações grandes e complexas
    - Manutenibilidade melhorada: cada serviço é pequeno e fácil de entender
    - Testabilidae melhorada: serviços são pequenos e fáceis de testar
    - Implantabilidade melhorada: serviços podem ser implantados independentemente
    - Melhora o desenvolvimento: cada time é responsável por um ou vários serviços independentes
    - Elimina o comprometimento de longo prazo com a tecnologia
    - Problemas:
        - Desenovlvedores devem se adaptar ao desenvolvimento distribuído
        - Requisições que abrangem vários serviços podem ser difíceis de implementar
        - Teste de integração entre serviços é mais complicado
        - Complexidade da implantação aumenta, deve-se tratar os aspectos de vários serviços sendo geridos
        - Aumento no consumo de memória: troca *n* instâncias de monolitos por *n x m* instâncias de serviços. Se cada serviço roda na sua própria JVM (para poder isolar instâncias), então tem-se *m* vezes mais JVMs. Se cada serviço roda na sua própria VM, o overhead é ainda maior

### Decomposição

- **Decomposição por Recurso de Negócios**: É uma técnica de análise e design de sistemas que se concentra na identificação e estruturação das funcionalidades de um sistema com base em recursos de negócios específicos. Essa técnica é frequentemente usada no contexto da engenharia de software e da gestão de projetos para desenvolver sistemas de informação que atendam às necessidades da organização.
- **Recurso de negócio**: Algo que gera valor, o que a empresa faz. Exemplo:
    - Serviço de logística -> O recurso de negócio seria a entrega
    - Serviço de gestão de cliente
    - Gestão de Inventário
    - Gestão de Entrega

- **Decomposição por Subdomínio**: É uma técnica de design de software que envolve dividir um sistema complexo em subdomínios menores e mais gerenciáveis. Cada subdomínio representa uma parte do sistema com responsabilidades claras e limitadas. Essa técnica é particularmente útil em arquiteturas de software orientadas a domínio e pode ser aplicada em conjunto com o design orientado a serviço. 

- **Domain-Driven Design (Software Orientado a Domínio)**:
    - Não é um framework
    - Não define camadas
    - Não define tecnologias e protocolos
    - DDD é sobre negócio
    - **Domínio**:
        - É o coração do negócio
        - Processos de negócio
        - Razão do software existir
        - É o negócio principal
    - Ajuda a organizar o domínio do problema
        - Identificar o domínio e subdomínios
        - Padronizar o vocabulário
        - Identificiar Entidades e Agregados
    - Um `domínio` pode ser separado em:
        - **Core Subdomain**: O que é a motivação do negócio, ideia central, o que mais entrega valor ao cliente, a parte mais importante
        - **Generic Subdomain**: Auxiliares ao negócio, facilitam o negócio mas não são o centro
        - **Supporting Subdomain**: Ajudam a desempenhar funções auxiliares
    - No DDD existem 2 espaços:
        - **Espaço do Problema**: Onde você analisa o negócio afim de encontrar o `Domínio e o Subdomínio`
        - **Espaço da Solução**: É onde ocorre o desenvolvimento da aplicação. O Domínio vira o `Modelo de Domínio` e o Subdomínio vira o `Contexto Delimitado` (o que gera os `Serviços`)
    - O DDD possui 3 pilares:
        - **Linguagem Ubíqua**: O mesmo vocabulário para o negócio e times de desenvolvimento. Criar um glossário
        - **Contextos Delimitados**: Responsabilidades bem definidas. Módulos.
        - **Mapas de Contextos**: Como os contextos delimitados se relacionam entre si. Encontrar o `domínio principal`, `domínios genéricos`, `domínios auxiliares`.
    - Domain Model Patterns:
        - Padroes de projeto baseados em domínio
        - **Entidades**: elementos que poussuem identificador e desconhecem bancos de dados, exemplo Pessoa, Produto, Pagamento, etc
        - **Agregagos**: conjunto de entidades vistas como uma só. Exemplo: Pedido e ItemDoPedido
        - **Objetos de Valor**: imutáveis, represetam uma coleção de atributos, criadas somente via construtores, reduz a "obessão por tipos primitivos". Ex: CPF, Money, Title
        - **Repositórios**: acesso à camada de dados para fazer presistência e consultas. Pode consultar serviços externos. Um repositório por agregação e não um por entidade
        - **Serviços de Domínio**: implementam a lógica de negócio, usam serviços de infraestrutura

        **Add img aqui**

### API Externa

- Em uma aplicação monoítica a API é a API do monolito
- Em uma aplicação de microsserviços
    - Cada serviço tem sua API
    - Pode-se ter vários clientes
- Clientes:
    - Aplicação Web
    - Aplicação Mobile
    - Javascript
    - etc
- Deve-se decidir qual tipo de API deve ser exposta aos clientes
- Permitir que os clientes acessem os serviços diretamente pode ser problemático
    - Clientes fazendo várias requisições via rede
    - Cliente precisa fazer composição de API
    - Clientes precisam atualizar o frontend em conjunto com mudanças no backend
    - Serviços podem usar protocolos de comunicação que não favorecem os clientes (mensageria, etc)

#### API Gateway

- Uma solução para os problemas acima é utilizar API Gateway
- É um componente de software que atua como ponto de entrada para um ecossistema de APIs, fornecendo uma série de funcionalidades e serviços para facilitar o gerenciamento, segurança e integração de APIs.
- Responsável pelo roteamento de requisições
    - Roteia requisições para o serviço correpondente
    - Usa um mapa de rotas
- Responsável por composição de APIs
    - Uma invocação na API pode gerar várias invocações a vários serviços
    - O cliente não precisa fazer as várias invocações, somente uma ao API Gateway
- Tradução de Protocolo
    - API Gateway expõe uam API RESTful
    - Mas pode converter requisições para gRPC, se algum serviço for implemnetado assim
    - **gRPC**:
        - É um framework de código aberto desenvolvido pelo Google que facilita a comunicação eficiente e bidirecional entre serviços distribuídos.
        - É projetado para ser mais eficiente do que outros protocolos de comunicação, como REST, especialmente em termos de desempenho e escalabilidade.
- API para clientes específicos:
    - Pode expor APIs distintas para clientes distintos
    - OSFA: one-size-fits-all
- Autenticação
- Autorização
- Limitação de recursos
- Cache
- Métricas
- Logs

#### Backends For Frontends (BFF)

- Um problema do API Gateway único: Quem é o responsável pelo gateway e sua operação?
- Gera um gargalo de desenvolvimento
- Uma solução: `Backends for Frontends`
    - Cada cliente possui sua própria API exposta
    - Cada API é mantida por um time diferente
    - O time do API Gateway é responsável por módulos comuns

    **Add img aqui**

### Gestão de Dados

- Um problema em uma arquitetura de microsserviços: como manter os dados, de forma distribuída?
- **Database per Service**: Cada serviço possui seu banco de dados
    - Os dados do serviço são acessados somente via sua API
    - As transações do serviço envolvem somente seu banco de dados
    - Seus dados não podem ser acessados por outros serviços
    - Maneiras de implementar:
        - **Private-tables-per-service**: cada serviço tem suas próprias tabelas privadas no banco de dados (Mesmo banco de dados SGBD, mesmos schemas, porém tabelas diferentes)
        - **Schema-per-service**: cada serviço tem seu próprio esquema privado no banco de dados (Mesmo banco de dados SGBD, porém schemas e consequentemente tabelas diferentes)
        - **Database-server-per-service**: cada serviço tem seu próprio banco de dados
    - Problemas:
        - Implementar transações que abrangem vários serviços não é simples
        - Evitam-se `transações distribuídas` por causa do `CAP Teorema`
            - **Consistency**: Todas as leituras retornam os dados mais recentes, ou falha
            - **Availability** - Todas as leituras retornam dados, mas nem sempre os mais recentes
            - **Partition Tolerance**: O sistema continua a funcionar mesmo em uma falha de rede
        - Em uma falha de rede, um sistema de banco de dados distribuído só consegue fornecer ou Consistência ou Disponibilidade, nunca os dois
        - Alta consistência vem ao custo de baixa disponibilidade
        - Alta disponibilidade vem ao custo de baixa consistência
        - Implementar consultas que agregam dados de vários serviços não é simples
        - Há uma complexidade maior envolvida na gestão de vários bancos de dados
    - Como resolver os problemas de `gestão de BD`: `Shared Database`
    - Como resolver os problemas de `transaçoes distirbuídas`: `Padrão SAGA` (para transações que abrangem vários serviços)
    - Como resolver os problemas de `consultas distribuídas`:
        - **Padrão API Composition**: O gateway recupera as informações separadas e faz a junção (join)
        - **Padrão CQRS**: Bancos de dados separados para consulta e transações

- **Shared Database**: Cada serviço acessa um banco de dados compartilhado
    - Qualquer serviço acessa qualquer dado mantido por qualquer serviço
    - Usa-se transações `ACID`
        - **A - Atomicidade**: as transações são unidades completas, ou tudo é executado ou tudo falha
        - **C - Consistência**: a transação cria um novo estado em caso de sucesso, em caso de falha mantém o estado anterior
        - **I -Isolamento**: uma transação não terminada nao sofre qualquer interferência de qualquer outra transação
        - **D - Durabilidade**: dados validados são registrados e estão disponíveis em seu estado correto mesmo em caso de falha do sistema ou reinício
    -  Benefícios
        - Fácil de implementar
        - Fácil de gerir somente um banco de dados
    - Problemas
        - Acoplamento em tempo de desenvolvimento, vários desenvolvedores trabalhando nos mesmos dados
        - Acoplamento em tempo de execução, transações de longa duração podem bloquear uma tabela necessária para outros serviços
        - Um banco de dados único pode não satisfazer todos os requisitos de armazenamento e acesso de todos os serviços
    - Como resolver os problemas: `Database per service`

### Transações Distribuídas

- Para uma arquitetura de microsserviços que estão implementados com o padrão Banco de Dados por Serviço
- Como implementar transaçoes que abrangem vários serviços? (Assumindo que não se pode usar `2PC[2-phase commit]`)
- Exemplo: Compra de um produto que atualiza a tabela de produtos do Serviço de Produtos e a tabela de compras do Serviço de Compras?

#### SAGA

- Saga é uma sequência de transações locais coordenadas por mensagens

**Add img aqui**

- Em caso de falha, usa uma mensagem de compensação para corrigir as alterações

**Add img aqui**

- Como coordenar a sequência de transações locais?
    - **Coreografia**: cada serviço publica um evento que dispara a próxima transação
    - **Orquestração**: um objeto orquestrador indica aos participantes qual transação executar

- **Saga baseado em Coreografia**
    - Serviços participantes se subscrevem entre si para consumir eventos
    - Serviço XYZ termina uma transação local
        - Emite um evento para todos os assinantes
    - Os serviços que subscrevem os eventos do Serviço XYZ iniciam suas transações locais
    - Ao terminarem, emitem eventos
    - Implementa-se com `mensageria assíncrona`
    - Exemplo: Compra de um produto
        - 1. Serviço de Pedido cria o pedido como pendente
        - 2. Serviço de cliente deve verificar os detalhes do cliente
        - 3. Serviço de Produto deve reservar o produto
        - 4. Serviço de Compra deve criar uma pendência de pagamento
        - 5. Serviço de Compra recebe confirmação do cliente e da reserva do produto, e efetiva o pagamento do cliente
        - 6. Serviço de Produto deve efetivar a retirada do produto do estoque após o pagamento
        - 7. Serviço de Pedido atualiza o pedido como efetivado depois do pagamento ser efetivado
      - Nesse exemplo todos os serviços possuem banco de dados separado (É disso que se trata SAGA)
      - Os pedidos ficam estocados em uma fila e cada serviço subscreve no evento

    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**

    - **Benefícios**: 
      - **Simplicidade**: Serviços publicam eventos sempre que criam, atualizam ou removem objetos de negócio
      - **Baixo acoplamento**: Participantes emitem eventos, mas não precisam se conhecer
  
    - **Problemas**:
      - **Mais difícil de entender**: o processamento da SAGA está disperso, é difícil entender como uma SAGA é efetivada
      - **Dependências cíclicas entre serviços**: não necessariamente um problema
      - **Risco de acoplamento**: como um serviço subscreve em todos que ele necessita, pode ser necessário que seja atualizado conforme o ciclo de vida de outro serviço
  
    - Funciona bem para SAGASs simples
    - Para SAGAs complexas, melhor usar `Orquestração`

- **Saga com Orquestração**
  - Existe um objeto que define o que cada participante faz
  - Se comunica com os participantes de forma assíncrona com um canal de retorno (resposta)
     - Orquestrador envia um comando a um participante
     - Quando o participante termina, envia uma resposta ao orquestrador
     - Orquestrador recebe a resposta e determina qual o próximo passo
  - Exemplo: Compra de um produto
    - Serviço de pedido cria o orquestrador da SAGA
    - 1. Orquestrador envia VerifyConsumer para o Serviço de Cliente
    - 2. Serviço de Cliente responde com ConsumerVerified
    - 3. Orquestrador evna ReserveProduct para o Serviço de Produto
    - 4. Serviço de Produto responde com ProductReserved
    - 5. Orquestrador envia AuthorizePayment para o Serviço de Compra
    - 6. Serviço de Compra responde com PaymentAuthorized
    - 7. Orquestrador manda ProductApproved para o Serviço de Produto
    - 8. Orquestrador manda ApproveOrder para o Serviço de Pedido
  - No passo 8 o orquestrador considera o Serviço de pedido como um participante da SAGA

    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**
    **Add img aqui**

    - **Benefícios**
      - **Não introduz dependências cíclicas**: somente o orquestrador invoca os participantes
      - **Menor acoplamento**: cada serviço implementa a API a ser chamada pelo orquestrador, não precisa saber sobre o resto da SAGA
      - **Simplifica a lógica de negócio**: o serviço de pedido somente trata seus estados (pendente, aprovado, rejeitado), toda a lógica da SAGA está implementada no orquestrador. Serviços ficam mais simples
    - **Problema**
      - Risco de muita centralização da lógica de negócio no orquestrador. Deve-se implementar orquestradores que são responsáveis somente pelo sequenciamento de invocações, sem lógica de negócio
    - **Recomendação**: Usar orquestração para tudo menos para SAGAs simples

### Consultas Distribuídas

- Problema
  - Como retornar consultas contendo dados que pertencem a mais de um serviço em uma arquitetura de microsserviços com Database per Service?
- Duas soluções
  - Padrão API Composition
  - Padrão CQRS 

- **Padrão API Composition**
  - A abordagem mais simples
  - Deve ser usada sempre que possível
  - Os clientes dos serviços que possuem os dados são responsáveis por combinar os resultados
  - Possui 2 agentes:
    - **API Composer**: implementa a consulta, invocando os serviços
    - **Provedor de Dados**: serviço que detém o dado sendo consultado
  - Qual serviço deve ser o `API Composer`?
    - Composição pode ser feita na `aplicação cliente`
      - Isso gera um problema de desempenho, tráfego de informações
    - Composição pode ser feita no `API Gateway`
      - Determinadas requisições, ao invés de serem roteadas para serviços, fazem várias chamadas e retornam as consultas
      - Pode deixar a API Gateway ainda mais complexa
    - Pode-se implementar um `serviço específico` para ser o API Composer
      - Boa opção para consultas internas
      - Boa opção quando a lógica de agregação é muito complexa para ser parte do API Gateway
  - Deve ser implementado de forma reativa
  - Invocar as partes em paralelo (quando possível)
  - Combiná-las quando todas estiverem prontas
  - **Benefícios**
    - Simples de implementar
    - Intuitivo
  - **Problemas**
    - **Aumenta o overhead**: muitas consultas a vários bancos de dados aumentam o custo computacional da operação, se as consultas forem grandes, pode ser exigida a composição em memória
    - **Risco de disponibilidade reduzida**: a disponibilidade de uma operação diminui com o aumento de serviços envolvidos
    - **Falta de consistência de dados**: várias consultas e vários bancos de dados, há o risco de retornar dados incosistentes
  - Solução: Usar o `padrão SQRS`

- **Padrão SQRS**
  - Não há como executar consultas que agregam dados de todos os serviços (consultas distribuídas)
  - Não podemos usar API Composition por causa de seus problemas
  - Como executar consultas que buscam dados de vários serviços: `Padrão SQRS (Command Query Responsability Segregation)`
  - Definir um banco de dados de visão
    - Uma réplica somente de leitura
    - Deve-se usar o padrão `Eventos de Domínio` para atualizar a base de Leitura
      - Organiza a lógica de negócio do serviço como um Agregado (DDD)
      - Esse agregado emite eventos quando objetos são criados ou atualizados
      - O serviço publica esses eventos, que podem ser consumidos
  - Separa comandos de consultas
    - **Módulo de Comandos**: atualizações (POST, PUT, DELETE)
    - **Módulo de consultas**: leituras (GET)
  - Módulo de Consultas
    - Se mantém atualizado
    - Subscreve eventos do módulo de comandos

    **Add img aqui**

  - **Benefícios**
    - Implementação `eficiente de consultas` na arquitetura de microsserviços
    - Torna possível a `execução de consultas` em um ambiente `baseado em eventos`
    - Melhora a separação de interesses
  - **Problemas**
    - Arquitetura mais complexa
    - Deve-se tratar o atraso de replicação

## HTML/CSS

### Material Utilizado

- https://questoes.grancursosonline.com.br/aluno/filtro/concursos?nivel=1&banca=102&desatualizada=0&anulada=0&query=html

### Básico

- `alt`: Texto a ser exibido no local da imagem, caso essa não seja exibida por alguma razão
- `<head>`:
    - Contém meta informações sober a página
- `<span>`: É um container inline que é usado para aplicar marcações de estilo a de um texto ou documento, e pode facilmente ser manipulado por código JavaScript.
- `<link>`:
```HTML
<link rel="stylesheet" href="mystyle.css">
```

- Tornando uma pagina web responsiva:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- Removendo todo conteúdo de um elemento:
```javascript
$(document).ready(function(){
    $("button").click(function(){
        $("div").empty();
    });
});
```

- Alterando a cor de uma classe:
```javascript
$(".title").css("color", "red").
```

- `$("elemento")` = tag de um elemento

- Para não exibir um compoente após renderizada a página:
```html
<p:textEditor rendered="false" />
```

- tags e classes:
```css
p.centro {

text-align: center;

color: blue;

} 
```

p = tag
.centro = classe

### Block-level

### Inline

### Cross-Site Scripting

### CSS

#### Básico

