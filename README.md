# Desafio-de-Projeto-Processando-e-Transformando-Dados-com-Power-BI
Desafio d eprojeco proposto pela Dio no Santander Bootcamp 2023 - Ciência de Dados com Python
Descrição do desafio módulo 3 – Processamento de Dados Simplificado com Power BI

1. Criação de uma instância na Azure para MySQL
   1. servidor flexivel mysql
   1. Grupo de recurso
      1. grupo\_dio
   1. detalhes servidor
      1. srvprojeto-db-dio
      1. brazil south
      1. mysql 5.7
      1. **Intermitente, B1ms**
      1. 1 vCores, 2 GiB RAM, 20 GiB armazenamento, IOPS de dimensionamento automático
      1. **Redundância geográfica : Sem suporte**
   1. Administrador
      1. master
      1. Minha Senha

1. Criar o Banco de dados com base disponível no github
   1. script no github está com erro . 
   1. usar do [desafio de projeto scripts](https://web.dio.me/topics/desafio-de-projeto-processando-e-transformando-dados-com-power-bi?page=1&order=oldest)
   1. banco de dados = azure\_company

1. Integração do Power BI com MySQL no Azure 
   1. nome  servidor - srvprojeto-db-dio.mysql.database.azure.com
   1. quando não encontra o drive mysql é preciso instalar ele 
      1. Verificação -  abrir powershell
         [System.Data.Common.DbProviderFactories]::GetFactoryClasses()|ogv

1. instalar vc redis x64  e o mysql conector dotnet 

1. Verificar problemas na base a fim de realizar a transformação dos dados

Diretrizes para transformação dos dados

1. Verifique os cabeçalhos e tipos de dados
   1. Corrigido várias colunas com erros
1. Modifique os valores monetários para o tipo double preciso
   1. Alterado 
1. Verifique a existência dos nulos e analise a remoção
   1. Nulo existente, sem necessidade de remover. 
1. Os employees com nulos em Super\_ssn podem ser os gerentes. Verifique se há algum colaborador sem gerente
   1. Não há
1. Verifique se há algum departamento sem gerente
   1. Não há
1. Se houver departamento sem gerente, suponha que você possui os dados e preencha as lacunas
   1. Não há
1. Verifique o número de horas dos projetos

1. Separar colunas complexas
   1. Separado coluna de endereço
1. Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. Fique atento, essa informação influencia no tipo de junção
   1. Mesclado e criado nova tabela
1. Neste processo elimine as colunas desnecessárias. 
   1. Removido colunas 
1. Realize a junção dos colaboradores e respectivos nomes dos gerentes . Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. Caso utilize SQL, especifique no README a query utilizada no processo.
   1. Feita  a junção via powerbi
1. Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores
   1. Mesclado
1. Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro.
   1. Mesclado
1. Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir. 

1. Agrupe os dados a fim de saber quantos colaboradores existem por gerente
   1. Agrupado
1. Elimine as colunas desnecessárias, que não serão usadas no relatório, de cada tabela
   1. Eliminado 
