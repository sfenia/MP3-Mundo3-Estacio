
# # BackEnd sem banco não tem

## 1º Procedimento | Mapeamento Objeto-Relacional e DAO

### Objetivo da Prática
O objetivo desta prática é desenvolver um aplicativo Java com acesso ao banco de dados SQL Server por meio do middleware JDBC (Java Database Connectivity). Durante o desenvolvimento, focaremos na implementação de persistência usando o padrão DAO (Data Access Object) e no mapeamento objeto-relacional em sistemas Java.

### Desenvolvimento da Prática
A seguir, apresentamos um resumo das etapas realizadas durante o desenvolvimento da prática:

1. **Configuração do Projeto e Bibliotecas:** Iniciamos criando um projeto chamado "CadastroBD" no NetBeans, configurando-o como um Aplicativo Java Padrão. Adicionamos o driver JDBC para SQL Server ao projeto, seguindo as instruções fornecidas.

2. **Configuração do Acesso ao Banco de Dados:** Configuramos o acesso ao banco de dados SQL Server pelo NetBeans. Criamos uma conexão, definimos os parâmetros de conexão (database, user e password), e testamos a conexão para garantir que está funcionando corretamente.

3. **Criação de Entidades e Classes Utilitárias:**
   - Criamos uma classe `Pessoa` com campos como `id`, `nome`, `logradouro`, `cidade`, `estado`, `telefone` e `email`. Implementamos construtores e um método `exibir` para imprimir os dados no console.
   - Criamos classes `PessoaFisica` e `PessoaJuridica` que herdam da classe `Pessoa`. Adicionamos campos específicos a cada uma e reescrevemos construtores e o método `exibir` para utilizar o polimorfismo.

4. **Classes Utilitárias:**
   - Criamos uma classe `ConectorBD` com métodos para obter conexão, `PreparedStatement`, e `ResultSet`. Também implementamos métodos `close` sobrecarregados para garantir o fechamento seguro dos recursos.
   - Criamos a classe `SequenceManager` para gerenciar sequências no banco de dados.

5. **Implementação do Padrão DAO:**
   - Criamos as classes `PessoaFisicaDAO` e `PessoaJuridicaDAO` que seguem o padrão DAO. Implementamos métodos para buscar pessoas, todas as pessoas, incluir, alterar e excluir pessoas. Utilizamos objetos `ConectorBD` e `SequenceManager` nas classes DAO.

6. **Teste das Funcionalidades:**
   - Na classe `CadastroBDTeste`, implementamos operações para criar, alterar, consultar e excluir pessoas físicas e jurídicas no banco de dados.
   - Verificamos os resultados por meio do console de saída do NetBeans.

### Resultados Esperados
Os resultados esperados incluem um código bem organizado e funcional, a utilização efetiva das bibliotecas JDBC para interagir com o SQL Server, e a demonstração das habilidades necessárias para desenvolver um aplicativo Java que realiza persistência de dados em um banco de dados relacional.

## Análise e Conclusão

Durante esta prática, exploramos conceitos importantes da programação Java relacionados à persistência de dados em um banco de dados SQL Server. Focamos no uso do middleware JDBC, no padrão DAO para o acesso aos dados e no mapeamento objeto-relacional.

Respondendo às questões propostas:

1. **Importância dos Componentes de Middleware, como o JDBC:** Componentes de middleware, como o JDBC, desempenham um papel fundamental na conexão de aplicativos Java com bancos de dados. Eles oferecem uma camada de abstração que permite que os aplicativos se comuniquem de maneira uniforme com diferentes sistemas de gerenciamento de banco de dados (DBMS). Isso facilita o desenvolvimento de aplicativos independentes do DBMS subjacente e, portanto, mais portáteis.

2. **Diferença no Uso de Statement ou PreparedStatement para a Manipulação de Dados:** A diferença principal entre `Statement` e `PreparedStatement` está na segurança e desempenho. O `PreparedStatement` é mais seguro contra ataques de injeção de SQL, pois permite a vinculação de parâmetros de consulta de forma segura. Além disso, o `PreparedStatement` é pré-compilado, o que pode melhorar o desempenho em consultas repetidas.

3. **Como o Padrão DAO Melhora a Manutenibilidade do Software:** O padrão DAO (Data Access Object) isola a lógica de acesso a dados do restante do código do aplicativo. Isso melhora a manutenibilidade do software, pois permite que você altere a lógica de acesso a dados em um único local (as classes DAO) sem afetar outras partes do código. Além disso, torna mais fácil a substituição de fontes de dados, como a mudança de um banco de dados SQL Server para um banco de dados MySQL, sem impactar o restante do aplicativo.

4. **Como a Herança é Refletida no Banco de Dados em um Modelo Estritamente Relacional:** Em um modelo estritamente relacional, a herança não é refletida diretamente no banco de dados. Em vez disso, cada tabela corresponde a uma classe no código Java. No entanto, se estivermos lidando com um modelo de banco de dados orientado a objetos, pode haver uma correspondência mais direta entre as hierarquias de herança no código e as tabelas no banco de dados, usando técnicas como a "tabela de classe concreta" ou a "tabela de classe única".

## 2º Procedimento | Alimentando a Base

### Objetivo da Prática
O objetivo desta etapa é implementar um cadastro em modo texto para interagir com o usuário e realizar operações no banco de dados. Isso inclui inclusão, alteração, exclusão, exibição por ID, exibição de todos os registros e finalização da execução.

### Desenvolvimento da Prática
Durante esta etapa, realizamos as seguintes ações:

1. **Alteração do Método Main:** Modificamos o método `main` da classe principal do projeto para implementar um cadastro em modo texto. O programa oferece opções ao usuário, como incluir, alterar, excluir, exibir por ID, exibir todos e finalizar a execução.

2. **Funcionalidades do Cadastro em Modo Texto:** As principais funcionalidades implementadas incluem:
   - Inclusão de pessoas físicas ou jurídicas, recebendo dados do usuário e adicionando no banco de dados através das classes DAO apropriadas.
   - Alteração de dados de pessoas, permitindo a escolha do tipo (física ou

 jurídica), entrada de ID, exibição dos dados atuais, solicitação de novos dados e alteração no banco de dados.
   - Exclusão de pessoas, com seleção do tipo e entrada de ID, removendo os registros do banco de dados.
   - Exibição dos dados de uma pessoa por ID, com consulta ao banco de dados através das classes DAO.
   - Exibição de todos os registros de um determinado tipo (física ou jurídica) no banco de dados.
   - Finalização do programa quando o usuário desejar.

3. **Teste das Funcionalidades:** Testamos as funcionalidades do sistema, incluindo operações de inclusão, alteração, consulta e exclusão, tanto para pessoas físicas quanto para pessoas jurídicas. Verificamos os resultados usando o SQL Server Management Studio.

### Resultados Esperados
Os resultados esperados incluem um código bem organizado e funcional para o cadastro em modo texto, a interação eficaz com o usuário por meio da classe `Scanner`, e a demonstração das habilidades necessárias para desenvolver um aplicativo Java que interage com um banco de dados relacional.

## Análise e Conclusão

Nesta prática, demos continuidade ao desenvolvimento do aplicativo Java com acesso ao banco de dados SQL Server. Implementamos um cadastro em modo texto que permite ao usuário realizar operações de CRUD (criação, leitura, atualização e exclusão) nos registros do banco de dados.

Respondendo às questões propostas:

1. **Diferenças entre a Persistência em Arquivo e a Persistência em Banco de Dados:** A persistência em arquivo armazena dados em estruturas de arquivos locais, enquanto a persistência em banco de dados utiliza sistemas de gerenciamento de banco de dados para armazenar dados de forma estruturada e segura. Os bancos de dados oferecem recursos avançados, como consultas SQL, transações ACID e segurança integrada, tornando-os mais adequados para aplicativos de negócios e grande escala.

2. **Uso de Operador Lambda para Simplificar a Impressão dos Valores:** O uso de operadores lambda simplifica a impressão de valores em coleções, como listas ou conjuntos. Eles permitem que você especifique uma ação a ser executada em cada elemento da coleção de forma concisa. Isso simplifica o código em comparação com a iteração manual e torna o código mais legível.

3. **Necessidade de Marcar Métodos como Static:** Métodos acionados diretamente pelo método `main`, sem o uso de um objeto, precisam ser marcados como `static` porque o método `main` é estático. Isso significa que ele pertence à classe, não a uma instância específica da classe. Métodos estáticos podem ser chamados diretamente na classe sem a necessidade de criar uma instância da classe, o que é útil quando você precisa iniciar a execução do programa.

Esta prática forneceu uma experiência prática valiosa no desenvolvimento de aplicativos Java que interagem com um banco de dados relacional usando o JDBC e seguem práticas de programação adequadas.

