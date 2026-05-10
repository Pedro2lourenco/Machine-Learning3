Este é um guia descritivo para o código de análise de churn utilizando Regressão Logística. O objetivo do script é processar dados de clientes de uma empresa de telecomunicações para prever a probabilidade de cancelamento de serviços.
## Estrutura do Projeto
O código está dividido em quatro etapas principais:
 1. **Importação e Carregamento**: Preparação do ambiente e leitura dos dados brutos.
 2. **Pré-processamento**: Seleção de variáveis relevantes e normalização.
 3. **Treinamento do Modelo**: Divisão da base de dados e ajuste da Regressão Logística.
 4. **Avaliação**: Cálculo de métricas de erro e visualização da importância das variáveis.
## Requisitos
Para executar este código, é necessário ter instalado:
 * Python 3.x
 * Pandas
 * Numpy
 * Scikit-Learn
 * Matplotlib
## Descrição das Etapas
### 1. Tratamento de Dados
O conjunto de dados original contém 28 colunas. O script filtra apenas as variáveis que possuem maior correlação teórica com o comportamento de churn:
 * tenure (tempo de permanência)
 * age (idade)
 * address (tempo no endereço atual)
 * income (renda)
 * ed (nível educacional)
 * employ (tempo no emprego atual)
 * equip (uso de equipamentos)
### 2. Normalização
Como as variáveis possuem escalas muito distintas (ex: renda em milhares vs. nível educacional de 1 a 5), é aplicado o **StandardScaler**. Este processo centraliza a média em 0 e define o desvio padrão como 1, garantindo que o modelo de regressão não seja enviesado por valores numericamente maiores.
### 3. Modelo de Regressão Logística
O modelo é treinado utilizando a divisão clássica de treino e teste (67% para treino e 33% para validação). Foram gerados dois tipos de saídas:
 * **Predict**: Classificação direta (0 ou 1).
 * **Predict Proba**: A probabilidade logística de cada indivíduo pertencer a uma classe.
### 4. Métricas e Visualização
A performance é medida através do **Log Loss** (Entropia Cruzada), que avalia o quão próximas as probabilidades previstas estão do valor real.
Além disso, o código gera um gráfico de barras horizontais exibindo os coeficientes do modelo. Isso permite identificar quais fatores mais influenciam positivamente ou negativamente na decisão do cliente de deixar a empresa.
## Como Executar
 1. Certifique-se de que a URL do arquivo CSV está acessível.
 2. Execute o bloco de importações.
 3. Siga a sequência de pré-processamento para garantir que os arrays do Numpy sejam criados corretamente.
 4. O gráfico final será exibido automaticamente após o treinamento.
