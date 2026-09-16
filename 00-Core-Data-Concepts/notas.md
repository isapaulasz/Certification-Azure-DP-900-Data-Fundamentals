# Minhas anotações

## Conceitos de dados do Microsoft Azure Data Core

### Descrever maneiras de representar dados

- Dados: coleção de fatos usados para registrar informações.
- Estrutura de dados: representam entidades importantes para uma organização. Cada entidade tem um ou mais atributos ou características.

1. Descrever características de dados estruturados
    - Modelo mais tradicional de dados.
    - Normalmente possui representação em formato de tabela (entidade), com linhas e colunas (atributos).
    - Geralmente são armazenados em bancos de dados, onde tabelas se referenciam umas às outras por meio de chaves.

2. Descrever características de dados semiestruturados
    - Informações que não residem em um banco de dados relacional, mas possuem alguma forma de estrutura.
    - Permitem alguma variação entre instâncias de entidade.
    - Formatos comuns: JSON, modelo chave-valor e grafos.

3. Descrever características de dados não estruturados
    - Comumente, são dados de arquivos: músicas, fotos, documentos, vídeos e arquivos binários.
    - Não possuem padronização de nome, tamanho ou formato.

---

### Identificar opções de armazenamento de dados

- Arquivos podem ser armazenados em sistemas de arquivos locais, no disco rígido do computador e em mídias removíveis.
- Na maioria das organizações, os dados importantes são armazenados de maneira centralizada em algum sistema de armazenamento compartilhado.
- Cada vez mais, esse local de armazenamento central está sendo hospedado na nuvem.

1. Descrever formatos comuns para arquivos de dados
    - **Dados estruturados:**
        - Arquivos de texto delimitados (CSV, TSV, etc.): geralmente são dados armazenados em formatos de texto sem formatação, com delimitadores de campo e terminadores de linha. É uma boa opção para dados estruturados que são acessados por vários aplicativos e serviços em um formato legível.
        - Parquet: formato de dados em coluna, contendo grupos de linhas em que os dados de cada coluna são armazenados juntos no mesmo grupo. Inclui metadados que descrevem o conjunto de linhas. É especializado em armazenar e processar dados aninhados. Dá suporte a esquemas eficientes de compactação e codificação. É o formato padrão para lakehouses modernos.
        - Avro: baseado em linhas, em que cada arquivo contém um cabeçalho (JSON) que descreve a estrutura. Os dados são armazenados como informação binária em um ou mais blocos de registros.
        - Delta Lake: baseia-se em Parquet, adicionando um log de transações. Permite transações ACID, controle de versão e atualizações confiáveis.

    - **Dados semiestruturados:**
        - JSON: esquema de documento hierárquico, usado para definir entidades de dados (objetos) que têm diversos atributos. Cada atributo pode ser um objeto (ou uma coleção de objetos). É ideal para dados semiestruturados por ser flexível.
        - XML: usa marcas entre colchetes para definir elementos e atributos. Tem sido substituído pelo JSON.
        - Parquet, Avro e Delta Lake também são boas opções de formatos para dados semiestruturados.

    - **Dados não estruturados:**
        - BLOB: objeto binário grande (Binary Large Object). Todos os dados são armazenados em dados binários, em que os bytes são mapeados em caracteres imprimíveis. Comumente, são imagens, vídeos, áudios e documentos de aplicativos.

2. Descrever tipos de bancos de dados
    - **Bancos de dados relacionais:**
        - Comumente usados para armazenar e consultar dados estruturados.
        - Cada instância recebe uma chave primária, usada para referenciar a instância de outras tabelas.
        - As chaves permitem a normalização de bancos de dados relacionais e a eliminação de valores duplicados.
        - São gerenciados e consultados usando SQL.
        - Serviços recomendados: SQL Server, SQL do Azure.

    - **Bancos de dados não relacionais:**
        - São sistemas de gerenciamento de dados que não usam esquema relacional.
        - Geralmente são chamados de NoSQL (embora alguns ofereçam suporte a uma variante do SQL).
        - Tipos comuns:
            1. Bancos de dados chave-valor: cada registro consiste em uma chave exclusiva e um valor associado, em qualquer formato.
            2. Bancos de dados de documentos: forma especial de banco de dados chave-valor, em que o valor é um documento JSON.
            3. Bancos de dados de família de colunas: podem armazenar dados tabulares, abrangendo linhas e colunas. É possível dividir colunas em grupos, chamados de famílias de colunas. Cada família de colunas tem um conjunto de colunas associadas.
            4. Bancos de dados em grafo: armazenam entidades como nós com ligações que definem relações entre elas.
        - Serviços recomendados: Armazenamento de BLOB, Cosmos DB.

---

### Descrever cargas de trabalho de dados comuns

1. Descrever recursos de cargas de trabalho transacionais
    - O processamento transacional costuma ser considerado a principal função da computação empresarial.
    - Um sistema transacional registra transações.
    - Uma transação é uma informação pequena e uma unidade de trabalho discreta, que tem valor, origem, destino, entidades etc.
    - As transações encapsulam eventos específicos que a organização deseja controlar.
    - As transações ocorrem em alto volume diariamente e precisam ocorrer e ser acessíveis rapidamente.
    - O trabalho executado por sistemas transacionais é comumente conhecido como OLTP.
    - OLTP: Online Transaction Processing ou Processamento de Transações em Tempo Real.
    - Soluções OLTP dependem de um sistema de banco de dados com armazenamento otimizado para operações de leitura e gravação. Isso é necessário para dar suporte a cargas de trabalho transacionais em que os registros são criados, recuperados, atualizados e excluídos (CRUD).
    - Dados transacionais são informações que rastreiam interações relacionadas às atividades de uma organização.
    - Para garantir integridade, os sistemas OLTP impõem transações compatíveis com a semântica **ACID**:
        - **Atomicidade**: cada transação é tratada como uma unidade independente, que resulta em sucesso ou falha por completo.
        - **Consistência**: as transações só podem conduzir os dados do banco de dados de um estado válido para outro estado válido.
        - **Isolamento**: a execução concorrente de transações não muda o estado do banco de dados.
        - **Durabilidade**: assim que uma transação for confirmada, ela permanecerá assim.

2. Descrever recursos de cargas de trabalho analíticas
    - Um sistema analítico é projetado para dar suporte aos usuários de negócios.
    - Geralmente são sistemas apenas de leitura.
    - Armazenam e acessam grandes volumes de dados históricos ou métricas de negócio.
    - Os dados normalmente passam por ETL ou ELT e são carregados em tabelas (normalmente em data lakehouses).
    - Os dados podem ser carregados em um modelo de OLAP.
    - OLAP: Online Analytical Processing ou Processamento Analítico Online.
    - Analistas precisam dos dados brutos para serem consultados e visualizados.
    - Data Lakes e Data Warehouses são comuns em cenários de análise de dados.
    - Data lakehouses é uma inovação que combina armazenamento flexível e escalonável com semântica de consulta relacional. O esquema da tabela pode exigir alguma desnormalização de dados em uma fonte de dados OLTP.
    - Duas plataformas reúnem a maioria desses recursos em um único workspace:
        - Microsoft Fabric: plataforma de análise SaaS que reúne recursos de armazenamento, engenharia de dados, data warehouse e relatórios em um workspace.
        - Azure Databricks: plataforma de análise em nuvem criada para engenharia de dados em larga escala e ciência de dados, usando Delta Lake (Parquet) além de um log de transações que permite controle de versão e transações ACID.
    - Um padrão para organização de dados em lakehouse é a arquitetura medalhão:
        1. Bronze: dados brutos, ingeridos dos sistemas de origem, sem transformação, preservando os registros originais para reprocessamento.
        2. Prata: dados limpos, sem duplicatas e com tipos de dados padronizados.
        3. Gold: dados agregados e prontos para negócios, modelados para casos específicos de relatórios e análises.
    - Esse padrão cria limites claros de qualidade em cada camada e sempre dá para reprocessar dados dos registros bronze originais se os requisitos forem alterados.

---

### Identificar funções e responsabilidades para cargas de trabalho de dados

1. Descrever as responsabilidades dos administradores de banco de dados
    - **Funções:**
        - Gerenciamento de banco de dados: design, implementação, manutenção e aspectos operacionais de bancos de dados locais e na nuvem.
        - Segurança de dados: gerenciar a segurança dos dados e a disponibilidade de dados.
        - Backups: trabalhar com stakeholders para implementar políticas, ferramentas, processos de backup e planos de recuperação.
        - Atribuir permissões aos usuários.
        - Monitoramento de desempenho.
    - **Ferramentas comuns:**
        - Banco de Dados SQL do Azure: banco de dados PaaS, totalmente gerenciado e hospedado no Azure. Administradores de banco de dados normalmente provisionam e gerenciam os sistemas de banco de dados SQL do Azure para dar suporte a aplicativos de LOB (linha de negócios) que precisam armazenar dados transacionais.
        - Azure Cosmos DB: sistema de banco de dados não relacional em escala global (NoSQL) que dá suporte a várias APIs. Instâncias podem ser provisionadas e gerenciadas por um administrador de banco de dados.
        - Azure Data Studio
        - SQL Server Management Studio
        - Portal/CLI do Azure

2. Descrever responsabilidades de engenheiros de dados
    - **Funções:**
        - Colaborar com stakeholders para projetar e implementar cargas de trabalho relacionadas aos dados.
        - Trabalhar com pipelines de ingestão, atividades de limpeza, transformação e armazenamento.
        - Gerenciar e monitorar pipelines de dados.
        - Preparar dados para análise.
    - **Ferramentas comuns:**
        - Banco de Dados SQL do Azure: banco de dados PaaS, totalmente gerenciado e hospedado no Azure. Engenheiros de dados podem usá-lo como fonte para pipelines de dados que executam operações de ETL.
        - Azure Cosmos DB: sistema de banco de dados não relacional em escala global (NoSQL) que dá suporte a várias APIs. Engenheiros de dados geralmente precisam integrar fontes de dados do Cosmos DB a soluções analíticas corporativas.
        - Armazenamento do Azure: serviço principal do Azure que permite armazenar dados em contêineres de blobs, compartilhamentos de arquivos e tabelas. Engenheiros de dados usam o Armazenamento do Azure para hospedar data lakes.
        - Azure Data Factory: serviço Azure que permite definir e agendar pipelines de dados para transferir e transformar dados. É usado por engenheiros de dados para criar soluções de ETL.
        - Microsoft Fabric: plataforma de análise SaaS unificada. Ela reúne engenharia de dados, data warehousing, análise em tempo real, ciência de dados e Power BI em um único workspace baseado em navegador, além de uma camada de armazenamento compartilhada chamada OneLake.
        - Azure Databricks: plataforma de análise em nuvem, otimizada para engenharia de dados em larga escala, ciência de dados e análises SQL em formatos abertos de lakehouse, principalmente Delta Lake. Engenheiros de dados podem usá-la para criar armazenamentos de dados analíticos.
        - Azure Stream Analytics: mecanismo de processamento de fluxo em tempo real que captura um fluxo de dados de uma entrada, aplica uma consulta para extrair e manipular dados do fluxo de entrada e grava os resultados em uma saída para análise ou processamento adicional. Engenheiros de dados podem incorporar o Azure Stream Analytics em arquiteturas de análise de dados.
        - Microsoft Purview: solução para governança e descoberta de dados, permitindo criar um mapa dos dados e acompanhar a linhagem de dados. Engenheiros de dados podem usar o Microsoft Purview para impor a governança de dados em toda a empresa e garantir a integridade dos dados usados para dar suporte a cargas de trabalho analíticas.
        - Azure Synapse Studio
        - SQL Server Management Studio
        - Portal/CLI do Azure

3. Descrever responsabilidades de analistas de dados
    - **Funções:**
        - Permitir que as empresas maximizem o valor dos ativos.
        - Explorar os dados para identificar tendências.
        - Oferecer insights sobre os dados.
        - Gerar relatórios visuais.
        - Modelagem de dados para análise.
        - Combinar dados para visualização e análise.
    - **Ferramentas comuns:**
        - Banco de Dados SQL do Azure: banco de dados PaaS, totalmente gerenciado e hospedado no Azure. Analistas de dados podem consultar os bancos de dados SQL do Azure diretamente para criar relatórios.
        - Power BI: plataforma de visualização de dados e business intelligence. Analistas de dados usam o Power BI para se conectar a fontes de dados, criar relatórios interativos e dashboards e compartilhar insights em toda a organização.
        - Azure Databricks: plataforma de análise em nuvem, otimizada para engenharia de dados em larga escala, ciência de dados e análises SQL em formatos abertos de lakehouse, principalmente Delta Lake. Analistas de dados podem usar o suporte de notebook nativo para consultar e visualizar dados.
        - Azure Data Explorer: plataforma de análise de Big Data. Analistas de dados podem usá-la para consultar e analisar dados que incluem um atributo de carimbo de data/hora, como normalmente é encontrado em arquivos de log e dados de telemetria da IoT.


