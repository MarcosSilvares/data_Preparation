# Preparando um dataset para modelagem de dados

## Contexto:

Uma empresa do ramo de e-commerce contratou você para levantar os indicadores de
recência, frequência e ticket médio (RFM) dos seus clientes.
A saber RFM:
 - R (Recency): Tempo que o cliente realizou a última compra (em dias)
 - F (Frequency): Quantidade de compras realizadas pelo cliente
 - M (Monetary): Valor do ticket médio gasto pelo cliente
onde ticket médio = média do total gasto por pedido para cada cliente.
Para isso, vocês receberam uma base de dados (arquivo csv) e devem construir um
código em Python que gera um output também csv, porém contendo apenas a
identificação do cliente e métricas RFM.

## Sobre os dados:

A tabela contém informações de compras de um e-commerce em 37 países. Contém a
identificação do cliente e os dados da compra.

| Coluna      | Descrição   | 
|-------------|-------------|
CustomerID    | Código de identificação do cliente
Description   | Descrição do produto             
InvoiceNo     | Código da fatura                   
StockCode     | Código de estoque do produto      
Quantity      | Quantidade do produto             
InvoiceDate   | Data do faturamento (compra)       
UnitPrice     | Preço unitário do produto         
Country       | País da compra                    

## Lendo e inspecionando os dados.

Está etapa foi feita ultilizando o "ProfileReport" para ter um parâmetro geral sobre a base de dados.

<img src="images/ProfileReport.png">

Com isso é possivel ter um bom parâmetro sobre a base, com informações como Número de Variáveis, Células faltantes em número e em porcentagem, Linhas Duplicadas em número e em porcentagem. Também é possivel ver os tipos das variáveis e a distribuição dos dados.

## Tratamento de Dados(Valores Nulos).

Verificando os valores nulos com o "isna" e utilize a função "sum" para a somar
a quantidade de nulos.

<img src="images/valoresNulos.png">

É possivel ver 299 Valores Nulos na coluna "Description", 34935 Valores Nulos na coluna "CustomerID" e 1 Valor Nulo na coluna "Country"

**Preços unitários e quantidade de produtos iguais ou inferior a 0**

<img src="images/preçoUnitario.png">

**Linhas nulas do CustomerID.**

<img src="images/nulosCustomerID.png">

Aqui temos os valores nulos totalmente zerados, conforme verificamos acima.

## Tratamento de Dados(Valores Duplicados).

Veridicando se existem dados duplicados através da função "duplicated" e dropando-as.

<img src="images/duplicados.png">

Após esta etapa temos os valores duplicados removidos e a base sem dados nulos conforme vimos um pouco acima.

## Corrigindo os tipos de dados.

**Tipos de dados:**

<img src="images/tipoDados.png">

É possível observar alguns erros: "InvoiceDate" está como "object" quando deveria estar como "datetime64[ns]" e "CustomerID" está como "float64" quando deveria estar como "int64". Vamos corrigi-los logo em seguida.

**Corrigindo Tipos:**

<img src="images/dadosCorrigidos.png">

Podemos observar que os dados foram devidamente corrigidos.

## Tratando Outliers.

**Observando Outliers:**

<img src="images/observOutliers.png">

Atráves da vizualização é possível observar a existência de outliers, ou seja, Valores atípicos e inconsistentes. 

**Removendo Outliers:**

A empresa pede para remover os outliers extremos em que a quantidade do item na compra é superior a 10.000, e o preço unitário é maior que 5.000.

<img src="images/removeOutliers.png">

Logo após a remoção é possível ver que não existem mais outliers e o dataset está limpo para proseguir com a obtenção das métricas solicitada.

<img src="images/observOutliers2.png">

## Criando coluna adicional.

Utilizando as colunas Quantity e UnitPrice e criando uma coluna adicional com o preço total da compra. Esta coluna adicional irá nos ajudar a criar as vizualizações solicitadas pela empresa.

<img src="images/TotalPrice.png">

## Plotando Gráficos

A Empresa solicitou que fossem plotados alguns gráficos para observarem visualmente algumas métricas.

**Top 10 países com maior valor em vendas**

<img src="images/top10pais_valor_vendas.png">

**Top 10 produtos mais vendidos**

<img src="images/top10produtos_mais_vendidos.png">

**Valor de venda total por mês**

<img src="images/valor_venda_mes.png">

**Valor de venda total por mês e por país (considerando apenas os top 10)**

<img src="images/valor_venda_mes_pais.png">

## Cálculo do RFM

**Recência:**

Recência é a diferença em dias da última compra do cliente e da última
compra disponível no conjunto de dados, que calcularam previamente.

<img src="images/recencia.png">

**Frequência:**

Frequência é a quantidade de compras feitas pelo cliente

<img src="images/frequencia.png">

**Monetário:**

M é o ticket médio, ou seja, a média das compras feitas pelo cliente.

<img src="images/monetario.png">

**Dataframe RFM:**

<img src="images/dataframeRFM.png">








