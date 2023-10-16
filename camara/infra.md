# ARQUITETURA DE INFRAESTRUTURA DE TECNOLOGIA DA INFORMAÇÃO E COMUNICAÇÃO

## Material

- https://learn.microsoft.com/pt-br/training/paths/deploy-manage-identity-infrastructure/

## Operação e Administração de Sistemas Operacionais (+Material)

**Funções de um SO**
- Afastar do usuário a complexidade do hardware através de uma interface (Modo usuário)
- Gerenciar recursos de hardware (Modo núcleo)

Os SOs podem realizar virtualização de outros SOs, alguns tipos são:
- Hyervisor tipo 1 (baremetal): Virtual Machine Monitor
    - Responsável por criar os drives próprios para o SO emulado
    - Rodam mais rápido
- Hypervisor tipo 2: Virtualização de Desktop

**Funções de um servidor de rede**
- O papel principal do SO servidor é fornecer serviços para os SOs cliente:
    - Endereçamento lógico
    - resolução de nomes
    - armazenamnto e acesso de arquivos
    - gestão de impressão, 
    - gestão de aplicações
    - gestão de diretório de recursos
    - acesso remoto
- Um servidor pode prover o mesmo recurso para vários OSs, sem que isso consuma mais memória que abrir o recurso no próprio OS. Por exemplo, se você sobe 5 sistemas windows em máquinas diferentes utilizando um servidor, esse servidor só está consumindo de memória um único SO.

## Windows Server (Fazer questões +Material)

O Windows Server é uma plataforma para compilar uma infraestrutura de aplicativos, redes e serviços Web conectados, do grupo de trabalho ao data center. Ele faz a ponte entre os ambientes locais e o Azure, adicionando mais camadas de segurança enquanto ajuda você a modernizar seus aplicativos e sua infraestrutura.

### AD DS (Active Directory Domain Services)

- O AD DS e seus serviços relacionados formam a base para redes corporativas que executam sistemas operacionais Windows. 
- O banco de dados do AD DS é o repositório central de todos os objetos de domínio, como contas de usuário, contas de computador e grupos. 
- O AD DS fornece um diretório hierárquico e pesquisável, bem como um método para aplicar definições de configuração e segurança para objetos em uma empresa.
- O AD DS inclui componentes lógicos e físicos.
- Você pode usar opções do AD DS para executar ações como:
    - Instalação, configuração e atualização de aplicativos.
    - Gerenciamento da infraestrutura de segurança.
    - Habilitação do serviço de acesso remoto e do DirectAccess.
    - Emissão e gerenciamento de certificados digitais.

**Componentes Lógicos**

Os componentes lógicos do AD DS são estruturas que você usa para implementar um design do AD DS apropriado em uma organização. Os componentes lógicos são:

- **Partição:** Uma partição, ou contexto de nomenclatura, é uma parte do banco de dados do AD DS. O Active Directory armazena cópias de partições em vários controladores de domínio e os atualiza por meio da replicação de diretório.
- **Esquema:** Um esquema é o conjunto de definições dos tipos de objeto e atributos que você usa para definir os objetos criados no AD DS.
- **Domínio:** Um domínio é um contêiner administrativo lógico para objetos como usuários e computadores. Um domínio é mapeado para uma partição específica, e você pode organizar o domínio com relações pai-filho com outros domínios. No domínio ficam as contas de usuário, contas de computador e grupos
- **Árvore de domínio:** Uma árvore de domínio é uma coleção hierárquica de domínios que compartilham um domínio raiz comum e um namespace DNS (Sistema de Nomes de Domínio) contíguo.
- **Floresta:** Uma floresta é uma coleção de um ou mais domínios que têm uma raiz do AD DS, um esquema comum e um catálogo global comum.
    - Por padrão, nenhum usuário de fora da floresta pode acessar nenhum recursos dentro da floresta. Além disso, todos os domínios em uma floresta confiam automaticamente nos outros domínios dela.
    - Uma floresta do AD DS é o limite de replicação para a configuração, as partições de esquema no banco de dados do AD DS e o catálogo global.
- **UO:** Uma UO é um objeto de contêiner para usuários, grupos e computadores que fornece uma estrutura para delegar direitos administrativos e administração ao vincular GPOs (Objetos de Política de Grupo). Há dois motivos para se criar UOs:
    - Para consolidar objetos a fim de facilitar o gerenciamento deles, aplicando GPOs ao coletivo.
    - Para delegar o controle administrativo de objetos dentro da UO.

- **Contêiner:** Um contêiner é um objeto que fornece uma estrutura organizacional para uso no AD DS. Você pode usar os contêineres padrão ou criar contêineres personalizados. Não é possível vincular GPOs a contêineres.

**Componentes Físicos**

Os componentes físicos no AD DS são aqueles que são tangíveis ou que descrevam componentes tangíveis no mundo real. Estes são:

- **Controlador de domínio:** Um controlador de domínio contém uma cópia do banco de dados do AD DS. Para a maioria das operações, cada controlador de domínio pode processar alterações e replicá-las em todos os outros controladores no domínio.
- **Armazenamento de dados:** 
Há uma cópia do armazenamento de dados em cada controlador de domínio. O banco de dados do AD DS usa a tecnologia de banco de dados do Microsoft Jet e armazena as informações de diretório no arquivo Ntds.dit e nos arquivos de log associados.
- **Servidor de catálogo global:** Um servidor de catálogo global é um controlador de domínio que hospeda o catálogo global, que é uma cópia parcial e somente leitura de todos os objetos em uma floresta de vários domínios. Um catálogo global acelera as pesquisas de objetos que podem ser armazenados em controladores de domínio em um domínio diferente na floresta.
- **RODC (Controlador de domínio somente leitura):** Um RODC é uma instalação especial, somente leitura, do AD DS. Os RODCs são comuns em filiais em que a segurança física não é ideal, o suporte de ti é menos avançado do que nos centros corporativos principais
- **Site:** Um site é um contêiner para objetos do AD DS, como computadores e serviços específicos de um local físico.
- **Sub-rede:** Uma sub-rede é uma parte dos endereços IP de rede de uma organização atribuídos a computadores em um site. Um site pode ter mais de uma sub-rede.

Além dos componentes e objetos de alto nível, o AD DS contém outros objetos, como usuários, grupos e computadores.

- **Usuários**: No Windows Server, uma conta de usuário é um objeto que contém todas as informações que definem um usuário. Esse tipo de conta inclui:
    - O nome de usuário.
    - Uma senha de usuário.
    - Associações de grupo.

- **Serviços:** Muitos aplicativos contêm serviços que você instala no servidor que hospeda o programa. Esses serviços normalmente são executados na inicialização do servidor ou são disparados por outros eventos. Os serviços costumam ser executados em segundo plano e não exigem nenhuma interação do usuário. Para que um serviço seja iniciado e autenticado, você usa uma conta de serviço, que pode ser uma conta local do computador, como as contas internas de Serviço Local, Serviço de Rede ou Sistema Local.

- **Contas baseadas em domínio:** Para ajudar a centralizar a administração e atender aos requisitos do programa, muitas organizações optam por usar uma conta baseada em domínio para executar serviços do programa. Embora isso forneça algum benefício em comparação ao uso de uma conta local, há vários desafios associados, como os seguintes:
    - Pode ser necessário um esforço administrativo extra para gerenciar a senha da conta de serviço com segurança.
    - Pode ser difícil determinar onde uma conta baseada em domínio está sendo usada como uma conta de serviço.
    - Pode ser necessário um esforço administrativo extra para gerenciar o SPN (nome da entidade de serviço).

- **Contas de Serviço Gerenciado**: São contas para o suporte de objetos do AD DS, elas facilitam o gerenciamento da conta de serviço fazendo o gerenciamento simplificado de senhas e SPN.

- **Contas de Serviço Gerenciado de Grupo:** As contas de serviço gerenciado de grupo permitem estender os recursos de contas de serviço gerenciado padrão para mais de um servidor em seu domínio. Em cenários de farm de servidores com clusters de NLB (Balanceamento de Carga de Rede) ou servidores IIS, muitas vezes é necessário executar serviços do sistema ou do programa na mesma conta de serviço. As contas de serviço gerenciado padrão não podem fornecer funcionalidade de conta de serviço gerenciada para serviços em execução em mais de um servidor, por isso se usam as contas de serviço gerenciado de grupo.

**Objetos de Grupo** 

Embora possa ser prático atribuir permissões e direitos a contas de usuário individuais em redes pequenas, isso se torna impraticável e ineficiente em grandes redes corporativas.

Por exemplo, se vários usuários precisarem do mesmo nível de acesso a uma pasta, será mais eficiente criar um grupo que contenha as contas de usuário necessárias e, em seguida, atribuir as permissões necessárias ao grupo.

Ao criar um grupo, você escolhe o tipo e o escopo dele. O tipo determina os recursos do grupo. 

- **Tipos de Grupo:** No Windows Server há dois tipos de grupo:

- Segurança
- Distribuição

- **Escopos de Grupo:** O escopo de um grupo determina a gama de habilidades ou permissões de um grupo e a associação de grupo. Há quatro escopos de grupo:

1. Local: Usado em um único computador para atribuir habilidades e permissões locais.

2. Local de Domínio: Empregado em controladores de domínio para gerenciar acesso e direitos no domínio local.

3. Global: Utilizado para agrupar usuários com características semelhantes e atribuir habilidades em toda a floresta.

4. Universal: Principalmente em redes multidomínio, permite atribuir habilidades em toda a floresta e aceitar membros de qualquer lugar da floresta do AD DS.

**Objetos de Computador**

Objetos de computador são entidades de segurança que representam computadores em um domínio no Windows. Eles têm contas com nomes e senhas que o sistema altera automaticamente periodicamente. Esses objetos autenticam-se no domínio, podem pertencer a grupos para acessar recursos e são configurados através da Política de Grupo. A vida útil de uma conta de computador começa quando o objeto é criado e ingressado no domínio, e tarefas administrativas incluem configuração de propriedades, movimentação entre Unidades Organizacionais (UOs), gerenciamento e eventual renomeação, redefinição, desabilitação, habilitação ou exclusão do objeto de computador.

**Contêiner Computadores**

O contêiner Computadores é um local padrão em um domínio do AD DS onde as contas de computador são armazenadas quando ingressam no domínio. Ele não é uma Unidade Organizacional (UO), mas sim um tipo de contêiner. Embora pareça semelhante a uma UO, existem diferenças importantes. Você não pode criar UOs dentro do contêiner Computadores nem vincular Objetos de Política de Grupo a ele. Portanto, é aconselhável criar UOs personalizadas para hospedar objetos de computador em vez de usar o contêiner Computadores.

## SQL (Structured Query Language) (+Material)

- É uma linguagem `declarativa`
    - Não é uma linguagem `estruturada` nem `procedural`
- Permite:
    - Definição da estrutura de dados
    - Modificações e consultas aos dados
    - Especificação de Restrições de Segurança
    - Criação de diferentes planos de execução
- SQL define 3 classes de `tipos de dados`:
    - Pré-definidos:
        - CHARACTER 
        - CHARACTER VARYING
        - CHARACTER LARGE OBJECT
        - BINARY LARGE OBJECT
        - NUMERIC
        - DECIMAL
        - SMALLINT
        - INTEGER
        - BIGINT
        - FLOAT
        - REAL
        - DOUBLE PRECISION
        - BOOLEAN
        - DATE
        - TIME
        - TIMESTAMP
        - INTERVAL
    - Construídos:
        - ARRAY
        - MULTISET
        - REF
        - ROW
    - Definidos pelo usuário (Domínio)

### **DDL**

**Create Table e Uso de *not null***

```SQL
CREATE TABLE Cliente(
    cod_cliente numeric(5) not null,
    nome_cliente varchar(30) not null,
    tel_cliente varchar(20)
)
```

**Create Domain**

```SQL
CREATE DOMAIN tipo_nome
    varchar(30)

CREATE TABLE Cliente(
    cod_cliente numeric(5) not null,
    nome_cliente tipo_nome,
    tel_cliente varchar(20)
```

**Valores *default***

```SQL
CREATE TABLE Cliente(
    cod_cliente numeric(5) not null,
    nome_cliente varchar(30) not null,
    tel_cliente varchar(20),
    saldo numeric(7,2) not null default 0
) 
```
No `numeric(7,2)` o 7 representa a quantidade de casas máximas antes da vírgula e o 2 representa a qnt de casas depois da vírgula

**Primary key - Unique**

- Primary key é sempre *not null*
- FK
- Possui id único
- Pode ter qualquer núm de atributos
- O atributo pode ter qualquer tipo

```SQL
CREATE TABLE Cliente(
    cod_cliente numeric(5) primary key,
    nome_cliente varchar(30) not null,
    tel_cliente varchar(20) unique,
    saldo numeric(7,2) not null default 0
)
```

- Para *unique* a var não vai poder se repetir

**Check**

- É uma clausula de validação

```SQL
CREATE TABLE Cliente(
    cod_cliente numeric(5),
    nome_cliente varchar(30) not null,
    tel_cliente varchar(20),
    saldo_numeric(7,2) not null default 0,
    primary key(cod_cliente),
    unique(tel_cliente)
    check(saldo > 0)
)
```

Nesse exemplo acima, como o saldo precisa ser maior que zero, e o *default* da varchar é 0 então vai dar problema. Ficar atento a isso na prova

**Foreign Key**

```SQL
CREATE TABLE Cidade(
    cod_cidade numeric(2) primary key,
    nome_cidade varchar(30) not null
)

CREATE TABLE Cliente(
    cod_cliente numeric(2) primary key,
    nome_cliente varchar(30) not null,
    saldo numeric(7,2) not null default 0.0,
    cod_cidade numeric(2) references Cidade
)
```

- `references` é a referência à chave primária da Cidade

**Cascade**

- Atualiza todas as chaves estrangeiras da tabela

```SQL
CREATE TABLE Cliente(
    cod_cliente numeric(2) primary key,
    nome_cliente varchar(30) not null,
    saldo numeric(7,2) not null default 0.0
    cod_cidade numeric(2),
        constraint fk_cidade
        foreign key(cod_cidade)
        references Cidade
        on delete cascade
        on update cascade
)
```

**Alter Table**

```SQL
ALTER TABLE <table name><alter table action>
<alter table action> ::=
    <add column definition>
    |<alter column definition>
    |<drop column definition>
    |<add table constraint definition>
    |<drop table constraint definition>
```

```SQL
ALTER TABLE Cliente
    ADD Estado char(2); #Adicionando atributo Estado na tabela Cliente

ALTER TABLE Cliente
    ADD COLUMN Estado char(2); #Adicionando atributo Estado na tabela Cliente
```

**Alter Column**

```SQL
<alter column action>::=
    <set cloumn defaulkt clause>
    |<drop column default clause>
```

```SQL
ALTER TABLE Cliente
    ALTER Estado SET DEFAULT('RJ'); # Configurando como padrão o dado 'RJ' na coluna Estado

ALTER TABLE Cliente
    ALTER Estado DROP DEFAULT; # Apagando a configuração padrão da coluna Estado

ALTER TABLE Cliente
    DROP Estado; # Apagando a coluna Estado

ALTER TABLE Cliente
    DROP COLUMN Estado; # Apagando a coluna Estado
```

**Drop Table**

```SQL
DROP TABLE <table_name>
    [CASCADE|RESTRICT]
```

```SQL
DROP TABLE Cidade CASCADE #Apaga a tabela cidade e todas as chamadas a essa tabela

DROP TABLE Cliente RESTRICT
```

### DML

- **Inclusão de Dados**

    ```SQL
    INSERT INTO <target table> [(<column_list>)]
    VALUES(<value_list>)|<query_expression>
    ```

    ```SQL
    INSERT INTO Cliente
    VALUES (20, 'Gabriel Pacheco') # Add na ordem das colunas na tabela

    INSERT INTO Cliente (nome, cod_cliente)
    VALUES ('Gabriel Pacheco', 50) # Add na nas colunas especificadas (nome, cod_cliente)
    ```

- **Udate** (+Material)

- **Exclusão de dados**

    ```SQL
    DELETE FROM <target table>
        [WHERE <search condition>]
    ```

    ```SQL
    DELETE FROM Clientes # Apagar todos os dados da tabela Clientes

    DELETE FROM Clientes WHERE nome_cliente like 'G%' # Apagar todos os dados onde o atributo `nome_cliente` comece com a letra `G` e pode ter qualquer quantidade de dados depois dela (definido pelo '%')
    ```

- **Case** (+Material)

### DQL

- **Select**

```SQL
SELECT <attribute list>
    FROM <table list>
    [WHERE <condition>]
    [GROUP BY <grouping attribute(s)>]
    [HAVING <group condition>]
    [ORDER BY <attribute list>]
```

- **All e Distinct**

```SQL
SELECT cod_empregado, salario_empregado
    FROM Empregado;

SELECT all cod_empregado, salario_empregado
    FROM Empregado; #Seleciona todos os dados

SELECT distinct salario_empregado 
    FROM Empregado; # Pega só a primeira ocorrencia de um salário específico
```

### DCL (+Material)

- **Grant**: Use a instrução GRANT para conceder privilégios a um usuário ou função específico ou a todos os usuários para executar ações em objetos de banco de dados
- Os seguintes privilégios podem ser condedidos:
    - Excluir dados de uma tabela específica
    - Inserir dados em uma tabela específica
    - Criar uma referência de chave estrangeira para a tabela nomeada ou para um subconjunto de colunas de uma tabela
    - Selecionar dados de uma tabela, visualização ou um subconjunto de colunas em uma tabela
    - Criar um gatilho (trigger) em uma tabela
    - Atualizar dados em uma tabela ou em um subconjunto de colunas em uma tabela
    - Executar uma função ou procedimento especificado
- Você pode conceder privilégios em um objeto se você for o proprietário do objeto ou o proprietário do banco de dados

- **Revoke**

### DTL (+Material)

- **Begin**
- **Commit**
- **Rollback**



## Arquitetura TCP/IP (+Material)

Toda comunicação, face-a-face ou por uma rede, é regida por `regras` pré-determinadas chamadas de `protocolos`

- O que é Protocolo: Um protocolo é um conjutno de regras e procedimentos a respeitar par emitir e receber dados numa rede
- Protocolos de Rede: Conjutos de protocolo de rede descrevem processos tais como:
    - O formato ou estrurura da mensagem
    - O método pelo qual os dispositivos de rede compartilham informações sobre rotas com outras redes
    - Como e quando mensagens de erro e de sistema são passadas entre dispositivos
    - A configuração e término das sessões de tranferência de dados
- Protocolos descrevem a `regra` de comunicação, mas não como elas devem ser executads. Cada fabricante segue o `padrão` de comunicação


### Modelos de Referência e de Protocolo

- Existem dois tipos básicos de modelos de rede: `modelos de protocolo` e `modelos de referência`

- Modelo de protocolo
    - Fornece um moidelo que corresponde de perto à estrutura de um conjunto específico de protocolos
    - O modelo TCP/IP é um modelo de protocolo porque descreve as funções que ocorrem em cada camada de protocolos dentro do conjunto TCP/IP

- Modelo de Referência:
    - Fornece uma referência comum para uma consistente manutenção dentro de todos os tipos de protroclos de rede serviços.
    - O modelo de referência OSI é o modelo de referência de rede mais amplamente conhecido

- Modelo OSI
    - Conjunto de protocolos usado para desenvolver uma rede internacional que não seja dependente de sistemas proprietários
    - Possui 7 camadas:
        - **Aplicação**: A camada de Aplicação fornece os meios para conectividade ponto-a-ponto entre indivíduos na rede humana usando redes de dados.

        - **Apresentação**: A camada de Apresentação fornece uma representação comum de dados transferidos entre serviços da camdada de Aplicação
            - Trata as conversões entre os dados que são recebidos. Computadores podem ter conversões diferentes, por isso eh necessário um gerenciador para isso

        - **Sessão**: A camada de Sessão fornece serviços à camdada de Apresentação para organizar seu diálogo e para fornecer a troca de dados.
        
        - **Transporte**: A camada de transporte define os serviços para segmentar, transferir e reunir os dados para comunicações individuais entre dispositivos finais.
        
        - **Rede**: A camada de Rede fornece serviços para trocar pedaços individuais de dados através da rede entre dispositivos finais identificados.
        
        - **Enlace de Dados**: Os protocolos da camada de Enlance de Dados descrevem métodos para trocar quadros de dados entre dispositivos através de um meio físico comum
            - Controla o fluxo de transmissão dos dados
            - Responsável pelo controle das Pontes
            - Responsável pelo controle dos switches
            - A única excessão eh o SWL3 (switcher layer 3) que funciona mais como um roteador, então ele está na camada de Rede
        
        - **Física**: Os protocolos da camada Física descrevem os meios mecânicos, elétricos, funcionais e procedimentais para ativar, manter e desativar conexões físicas para transmissão de bits para e/ou partir de um dispositivo de rede.

- Modelo TCP/IP: Possui 4 camadas
    - **Aplicação**: Representa os dados ao usuário com codificação e controle de diálogo
        - Chega de forma binária e converte ela em uma interface para o usuário
        - Corresponde a 3 camadas do modelo OSI: `Aplicação`, `Apresentação` e `Sessão`
        - O DNS (Sistema de Resolução de domínios), o HTTP (Protocolo de Transferência de Hipertexto), o SMTP (Protocolo de Transferência de Correio Simples) e o POP (Protocolo dos Correios) fazem parte dessa camada

    - **Tranporte (TCP)**: Oferece suporte à comunicação entre diversos dipositivos e redes distintas
        - Corresponde a camada de `Transporte` do modelo OSI

    - **Internet (IP)**: Determina o melhor caminho através da rede
        - Correnponde a camada de `Rede` do modelo OSI
        - O roteador esta na camada de rede do modelo OSI

    - **Acesso à Rede (Ethernet)**: Controla os dispositivos de hardware e meio físico que compõem a rede
        - É a camada de `Enlace de Dados` e a camada `Física` do modelo OSI

- O processo de comunicação completo inclui os seguintes passos:
    - 1. `Criação` de dados

    - 2. `Segmentação` e encapsulamento de dados
        - Acelera a velocidade da transferência, porém aumenta a complexidade

    - 3. `Geração` dos dados no meio físico na camada de acesso à rede

    - 4. `Transporte` dos dados através da rede
    
    - 5. `Recepção` dos dados na camada de acesso à rede
    
    - 6. `Desencapsulamento` e remontagem dos dados
    
    - 7. `Tranferência` desses dados à aplicação de destino

### Processo de envio e recebimento

- Ao se enviar mensagens em uma rede, a pilha de protocolo em um host opera de cima para baixo.
- Esse processo é revertido no host de destino
- Os dados passam pela camada de Dados

### Obtendo os Dados para o Dispositivo Final

- A forma que um pedaço do dado assume em qualquer camada é chamada PDU (Unidade de Dados de Protocolo)

**Add img aqui**

### Obtendo os dados através da rede

**Add img aqui**

### Camada de Aplicação

- Fornece a troca de informações de usuários
- Esses protocolos especificam as informações de formato e controle necessários para muitas funções comuns de comunicação na Internet
- `Aplicações`: Fornecem a interface humana
- `Serviços`: Seguem protocolos para preparar os dados para a rede

- **Modelo Cliente/Servidor**
    - Os processos de cliente e servidor são considerados como estando na camada de Aplicação

    **Add img aqui**

- **Servidor**
    - Qualquer dispositivo qu responda a solicitações de aplicações de clientes funciona como um servidor

    **Add img aqui**

- **Serviços e protocolo DNS**
    - O protocolo DNS define um serviço automatizado que alia os nomes de recursos com o endereço de rede numérico necessário.
    - Ele converte o nome em endereço de IP
    - Ex: Servidor DNS = www.cisco.com
          Endereço = 198.133.219.25

### Topologia (Buscar mais material!!)

- Dica: Se vc não souber, chuta topologia estrela

### UDP (Buscar mais material!!!)

## FTP (Buscar mais material!!!)

### QoS (Qualidade do Serviço) Buscar mais material!!!

### Moduladores e multiplexadores (Buscar mais material!!!)


## Oracle Database

### Material de Estudo

- https://www.youtube.com/watch?v=PB9Vcpe8q2Y

### Introdução

- Toda organização tem informações que devem ser armazenadas e gerenciadas para atender aos seus requisitos
- Uma organização deve `coletar e manter registros` (SGBD)
- As informações devem estar `disponíveis` sempre que necessário
- Um banco de dados é uma `coleção organizada de informações`
- O objetivo de um banco de dados é coletar, armazenar e recuperar informações relacionadas para uso por `aplicativos de banco de dados` (clientes).
- Um `Sistema de Gerenciamento de Banco de Dados (SGBD)` é um software que `controla` o armazenamento, a organização e a recuperação de dados.
- Um `aplicativo de banco` de dados é um programa que interage com um banco de dados para `acessar e manipular dados`
- Um `banco de dados hierárquico` organiza dados em uma `estrutura em árvore`.
- Um `banco de dados de rede` é semelhante a um banco de dados hierárquico, exceto que os registros têm um relacionamento `muitos-para-muitos` em vez de um-para-muitos
- Um `banco de dados relacional` é um banco de dados em conformidade com o modelo relacional (entidades e relacionamentos)
- O `modelo relacional` possui os seguintes aspectos principais:
    - **Estruturas**: objetos bem definidos armazenam ou acessam os dados de um banco de dados
    - **Operações**: ações `claramente definidas` (declarativo) permitem que os aplicativos manipulem os dados e as estruturas de um banco de dados.
    - **Regras de integridade**: governam as operações nos dados e nas estruturas de um banco de dados.
        - Define as restrições de cada entidade
- Um `banco de dados relacional` armazena dados em `conjuntos de relações simples`:
    - Uma `relação` é um `conjunto de tuplas`
    - Uma `tupla` é um `conjunto não ordenado de valores de atributos`.
- Uma `tabela` é uma representação bidimensional de uma relação na forma de `linhas` (tuplas) e `colunas` (atributos)
- Cada `linha` possui o mesmo `conjunto de colunas`
- Um `banco de dados relacional` é um banco de dados que `armazena dados em relações` (tabelas)
- Um `SGBDR`:
    - Move dados para um banco de dados
    - Armazena os dados de maneira `persistente`
    - Recupera os dados para que os aplicativos possam manipulá-los através de `consultas`
- Um `SGBDR` distingue entre os seguintes tipos de operações:
    - **Operações Lógicas**: um aplicativo especifica qual conteúdo é necessário (de forma `declarativa`)
    - **Operações Físicas**: o SGBDR determina como as coisas devem ser feitas e realiza a operação, `armazena e recupera` dados para que as operações físicas sejam `transparentes` para aplicativos de banco de dados.

### Oracle Database

- O Oracle Database é um `SGBDOR`
    - Um `SGBDR` que implementa recursos `orientados a objetos`, como tipos definidos pelo usuário, herança e polimorfismo, é chamado de `Sistema de Gerenciamento de Banco de Dados Objeto-Relacional` (SGBDOR)
- O Oracle Database estendeu o modelo relacional a um `modelo objeto-relacional`, possibilitando o armazenamento de modelos de negócios complexos em um banco de dados relacional
- A tipificação dos dados acontece no momento em que o usuário insere esse dado, e não previamente como os modelos relacionais tradicionais

### Objetos de Esquema

- No Oracle Database, um `schema` é uma `coleção de estruturas lógicas` de dados (tabelas, views, indices, triggers, etc) ou `objetos de schema`
- Um usuário de banco de dados é `proprietário de um schema de banco de dados`, que tem o mesmo nome que o nome de usuário.
- `Objetos de schema` são estruturas criadas pelo usuário que se referem diretamente aos dados no banco de dados.
    - Objetos de schema podem ser criados e manipulados com SQL (DDL)
    - Um objetos de schema é um tipo de objeto de banco de dados.
- O banco de dados suporta muitos tipos de objetos de schema, dos quais os mais importantes são `tabelas e índices`
- Alguns objetos de banco de dados, como perfis e funções, não residem em schemas

#### Tabelas

- Uma `tabela` descreve uma entidade
    - Uma tabela é um conjunto de linhas e colunas
- Uma `coluna` identifica um `atributo da entidade` (uma característica da entidade) descrito pela tabela, enquanto uma `linha` identifica uma `instância da entidade`.
    - A cada coluna é atribuído um nome, um tipo de dados e uma largura
- É possível especificar uma regra, chamada `restrição de integridade`, para uma coluna. Um exemplo é uma restrição NOT NULL, que força a coluna a conter um valor em cada linha

#### Índices

- Um `índice` é uma estrutura de dados opcional que pode ser criado em uma ou mais colunas de uma tabela
- Os índices podem aumentar o desempenho da recuperação de dados
- Um banco de dados pode usar índices para `localizar as linhas solicitadas com eficiência`
- Os índices são `logicamente e fisicamente independentes dos dados`
- É possível descartar e criar índices sem afetar as tabelas ou outros índices

### [Acesso aos Dados - Linguagem SQL](#sql-structured-query-language-material)

- A linguagem SQL é uma `linguagem declarativa` baseada em conjunto que fornece uma interface para um `SGBDR`, como o Oracle Database.
- A linguagem SQL `não é processual` e descreve o que deve ser feito
- A linguagem SQL é a `linguagem padrão ANSI` para bancos de dados relacionais
- Todas as operações nos dados em um Oracle Database são executadas usando instruções SQL
- Uma instrução SQL pode ser considerada um pgograma ou instrução de computador
- Uma instrução SQL é uma sequência de texto SQL
- As instruções SQL permitem executar as seguintes tarefas:
    - [Consultar dados](#dql) 
    - [Inserir, atualizar e excluir linhas em uma tabela](#dml)
    - [Criar, substituir, alterar e liberar objetos](#ddl)
    - [Controlar o acesso ao banco de dados e seus objetos](#dcl-material)
    - [Garantir consistência e integridade do banco de dados](#dtl-material)

### Acesso aos dados - PL/SQL

- O PL/SQL é uma `extensão procedural` do Oracle SQL
- É integrado ao Oracle Database, permitindo que sejam usadas todas as instruções, funções e tipos de dados SQL do Oracle Database
- Pode ser usado para `controlar o fluxo de um programa SQL`, `usar variáveis` e `escrever procedimentos de tratamento de erros`
- Um `procedimento` ou função PL/SQL é um `objeto de schema` que consiste em um conjunto de instruções SQL e outras construções PL/SQL
- As instruções são agrupadas, armazenadas no banco de dados e executadas como uma `unidade` para resolver um problema específico

