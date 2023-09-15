# Preparando um dataset para modelagem de dados

**Contexto:**

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

**Sobre os dados:**

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

**Lendo e inspecionando os dados.**

Está etapa foi feita ultilizando o "ProfileReport" para ter um parâmetro geral sobre a base de dados.

<img src="images/ProfileReport.png">





