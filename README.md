# Projeto Airbnb Rio - Ferramenta de Previsão de Preço de Imóvel para pessoas comuns

Contexto
No Airbnb, qualquer pessoa que tenha um quarto ou um imóvel de qualquer tipo (apartamento, casa, chalé, pousada, etc.) pode ofertar o seu imóvel para ser alugado por diária.

Você cria o seu perfil de host (pessoa que disponibiliza um imóvel para aluguel por diária) e cria o anúncio do seu imóvel.

Nesse anúncio, o host deve descrever as características do imóvel da forma mais completa possível, de forma a ajudar os locadores/viajantes a escolherem o melhor imóvel para eles (e de forma a tornar o seu anúncio mais atrativo)

Existem dezenas de personalizações possíveis no seu anúncio, desde quantidade mínima de diária, preço, quantidade de quartos, até regras de cancelamento, taxa extra para hóspedes extras, exigência de verificação de identidade do locador, etc.

Nosso cbjetivo
Construir um modelo de previsão de preço que permita uma pessoa comum que possui um imóvel possa saber quanto deve cobrar pela diária do  no Rio de Janeiroseu imóvel.

Ou ainda, para o locador comum, dado o imóvel que ele está buscando, ajudar a saber se aquele imóvel está com preço atrativo (abaixo da média para imóveis com as mesmas características) ou não.

O que temos disponível, inspirações e créditos
As bases de dados foram retiradas do site Kaggle, devido ao volume de dados.

As bases de dados são os preços dos imóveis obtidos e suas respectivas características em cada mês.
Os preços são dados em reais (R$)
Temos bases de abril de 2018 a maio de 2020, com exceção de junho de 2018 que não possui base de dados
Expectativas Iniciais
Acredito que a sazonalidade pode ser um fator importante, visto que meses como dezembro costumam ser bem caros no RJ
A localização do imóvel deve fazer muita diferença no preço, já que no Rio de Janeiro a localização pode mudar completamente as características do lugar (segurança, beleza natural, pontos turísticos)
Adicionais/Comodidades podem ter um impacto significativo, visto que temos muitos prédios e casas antigos no Rio de Janeiro
Vamos descobrir o quanto esses fatores impactam e se temos outros fatores não tão intuitivos que são extremamente importantes.

No arquivo AirbnbRio.ipynb fazemos:
•	Importação das bibliotecas utilizadas;
•	Importação da base de dados;
•	Entendimento  da base de dados;
•	Análise e manipulação dos dados;
•	Mapa de calor;
•	Tratamento da base de dados;
•	Criação de funções para gráficos de análises;
•	Tratamento de colunas de valores;
•	Visualização de mapas de propriedades;
•	Criação de métricas de avaliação (foram utilizados o R² e RMSE);
•	Escolhas dos modelos a serem avaliados
  o	Rendom Forest
  o	LinearRegression
  o	Extra Tree
•	O modelo escolhido foi o ExtraTreesRegressor.

Em DeployProjetoAirbnb.ipynb:
•	Usamos o streamlit para a criação da interface;
•	Criamos dicionários para facilitar a utilização do modelo
  o	x_numericos: Este dicionário contém as variáveis numéricas que podem ser usadas como features no modelo.
  o	x_tf: Este dicionário é para variáveis categóricas binárias, provavelmente representadas como 0 (falso) e 1 (verdadeiro).
  o	x_listas: Este dicionário contém listas de categorias possíveis para variáveis categóricas. 
•	Criação de um botão para a previsão do modelo
