# ARQUITETURA DE SISTEMAS DA INFORMAÇÃO

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

## ITIL4 (+Material) (Fazer questões pra ver se precisa de mais material)

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
- *time-boxed* com no máximo oito horas para uma Sprint de um mês de duração
- O que pode ser entregue como resultado do incremento da próxima Sprint?
- Como o trabalho necessário para entregar o incremento será realizado?

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

### Governança Corporativa de Tecnologia e Informação (EGIT)

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
    - Análise de valor limite
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
