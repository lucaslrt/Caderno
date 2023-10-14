# SEGURANÇA CIBERNÉTICA E DA INFORMAÇÃO (+Material)

## Material de Estudo

- https://www.youtube.com/watch?v=2zkfSYjVf7Y

## Dicas de estudo

- Estudar algoritmos de sistemas de criptografia

## Segurança da Informação

- A segurança da informação se concentra na confiabilidade das informações e no gerenciamento da continuidade das operações (Plano de continuidade de negócios [PCN]). Para avaliar se meu dado é confiável existem alguns pilares a serem seguidos:
    - Integridade: Garantir a exatidão da informação
    - Confidencialidade: Garantir somente acesso autorizado às informações.
    - Disponibilidade: Garantir que a informação esteja sempre disponível.
    - Autenticidade: Garantir que a informação é autentica.
    - Não-repúdio ou Irretratabilidade: Garantir que o usuário não negue autoria ou alterações nas informações

- Dicas:
    - A banca pode formular um novo pilar para uma questão expecífica ao longo do enunciado, por isso, é importante ficar atento às palavras-chave (Legalização, responsabilização, etc...)

## Controle de Acesso

- É o processo de implementação e execução das políticas de autorização. Existem 3 tipos de controle de acesso:
    - DAC(Controle de Acesso Discricionário): Onde os usuários têm uma quantidade significativa de controle sobre os recursos que possuem. O dono do recurso define quem pode acessar aquele recurso.
    - MAC (Controle de Acesso Obrigatório): Onde as políticas de acesso são centralizadas e administradas de forma mais rígida, muitas vezes em ambientes altamente seguros. Existem categorias, o dado recebe uma categoria (público, privado, sensível, etc). Somente o usuário que tem uma classificação maior ou igual pode acessar a categoria.
    - RBAC (Controle de Acesso Baseado em Função): Onde as permissões são atribuídas com base nas funções dos usuários dentro da organização. Ao invés de atribuir a permissão a um usuário específico você atribui a um grupo 
- Há também o Controle de Acesso Físico:
    - Medidas implementadas para prevenir o acesso não autorizado a recursos físicos.
    - Barreiras físicas, sistemas de identificação, alarmes, etc..
- Temos também o Controle de Acesso Lógico
    - Medidas implementadas para prevenir o acesso não autorizado a recursos informacionais e sistemas informatizados.
    - Autenticação, Autorização, Criptografia, Firewalls, IDS (Sistemas de Detecção de Intrusões), IPS (Sistemas de Prevenção de Intrusões), Registros e Monitoramento, Antivirus, Antispam, etc...

## Autenticação

- Ato de estabelecer ou confirmar algo ou alguém como autêntico, isto é, que reivindica a autoria ou a veracidade de alguma coisa. Ou seja, eh identificar-se para um sistema.

- Confirmação da procedência de um objeto ou pessoa, neste caso, frequentemente relacionada com a verificação da sua identidade

- Fatores de Autenticação
    - Autenticação baseada em conhecimento (O que você sabe[Senha, por exemplo])
    - Autenticação baseada na propriedade (O que você tem ou possui[Token, app de autenticação, certificados digitais])
    - Autenticação baseada na característica (O que você é [Biometria])

- MFA (Multi Factor Autenticator): Usar dois ou mais fatores de autenticação. Pode ser referido tbm como 2FA (Two factor autenticator)

- Autorização
    - É o processo de definir e gerenciar as permissões que são atribuídas a um usuário ou a um grupo de usuários
    - As permissoes podem incluir, por exemplo, acesso a determinados arquivos, capacidade de realizar certas operações ou de utilizar determinados recursos do sistema.
    - Esse processo pode ser gerenciado através de políticas de controle de acesso como ACL(Lista de controle de Acesso) ou através de modelos como RBAC (Controle de Acesso Baseado em Função)

- Auditoria
    - É o processo de monitoramento e registro das atividades de usuários e sistemas.
    - Assegurar que as políticas de controle de acesso estão sendo seguidas e para detectar qualquer atividade suspeita ou não autorizada.
    - As informações coletadas podem ser usadas para análises de segurança, investigaçoes forenses e para ajudar a melhorar as políticas de controle de acesso no futuro.

## Criptografia

- Técnica que utiliza algoritmos matemáticos para proteger informações, garantindo confidencialidade, integridade e autenticidade dos dados.

- Criptografia simétrica:

- Criptografia assimétrica:

- Função hash criptográfica
