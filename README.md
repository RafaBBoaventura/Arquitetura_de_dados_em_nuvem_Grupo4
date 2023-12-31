# **Arquitetura_de_dados_em_nuvem_Grupo4**

Repositório criado para disponibilizar a documentação inicial e os demais arquivos a serem criados ao longo deste projeto. Projeto realizado para a disciplina de Projeto: Arquitetura de Dados em Nuvem

**Componentes**

Felipe Oliveira Martins

Rafael Barroso De Oliveira

Natalia De Souza Lomba Dos Santos

**1.	Introdução**

Nossa empresa é uma consultoria que faz analise e levantamento de dados para auxiliar as empresas nas tomadas de decisão. Fomos acionados por uma transportadora de grande porte, que atua há mais de 30 anos no mercado de transporte de cargas e possui uma tecnologia que monitora o consumo de combustível por KM rodado e faz o monitoramento pela rota de viagem programada para o veículo. 

Por não possuírem um conhecimento referente a variação dos valores de combustível, a tecnologia implantada não está sendo bem explorada, afetando nas tomadas de decisão.
O objetivo deste trabalho é fazer uma análise histórica sobre a variação de preços dos combustíveis com o objetivo de aumentar a compreensão sobre como essa variação impacta nos custos da companhia. Além disso, pretende-se entregar uma análise sobre as tendências futuras para esses preços no próximo semestre utilizando modelos de machine learning, permitindo que o cliente faça um planejamento de custos mais adequado. 

Alguns dos objetivos chaves e análises que serão realizadas ao longo do projeto são:

• Quantidade de postos pesquisados. 

• Evolução do preço médio, máximo e mínimo de revenda ao longo do tempo.

• Preço de revenda por região e estados do Brasil.

• Análise de qual produto teve maior variação (%) de preço. 

• Interessante explorar outras informações que possam complementar a análise e ter algum impacto / relação com o aumento dos preços, como: Histórico do PIB, variação do IPCA, ocorrência de eventos mundiais (ex.pandemia, guerras), valor do salário mínimo, cotação do dólar, mudança na política de preço da Petrobras entre outros.

Fonte dos dados: https://dados.gov.br/dados/conjuntos-dados/serie-historica-de-precos-de-combustiveis-e-de-glp

**2. Governança de dados:**

A governança de dados é o conjunto de políticas, processos e práticas que visam garantir que os dados sejam geridos de maneira eficaz e eficiente, a fim de maximizar seu valor e minimizar seus riscos.

**Importância:**

A governança de dados é fundamental para garantir que os dados sejam confiáveis, precisos e protegidos, e para assegurar que os usuários finais tenham acesso aos dados de que precisam para tomar decisões informadas.

**3. Arquitetura de Dados:**

Para definir a arquitetura do nosso projeto foi necessário fazer um planejamento sobre a estrutura necessária e definir qual seria a lógica seguida. Com base nisso, definimos a estrutura que está exposta abaixo em um esquema ilustrativo, representado pela figura 1.

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/09a8561f-2df7-4dd1-98cd-3d237c7494ee)

Na figura 1, a fonte de dados é composta pela base de dados disponibilizada no site de Dados Abertos do Governo e que pode ser consultada através do site: https://dados.gov.br/dados/conjuntos-dados/serie-historica-de-precos-de-combustiveis-e-de-glp. A base de dados encontra-se em formato XML no Excel e traz o levantamento semanal de preços dos combustíveis estratificada por munícipios. 
Ainda na figura 1, usamos a solução de armazenamento da Microsoft para cloud o Blob para armazenar as planilhas exportadas do site da ANP e para integração e transformação de dados usamos do serviço Data Factory. Após tratadas a tabela final foi carregada no Synapse Analytics. 

**4. Modelagem:**

A modelagem de dados abordada foi a Star Schema, que indica que uma estrutura de dados deve seguir uma tabela de FATOS rodeada por DIMENSÕES, dando um aspecto de uma estrela.

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/213bb061-2a23-49be-917b-f0d24d5dd375)

**5. Gerenciamento de segurança de dados:**

É o processo de coletar, armazenar, proteger e usar os dados de uma organização. 

Protege os dados contra ameaças internas e externas e garante a confiabilidade, integridade e disponibilidade dos dados.

Os dados escolhidos para este projeto são dados públicos e seguem as práticas de governança e segurança dos dados implementadas pelos órgãos federais competentes. A Governança de Dados da administração pública federal direta, autárquica e fundacional atualmente é regulamentada pelo Decreto nº 10.046, de 9 de outubro de 2019, o qual orienta sobre as ações de gerenciamento de dados sob as perspectivas do compartilhamento, da arquitetura, da segurança, da qualidade, da operação e de outros aspectos tecnológicos. 

Dentre as ações implementadas no âmbito da governança de dados está a Trilha de governança de dados. A Trilha de Governança de Dados tem por objetivo contribuir para a implementação da cultura de dados no âmbito do Poder Executivo Federal, a partir da legislação vigente e das diretrizes de privacidade, transparência, proteção de dados, criação de valor, ética, melhora da atuação estatal e eficiência, no uso dos dados em benefício do cidadão.

A trilha visa ainda orientar os órgãos para uma jornada que pretende alinhar infraestrutura, regulação, economia digital e pessoas aos valores sociais no uso de dados pelo governo, garantindo a proteção dos direitos individuais do cidadão.

O Fórum de Governança de Dados é um evento lançado pela Secretaria de Governo Digital em dezembro de 2022 com objetivo de criar uma rede na Administração Pública para troca de experiências e impulsionar o aculturamento em governança de dados do setor público. Especialmente entre os órgãos do Poder Executivo federal. O evento acontece mensalmente sempre com pautas sugeridas pelos participantes.

O Comitê Central de Governança de Dados (CCGD) foi instituído pelo Decreto 10.046, de 9 de outubro de 2019, com competências para deliberar, dentre outras, sobre as orientações e as diretrizes para a categorização de compartilhamento amplo, restrito e específico, e a forma e o meio de publicação dessa categorização, observada a legislação pertinente, referente à proteção de dados pessoais; e as orientações e as diretrizes para a integração dos órgãos e das entidades com o Cadastro Base do Cidadão.

**6. Metodologia:**

Foi criado na plataforma Azure um grupo de recursos com as ferramentas e serviços que serão utilizados no projeto. 

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/5b9eb89b-b36d-4624-8f01-ed07aa4f87aa) 
![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/a2106946-9db0-4af9-9c21-1518b3794578)

A base de dados definida está no formato CSV, extraída do site de Dados Abertos, foi importada para o Blob.

Para importar o arquivo para o Blob foi necessário a criação de um recurso através das storage accounts (contas de armazenamento).

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/2c7bdb87-7de7-452c-83c5-d4ce654a587d)

Após acessar a conta de armazenamento clique em +criar para fazer a criação.

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/eeed630f-e039-41af-8ab0-fb7d0a82a1e7)

Em seguida, acesse a conta de armazenamento criada e selecione a opção contêineres.

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/f78e5a66-919d-4d07-811c-cb38b9ec8d2e) 
![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/6a96b33b-a13c-4221-bef8-ae222009e0e4)

Foi criado então um novo contêiner com o nome dadosbrutos e, dentro dele, realizado o upload das tabelas que foram extraídas do site de Dados Abertos. 

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/8739888f-dc7e-4fc7-a726-bef68f41d888)

Em seguida no Data Factories foi criada uma nova pipeline com o nome ProjetoPUC.

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/5dcf7249-475d-496a-bf3e-e498abcfbb0c)

Em conjuntos de dados foi criado um fluxo de dados (dataflow) com o nome carregados. 

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/e30c3b4c-8ca8-404d-b296-2e2d26004aff)

Dentro desse fluxo de dados foram importadas as tabelas de dados que estavam armazenadas no Blob. 

E foi realizado o tratamento das tabelas onde foi feita a exclusão das colunas que não seriam necessarias para o projeto (5 ultimas coluna conforme mostra a figura abaixo) e também a união dos dados, transformando em uma única tabela chamada tabela final. 

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/6fac9d1d-f721-4643-b3d7-52502e890387)
![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/02cf3a95-2add-4b35-af9b-055dac53b974)

Essa tabela final foi alocada no Synapse Analytics com todos os dados já tratados para a próxima etapa do projeto.

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/1c040eb9-5b83-4d10-843d-f0a56d05977a)
![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/558a1524-d5eb-4d4e-a341-e3004610e574)

Além disso, acrescentamos uma tabela com a informação do preço do barril de petróleo na bolsa de valores de Nova Iorque.

Essa tabela foi retirada do site http://www.ipeadata.gov.br/Default.aspx para o enriquecimento do resultado final. 

Foi realizado o mesmo processo das tabelas anteriores: foi extraída do site em formato CSV, em sequência foi importada para o contêiner com o nome dadosbrutos no Blob.

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/bebcdcb4-8a0d-475f-a56c-10531eade352)

Em seguida no data factory, pipeline ProjetoPUC data flow, foi realizado o tratamento da tabela. Nesse tratamento, excluímos os dados entre 1987 a 2003 que não seriam utilizados para os fins desse projeto. 

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/ff76b789-f0af-4545-b645-74aa6b6cfba0)
![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/f4c6b228-f6f3-4e31-a2b2-920bd7c0925c)

As tabelas (TabelaFinal e tabelafinal2) foram alocadas no Synapse Analytics com todos os dados já tratados para etapa final de visualização.

# **7. Aprendizagem de Máquina**

Fontes utilizadas para criar os modelos:

Scikit-learn: https://scikit-learn.org/stable/ - Biblioteca de machine learning para Python

TensorFlow: https://www.tensorflow.org/ - Biblioteca de machine learning para Python e outras linguagens

Pandas: https://pandas.pydata.org/ - Biblioteca de análise de dados para Python


# Importar as bibliotecas necessárias
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# importar base de Dados 
Base_dados = pd.read_excel("/2018-a-2021_V2.1.xlsx")
Base_dados

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/86bcb8fc-b282-4d61-a0b0-2f6fec9e88e5)

# visualizar as 5 primeiras linhas 
Base_dados.head()

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/71df1450-820e-4ab4-96e1-2718759cb523)

# visualizar as 5 ultimas linhas 
Base_dados.tail()

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/6dc68a3d-582a-4c15-842b-43a98a7d6d1a)

#converter para um Array

Eixo_X = Base_dados.iloc[:,10].values
Eixo_y = Base_dados.iloc[:,11].values

#Visualizar eixo
Eixo_X

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/b972a7ec-b992-4d73-8f86-beb22e767f55)

#Visualizar eixo
Eixo_Y

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/68e7d200-e45f-40dd-a689-3f3f87fee970)

#Visualizar Grafico 

plt.figure(figsize=(7,3) )
plt.scatter(Eixo_X,Eixo_y);
plt.title("Minimo e Maximo do preço das revenda")
plt.xlabel("Minimo")
plt.ylabel("Maximo");

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/8bf7248b-b236-4c0b-bbe6-8289fbe593fe)

#visualizar correlações 
sns.pairplot(Base_dados);

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/a0866248-4b8b-4109-af57-ce9331604ff4)

plt.figure(figsize=(7,3) )
sns.heatmap(Correlacao, annot=True);

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/08e54a41-9f08-49ad-84b0-89c0c0d281b9)

Eixo_X = Eixo_X.reshape(-1,1)
Eixo_Y = Eixo_Y.reshape(-1,1)

#Importar biblioteca para treinamento 
from sklearn.linear_model import LinearRegression

Funcao_Regressao = LinearRegression()

Funcao_Regressao.fit(X_treinamento, Y_treinamento)

print(len(X_treinamento), len(X_teste))

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/9099d3ee-c16b-4aea-b683-23a4328f4a21)

# Verificação do resultado 
Funcao_Regressao.score(X_treinamento, Y_treinamento)

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/8d3593de-3702-4312-93db-816d83bd8fd9)

# visualização no grafico 
plt.figure(figsize=(10,5))
plt.scatter(X_treinamento, Y_treinamento)
plt.plot(X_teste,Funcao_Regressao.predict(X_teste),color="red");

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/5a603e04-da4c-4699-bcd3-f4e17663ea71)


# **7. Análise dos resultados**

Acurácia em cada partição: [0.9854943110501782 ] 

Acurácia média: 0.98 

A acurácia é a exatidão de uma solução mais a sua precisão

#PREVISÕES Erro médio da Regressão- Avalia a média que o modelo está errando 

Previsoes = Funcao_Regressao.predict(X_teste )

from sklearn import metrics
print('RMSE',np.sqrt( metrics.mean_squared_error(Y_teste,Previsoes)))

![image](https://github.com/RafaBBoaventura/Arquitetura_de_dados_em_nuvem_Grupo4/assets/131798428/2031e718-82b9-4691-8f74-27e2efe670c8)


Foi criada uma matriz de confusão, porém a não foi possível gerar o gráfico.

Erro nos valores do Y_Teste. 

# Matriz de confusão

Previsoes = Funcao_Regressao.predict(X_teste )

from sklearn.metrics import confusion_matrix
Matriz_Confusao = confusion_matrix(Y_teste, Previsoes)
print( Matriz_Confusao )

plt.figure( figsize=(10,5))
sns.heatmap( Matriz_Confusao, annot=True)

Para medir o percentual de assertividade realizado o comando abaixo, porém sem sucesso no resultado.
# percentual de assertividade do modelo 

from sklearn.metrics import classification_report

report = classification_report( Y_teste, Previsoes)
print(report)

Conclusão final: identificamos que apesar de nossa base de dados ser volumosa, os dados indicados nela não foram suficientes para obter uma correlação para uma previsão. Adquirimos outros dados onde consta o preço do barril, para enriquecer nossa base original, porém não foi possível unificá-las devido divergências de data/período.

Nosso grupo permanece buscando uma solução para conclusão desse projeto. 










