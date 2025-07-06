# Alura_One-Challenge_TelecomX

## 📝 Descrição do Projeto
Este projeto realiza uma análise completa sobre a evasão de clientes (churn) em uma empresa fictícia de telecomunicações, a TelecomX. O objetivo principal é identificar os fatores que mais influenciam a decisão de um cliente cancelar seu contrato, utilizando técnicas de **Extração, Transformação e Carga (ETL)** e **Análise Exploratória de Dados (EDA)**.

A partir dos insights gerados, o projeto busca fornecer recomendações estratégicas que possam auxiliar a TelecomX a desenvolver ações mais eficazes para a retenção de clientes.

## 📊 O Conjunto de Dados
O dataset utilizado contém informações demográficas dos clientes, os serviços contratados (telefone, internet), detalhes da conta (tipo de contrato, forma de pagamento, cobranças) e, mais importante, a informação se o cliente evadiu ou não (Churn).

Os dados foram originalmente fornecidos em um arquivo JSON com uma estrutura aninhada, exigindo um processo de transformação para viabilizar a análise.

## ⚙️ Metodologia Aplicada
O projeto foi desenvolvido no Google Colab e seguiu as seguintes etapas:

**1. Extração (Extract)**

Os dados foram carregados diretamente de um arquivo JSON hospedado online para um DataFrame utilizando a biblioteca pandas.

**2. Transformação (Transform)**

Esta foi a etapa mais crítica do projeto, onde os dados brutos foram limpos e preparados para a análise. As principais transformações incluem:

- **Desaninhamento de Dados**: As colunas com dados aninhados em formato JSON (customer, phone, internet, account) foram normalizadas e integradas ao DataFrame principal.

- **Tratamento de Dados Faltantes**: Valores ausentes na coluna de cobranças totais (Charges.Total) foram tratados, assumindo-se que representavam clientes novos sem cobranças acumuladas.

- **Padronização e Tradução**: Os nomes das colunas foram padronizados para letras minúsculas e, juntamente com os valores categóricos, foram traduzidos para o português para facilitar a compreensão.

- **Conversão de Tipos**: Colunas categóricas binárias (Sim/Não) foram convertidas para o formato numérico (1/0) para otimizar a análise.

- **Engenharia de Features**: Criação de uma nova variável (taxa_diaria) para explorar outras perspectivas da cobrança.

**3. Análise Exploratória e Visualização (EDA)**

Com os dados limpos e estruturados, foi realizada uma análise exploratória para entender o perfil dos clientes que evadiram. Foram criadas visualizações de dados interativas com a biblioteca plotly para investigar a relação entre o churn e variáveis como:

- Tempo de contrato (tenure)

- Tipo de contrato (mensal, anual)

- Serviços contratados (e.g., tipo de internet)

- Valor da cobrança mensal

- Características demográficas (gênero, se é idoso, etc.)

## 💡 Principais Insights da Análise
A análise revelou padrões claros no comportamento dos clientes que cancelaram o serviço:

- **Tempo de Contrato**: Clientes com menor tempo de contrato (novos clientes) possuem uma taxa de churn significativamente mais alta. A taxa de evasão diminui drasticamente à medida que o cliente permanece mais tempo na empresa.

- **Tipo de Contrato**: Clientes com contrato mensal são muito mais propensos a cancelar do que aqueles com contratos de 1 ou 2 anos.

- **Serviço de Internet**: Clientes que possuem o serviço de fibra ótica apresentam uma taxa de churn maior, o que pode indicar problemas de qualidade, instabilidade ou uma percepção de custo-benefício desfavorável em comparação com a concorrência.

- **Valor da Cobrança**: A evasão é mais comum entre clientes com taxas mensais mais elevadas.

- **Faturamento**: Clientes que utilizam fatura eletrônica (PaperlessBilling) tendem a evadir mais, sugerindo uma possível fricção ou insatisfação com o processo de faturamento digital.

## 🛠️ Tecnologias Utilizadas
**Linguagem**: Python

**Bibliotecas**:

- pandas para manipulação e análise de dados.

- plotly para a criação de visualizações de dados interativas.

**Ambiente**: Google Colab

