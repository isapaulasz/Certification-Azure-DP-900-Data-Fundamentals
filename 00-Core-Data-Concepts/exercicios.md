# Exercícios de fixação

## 1. Você tem dados que descrevem produtos e são armazenados em documentos JSON. A estrutura do produto muda ao longo do tempo, à medida que novos atributos são adicionados. Que tipo de dados você tem?

A. Semiestruturado

B. Estruturado

C. Desestruturado

D. Não estruturado

<details>
<summary><b>Resposta</b></summary>

**A**: Os dados semiestruturados têm alguma estrutura, mas permitem variações entre instâncias de uma entidade. Um formato comum para dados semiestruturados é JSON.

</details>

## 2. Quais são os dois tipos de arquivo que armazenam dados no formato columnar? Cada resposta correta apresenta uma solução completa. Selecione todas as respostas aplicáveis.

A. Avro

B. CSV

C. Parquet

D. ORC

<details>
<summary><b>Resposta</b></summary>

**C, D**: ORC e Parquet são formatos de dados colunares. O Avro é baseado em linhas, e o CSV é usado para dados delimitados.

</details>

## 3. Qual tipo de carga de trabalho de dados é otimizada para atualizações e depende de relações entre entidades para correlacionar dados?

A. Analítico

B. Gráfico

C. Série temporal

D. Transacional

<details>
<summary><b>Resposta</b></summary>

**D**: As cargas de trabalho transacionais são otimizadas para operações CRUD (criar, ler, atualizar e excluir). Os bancos de dados analíticos são altamente desnormalizados para armazenar grandes quantidades de dados agregados e são otimizados para leituras. As cargas de trabalho de série temporal não armazenam grandes quantidades de dados agregados. As cargas de trabalho de grafo armazenam dados hierárquicos.

</details>

## 4. Quais são as três propriedades das cargas de trabalho de dados analíticos? Cada resposta correta apresenta uma solução completa.

A. As operações de leitura e gravação são otimizadas.

B. As operações de leitura são otimizadas.

C. Eles calculam as métricas de negócios ao longo do tempo.

D. Eles operam com os dados atuais.

E. Eles operam com dados históricos.

<details>
<summary><b>Resposta</b></summary>

**B, C, E**: As cargas de trabalho de dados analíticos operam em dados históricos, são otimizadas para operações de leitura e calculam as métricas de negócios ao longo do tempo. As operações de leitura e gravação são otimizadas para cargas de trabalho de dados transacionais.

</details>

## 5. Quais dois tipos de aplicativos são usados em sistemas transacionais? Cada resposta correta apresenta uma solução completa.

A. Aplicativos LOB (linha de negócios)

B. Aplicativos dinâmicos

C. Relatórios que apresentam métricas de negócios

D. Relatórios que apresentam medidas OLAP

<details>
<summary><b>Resposta</b></summary>

**A, B**: Aplicativos dinâmicos são usados em sistemas de processamento de dados transacionais. Os aplicativos LOB são um tipo de aplicativo dinâmico que processa dados de negócios.

</details>

## 6. Qual função de trabalho é responsável por solucionar problemas de desempenho de índice, provisionar acesso a bancos de dados e fazer backup de bancos de dados?

A. Administrador de banco de dados

B. Analista de banco de dados

C. Engenheiro de banco de dados

D. Usuário do banco de dados

<details>
<summary><b>Resposta</b></summary>

**A**: Os administradores de banco de dados mantêm bancos de dados existentes. Os engenheiros de banco de dados criam bancos de dados. Os analistas de banco de dados usam dados de um banco de dados para tomar decisões de negócios. Os usuários do banco de dados usam um banco de dados.

</details>

## 7. Qual função de trabalho é responsável por gerenciar a segurança dos dados em um banco de dados, implementar planos de backup e recuperação e monitorar o desempenho de soluções de banco de dados?

A. Administrador de banco de dados

B. Analista de dados

C. Engenheiro de dados

D. Usuário do banco de dados

<details>
<summary><b>Resposta</b></summary>

**A**: Um administrador de banco de dados gerencia a segurança dos dados, implementando planos de backup e recuperação e monitorando o desempenho de soluções de banco de dados. Um engenheiro de dados gerencia a privacidade dos dados, monitorando armazenamentos de dados e pipelines de dados. Um analista de dados é responsável por criar modelos de dados, limpar e transformar dados e encontrar padrões de dados ocultos. Os usuários do banco de dados usam um banco de dados.

</details>

## 8. Qual função de trabalho é responsável por gerenciar a privacidade dos dados, monitorar armazenamentos de dados e monitorar pipelines de dados?

A. Administrador de banco de dados

B. Analista de dados

C. Engenheiro de dados

D. Usuário do banco de dados

<details>
<summary><b>Resposta</b></summary>

**C**: Um engenheiro de dados gerencia a privacidade dos dados, monitorando armazenamentos de dados e pipelines de dados. Um analista de dados é responsável por criar modelos de dados, limpar e transformar dados e encontrar padrões de dados ocultos. Um administrador de banco de dados gerencia a segurança dos dados, implementando planos de backup e recuperação e monitorando o desempenho de soluções de banco de dados. Os usuários do banco de dados usam um banco de dados.

</details>

## 9. Qual função de trabalho é responsável por criar modelos de dados e encontrar padrões de dados ocultos?

A. Administrador de banco de dados

B. Analista de dados

C. Engenheiro de dados

D. Usuários de banco de dados

<details>
<summary><b>Resposta</b></summary>

**B**: Um analista de dados é responsável por criar modelos de dados, limpar e transformar dados e encontrar padrões de dados ocultos. Um engenheiro de dados gerencia a privacidade dos dados, monitorando armazenamentos de dados e pipelines de dados. Um administrador de banco de dados gerencia a segurança dos dados, implementando o plano de backup e recuperação e monitorando o desempenho das soluções de banco de dados. Os usuários do banco de dados usam um banco de dados.

</details>

## 10. Qual tipo de estrutura de dados permite armazenar dados em um formato de duas colunas sem exigir um sistema de gerenciamento de banco de dados complexo?

A. Banco de dados de documentos

B. Banco de dados de grafos

C. Repositório de chave/valor

D. Banco de dados relacional

<details>
<summary><b>Resposta</b></summary>

**C**: Um repositório de chave/valor é usado para pesquisas simples com base em uma única chave para obter um único valor. Um banco de dados relacional é a melhor opção para criar, ler, atualizar e excluir operações (CRUD) e usa a menor quantidade de espaço de armazenamento, mas nossa solução não requer um DBMS (sistema de gerenciamento de banco de dados) no navegador. Um banco de dados de documentos usa dados não estruturados, como JSON, e é otimizado para recuperação, não para operações CRUD. Um banco de dados de grafos é usado para armazenar dados hierárquicos, como gráficos organizacionais que têm nós e bordas.

</details>

## 11. Que tipo de dados devem ser enviados de câmeras de vídeo em um formato binário nativo?

A. Semiestruturado

B. Estruturado

C. Desestruturado

<details>
<summary><b>Resposta</b></summary>

**C**: Dados não estruturados contêm arquivos como documentos, imagens, dados de áudio, dados de vídeo e arquivos binários.

</details>

## 12. Quais são os dois atributos de uma carga de trabalho de dados transacional? Cada resposta correta apresenta uma solução completa.

A. Altamente desnormalizado

B. Altamente normalizado

C. Otimizado para operações CRUD (criar, ler, atualizar e excluir)

D. Otimizado para operações de leitura

<details>
<summary><b>Resposta</b></summary>

**B, C**: Os bancos de dados transacionais são altamente normalizados e são otimizados para operações CRUD.

</details>

## 13. Quais dois atributos são características de uma carga de trabalho de dados analíticos? Cada resposta correta apresenta uma solução completa.

A. Altamente desnormalizado

B. Altamente normalizado

C. Otimizado para operações CRUD (criar, ler, atualizar e excluir)

D. Otimizado para operações de leitura

<details>
<summary><b>Resposta</b></summary>

**A, D**: As cargas de trabalho de dados analíticos são altamente desnormalizadas e são otimizadas para operações de leitura.

</details>

## 14. Qual função de trabalho é responsável por criar soluções de banco de dados, criar bancos de dados e desenvolver procedimentos armazenados?

A. Administrador de banco de dados

B. Analista de banco de dados

C. Engenheiro de banco de dados

D. Usuário do banco de dados

<details>
<summary><b>Resposta</b></summary>

**C**: Os engenheiros de banco de dados criam bancos de dados. Os analistas de banco de dados usam dados de um banco de dados para tomar decisões de negócios. Os usuários do banco de dados usam um banco de dados. Os administradores de banco de dados mantêm bancos de dados existentes.

</details>

## 15. Qual função de trabalho é responsável por criar relatórios de um banco de dados e usar cubos OLAP?

A. Administrador de banco de dados

B. Analista de banco de dados

C. Engenheiro de banco de dados

D. Usuário do banco de dados

<details>
<summary><b>Resposta</b></summary>

**B**: Os analistas de banco de dados usam dados de um banco de dados para tomar decisões de negócios. Os usuários do banco de dados usam um banco de dados. Os administradores de banco de dados mantêm bancos de dados existentes. Os engenheiros de banco de dados criam bancos de dados.

</details>
