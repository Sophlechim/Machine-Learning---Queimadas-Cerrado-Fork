<h2 align="center"> RISCO DE FOGO: </h2>
<h3 align="center">  O USO DE MACHINE LEARNING PARA ANÁLISE DAS QUEIMADAS NO CERRADO BRASILEIRO </h3>
<p align="center"><img src="https://www.envolverde.com.br/wp-content/uploads/2012/09/Cerrado.jpg"></p>

## Descrição do Projeto
<p align="justify">
O presente projeto buscou desenvolver um modelo preditivo de risco de incêndio no Cerrado brasileiro. O alvo do nosso modelo é o risco de fogo e os atributos são variáveis da climatologia local (precipitação, dias sem chuva e localização geográfica) e a potência radiativa do fogo (<i>fire radiative power</i>, medida de energia radiante por unidade de tempo associada à taxa de queima da vegetação, dada em MW). Os dados coletados são do banco de dados abertos do <a href="https://queimadas.dgi.inpe.br/">Instituto Nacional de Pesquisas Espaciais</a>.
</p>
<p align="justify">
Este repositório tem como intuito demonstrar o processo metodológico utilizado para o desenvolvimento do modelo, que consistiu em (<b>a</b>) escolha do tema, (<b>b</b>) coleta, tratamento e análise de dados, (<b>c</b>) experimentação de algoritmos supervisionados e não-supervisionados e, por, fim, (<b>d</b>) avaliação e definição dos algoritmos mais representativos.</p>
<p align="justify">
O projeto foi elaborado pelas estudantes durante o segundo semestre de graduação da Ilum - Escola de Ciência, para a disciplina de Aprendizado de Máquina. O grupo é composto pelas estudantes: </p>
<p>:heavy_check_mark: Isabela Bento Beneti  </p>
<p> :heavy_check_mark: Monyque Karoline de Paula Silva </p>
<p> :heavy_check_mark: Sofia Baccega C.C. de Oliveira </p>
<p> :heavy_check_mark: Sophia Figueiredo Michel </p>
<p align="justify">
 
<details><summary><h3><b>Como se guiar no nosso GitHub?</h3></b></summary>
<p align="justify">
 É bem simples!  O código está em dividido em quatro arquivos de formato <i>ipynb</i> (<b>Bloco 1</b>, <b>2</b>, <b>3</b> e <b>4</b>), podendo ser aberto pelo jupyter notebook, vscode, g. colab ou em seu ambiente de desenvolvimento preferido.
</p>

<p align="justify"> Os arquivos zipados <b>Dados Mensais - 2021</b> e <b>2022</b> são os dados necessários para rodar o projeto; estão em formato <i>csv</i>, precisam ser extraídos e alocados na mesma pasta que o código.
</p>

<p align="justify">A explicação detalhada do que foi realizado em cada bloco pode ser encontrada em seu respectivo arquivo, enquanto seu papel para o desenvolvimento do modelo e procedimentos gerais estão descritos na aba <b>Bloco</b> deste documento.
</p>
</details>


## Possíveis problemas e suas soluções!
<p align="justify">
Ao longo do nosso projeto, nos deparamos com alguns problemas que foram complicados de resolver por motivos muito específicos e que causaram certa dor de cabeça. Por isso, para que você não passe pelos mesmos estresses, aqui estão algumas dicas de soluções para prováveis problemas que possam surgir.
</p>

<details><summary><b>Debugging</b></summary>
<p align="justify">
<h4>Arquivos:</h4> Para rodar o código em algum ambiente de desenvolvimento, cheque os procedimentos necessário para o uso de arquivos adicionais! Isso será necessário logo no início do código deste projeto, que é quando é carregado os dados usados pelo modelo.
</p>
<p align="justify"> Por exemplo: para o caso do <b>Jupyter Notebook</b> e do <b>VSCode</b>, é necessário salvar o arquivo do código (<i>ipynb</i>) na mesma pasta dos dados (<i>csv</i>). Para o caso do <b>Google Colab</b>, é necessário realizar o upload dos dados na aba de arquivos. Logo, esse procedimento pode variar, então é bom dar uma olhada na documentação do IDE escolhido!
</p>
</details>

<details><summary><b>Upgrade do threadpool</b></summary>
<p align="justify"> 
Se você está no Bloco 3 de dados não-supervisionado e ao  realizar o plot do cotovelo de qual cluster é o mais adequado para o agrupamento e por algum acaso, receber o seguinte erro:
</p>

<img src="https://user-images.githubusercontent.com/106678040/204189749-89f5a20d-cdc7-4341-85d3-a7860d043627.jpeg" width="600" height="50"/>

<p align="justify"> 
Não se preocupe! Este é um erro muito comum, se você está usando o KMeans no Sklearn! Isso pode ocorrer, pois o seu threadpoolctlde pode estar desatualizado, em muitos casos, eles se encontra na versão 2.2.0. Vamos ver como atualizá-lo? É só seguir o comando abaixo!
<img src="https://user-images.githubusercontent.com/106678040/204190495-5c518c37-5aa7-438d-bedd-15be85bc9d1f.jpeg" width="1200" height="150"/>
</p>
<p align="justify"> 

</details>

<details><summary><b>Dataset muito grande</b></summary>
<p align="justify">
É possível reparar que o dataset do projeto é realmente muito grande, ou seja, tem uma enorme quantidade de dados, o que pode causar problemas com o tempo de demora para certos códigos rodarem, como por exemplo: os modelos de "K-vizinhos mais próximos" e "Floresta Aleatória" e o código de "Validação Cruzada". Quando ainda estávamos com o dataset antigo, haviamos percebido como essas partes específicas demoravam tanto pra rodar e ao resolver trocar nossos dados e usar ainda mais do que antes, sabiamos que ia levar mais tempo ainda.
</p>
<p align="justify">
Para contornar esse problema e não gerar problemas de sobrecarga dos computadores, lembramos da possibilidade de utilizar o High- Performance Computing (HPC) da faculdade, o nosso Supercomputador, para reduzir o tempo que precisaríamos esperar com o computador ligado por várias horas até concluir todas as células de código. Portanto, recomendamos que conecte-se a uma rede de processamento de alto desempenho, a não ser que você queria ficar 11 horas com o computador ligado e rodando um código de validação cruzada :)
</p>
<p align="justify">
<b>No caso de alunos e professores da llum - Escola de Ciência</b> que estejam interessados em acessar e analisar nosso projeto, por favor acessem o nosso HPC Heisenberg. Para relembrar como entrar no Heisenberg, acessem o Guia da Apostila de Prática em Ciência de Dados na seção 9, que discorre sobre o processo de entrada no HPC. Não se esqueça que é necessário estar conectado a rede onde o Supercomputador se encontra e atua, não basta apenas se conectar ao VPN.
</p>
<p align="justify">
Outro ponto válido de ser ressaltado é que, quando você já estiver no link do Jupyter puro e com o arquivo do código aberto, lembre de instalar todas as bibliotecas necessárias que foram utilizadas no projeto.
</p>
</details>

## Processo Metodológico
<details><summary><b>Objeto de Análise</b></summary>
<p align="justify">
Durante a primeira aula, discutimos a respeito das áreas em comum que nos interessavam e percebemos que nossos interesses convergiam para as áreas ecológicas e sociais. Por isso, decidimos explorar um tema relacionado à área socioambiental.
</p>
<p align="justify">
A partir disso, procuramos quais temas socioambientais possuem dados o suficiente coletados, acessíveis e bem documentados. Analisamos algumas das fontes recomendadas pelos professores no guia do início da disciplina e nos interessamos pelo banco de dados do INPE. A partir disso, passamos a desenvolver a ideia de um projeto que relacionava as queimadas na vegetação brasileira com outros fatores, tais como precipitação e quantidades de dias sem chuva.
</p>
<p align="justify">
Por fim, decidimos que, a partir desse banco de dados e fatores analisados, desenvolveríamos um modelo preditivo de focos de incêndio.
</p>
</details>
<details><summary><b>Recortes</b></summary>
<p align="justify">
Uma das grandes discussões realisadas pelo nosso grupo foi sobre quais recortes utilizaríamos para elaborar o projeto. Acabamos por decidir o bioma Cerrado, que é o segundo bioma mais afetado por queimadas em todo o Brasil e sobre o qual há muitos dados disponíveis para estudo. A escolha do bioma se deu fortemente por pelo aumento de focos de incêndio na região. Além disso, não optamos pelo bioma da Amazônia devido o grande número de pesquisas dedicadas à região e a vontade de ressaltar outros biomas negligenciados pela mídia. 
</p>
</details>
<details><summary><b>Divisão de trabalho</b></summary>
<p align="justify">
A disciplina está organizada em 4 blocos progressivos para a construção de um modelo de aprendizado de máquina. Ao longo do primeiro bloco, decidimos que seria mais produtivo que cada uma das integrantes ficasse responsável por um dos tópicos da lista. Ao final, o trabalho foi realizado de maneira bem mais conjunta do que o previsto, já que nós ajudamos umas as outras durante o processo!
</p>
</details>

## Bloco 1
<p align="justify">
O primeiro bloco foi dedicado à decisão do tema do projeto e à busca de APIs para coleta dos dados necessários. Assim, nos familiarizamos com o processo de aquisição, armazenamento, tratamento e análise exploratória de dados.
</p>
<details><summary><b>Coleta de Dados</b></summary>
<p align="justify">
Durante as primeiras semanas, pesquisamos intensamente por bancos de dados e APIs pertinentes ao nosso modelo de previsão de queimadas no Cerrado. Priorizamos dados confiáveis, organizados e bem documentados, além de facilmente manipuláveis em python. Concluímos, por fim, após discussões com nossos professores, que os dados do INPE eram de fato os mais coerentes e também os mais completos para se trabalhar, contendo neles não apenas as coordenadas das queimadas, como também o risco de fogo e sua potência radiativa associada, o bioma ao qual aquela região pertence, a precipitação, o número de dias sem chuva, entre outros.
 <br>
Coletamos, então, todos os dados de queimadas do INPE desde janeiro de 2022 até julho de 2022. Esse conjunto de dados, para nossa surpresa, não incluía somente informações sobre o Brasil, mas sobre o mundo inteiro. Por isso, na tarefa seguinte (de preparação), foi essencial que filtrássemos os dados.
</p>
</details>
<details><summary><b>Preparação dos Dados</b></summary>
<p align="justify">
Identificamos que os dados do nosso conjunto eram todos do tipo float. Os dados foram normalizados para que ficassem na mesma escala. Em seguida, realizamos uma análise exploratória dos dados.
</p>
</details>
<details><summary><b>Análise Exploratória dos Dados</b></summary>
<p align="justify">
Após todo o processo de coleta, filtragem e tratamento dos dados, pudemos finalmente analisar tudo o que conseguimos obter através do nosso conjunto. Nossa hipótese era de que meses em que existe uma baixa taxa de precipitação e mais dias sem chuva apresentam maior probabilidade de focos de fogo na região. Assim, geramos matrizes de covariância e correlação para explorar e computar essa relação a partir de gráficos.
</p>
</details>

## Bloco 2
<p align="justify">
Neste bloco, aplicamos algoritmos de aprendizado supervisionado aos nossos dados com o objetivo de identificar qual poderia ser o mais adequado. Para analisar as divergências de cada técnica e o papel da normalização dos dados, desenvolvemos um notebook dividido em duas seções: uma para os dados normalizados e outra para os não-normalizados.
</p>
<details><summary><b>Treino, teste e baseline</b></summary>
<p align="justify">
No treinamento dos modelos, iniciamos com o modelo mais genérico e que servirá de referência de desempenho aos demais: o modelo <i>baseline</i>! Esse modelo realiza uma média dos valores da target e, geralmente, não apresenta uma boa taxa de acerto. Utilizamos o RMSE como métrica e obtivemos um valor aproximado de 0.22 de erro de predição.
</p>
</details>
<details><summary><b>Treinamento de modelo de <i>k</i> vizinhos mais próximos</b></summary>
<p align="justify">
Dada a parametrização inicial com RMSE de 0.22, o objetivo das discentes passou a encontrar um modelo cuja o RMSE fosse menor e se possível, mais próximo de zero. Deste modo, surge o k-nn vizinhos como um modelo cujo a hipótese consiste na ideia de que a similaridade dos dados é condizente com as regiões próximas no espaço de entrada. Os k determinam a quantidade de vizinhos que serão analisados na região, este modelo apresentou um RMSE próximo a zero e observou-se que conforme for menor o número de k menor será o RMSE.
</p>
</details>
<details><summary><b>Regressão linear</b></summary>
<p align="justify">
O modelo de regressão linear não obteve uma boa métrica, chegando a 0.20. Este modelo tem como objetivo relacionar linearmente as nossas features e o nosso target, logo, este resultado demonstra que a relação entre as features e o target não estão linearmente relacionadas o que corrabora com a proposta de features de climatologia do nosso modelo, visto que o clima não é uma concepção linear.
</p>
</details>
<details><summary><b>Árvore de decisão</b></summary>
<p align="justify">
Seguindo a série de treinamentos de modelos, introduzimos o algoritmo de árvore de decisão para descobrir a performance desse modelo e compará-la em relação aos outros modelos, podendo observar que é melhor que os modelos anteriormente treinados. Definidos hiperparâmetros para a árvore para reduzir 'overfittings' criados a partir das diferenças entre os dados treinados e não treinados, foi possível perceber que tanto o número de 'nodes' quanto a profundidade da nossa árvore afetam na complexidade e performance do nosso modelo. Ao alterá-los, com a intenção de evitar ajustes excessivos, pode-se concluir que o comportamento do erro quadrático médio não possui grande variação conforme definimos diferentes valores de hiperparâmetro de curtos intervalos de diferença.
</p>
</details>
<details><summary><b>Floresta aleatória</b></summary>
<p align="justify">
Este modelo pode ser compreendido como uma complementaridade ao modelo de Árvore de Decisões. Ok! Mas em que sentido? As árvores de decisões podem apresentar modelos simples e explicativos, mas possuem a desvantagem de nem sempre apresentarem uma boa perfomance, logo, de modo a melhorar essa performance, usufrui-se da Floresta Aleatória cujo o objetivo é o de desenvolver um comitê que contenha diversas árvores de decisão onde cada uma realiza sua previsão individual, cada previsão individual pode ser considerada como um voto e ao ser relacionada com outros votos, possibilita-se a determinação de uma resposta final. O RMSE apresentou resultados próximos a zero e se mostrou eficaz.
</p>
</details>
<details><summary><b>Comparando os desempenhos dos modelos de regressão</b></summary>
</p>
<p align="justify">
Para comparar os cinco modelos preditivos desenvolvidos, comparamos os valores de RMSE e de precisão, a fim de determinar qual deles possuia o melhor desempenho. Para tanto, nós colocamos esses valores em uma tabela, e obtemos o seguinte resultado: 
</p>

| Modelo | Normalizado | Não Normalizado |
| :---       |     :---:      |   ---:        |
| Baseline   | 0.22437296     | 0.22436829    |
| 1 K-NN     | 0.08327995     | 0.08534422    |
| 2 K-NN     | 0.08421390     | 0.08509752    |
| 3 K-NN     | 0.08740112     | 0.08732847    |
| 4 K-NN     | 0.09072226     | 0.08951491    |
| 5 K-NN     | 0.09320795     | 0.09162095    |
| 6 K-NN     | 0.09536342     | 0.09331903    |
| 7 K-NN     | 0.09736359     | 0.09484598    |
| 8 K-NN     | 0.09917756     | 0.09610478    |
| Regressão  | 0.20094583     | 0.20094583    |
| Árvore     | 0.07898324     | 0.07870004    |
| Floresta   | 0.06039642     | 0.06040035    |
</p>
Podemos perceber, pois, que tanto para o s dados normalizados quanto para os dados não normalizados, os melhores modelos preditivos (isto é, os que resultam em melhor previsão) são os de FLoresta aleatória e o de K-NN. 
</p>
Direcionando nosso olhar para o K-NN, podemos perceber, também, que os melhores resultados desse modelo são obtidos com menores números de vizinhos selecionados.
<\p>
Isso ocorre pois, no caso dos nossos dados, quando realizamos o modelo K-NN com uma grande quantidade de vizinhos, nós estamos nos "afastando" muito da área que está sendo utilizada para predição, o que torna as previsões menos precisas.
<\p>
O gráfico presente no notebook "Bloco 2" mostra exatamente como o erro desse modelo cresce conforme aumentamos o número de vizinhos analisados:
</P>
<p align="center">
<img width="574" alt="ERRO" src="https://user-images.githubusercontent.com/106626661/192491037-3d8cb660-27f1-4189-8447-d7a3126b8a17.png">
</details>
<details><summary><b>Classificação</b></summary>
O metódo de classificação utilizado foi o K-NN. Em um primeiro momento, necessita-se de dados categóricos, por isso, desenvlve-se uma coluna de classificação categória sobre as chances do risco de fogo. Após esta criação, aplica-se o metódo de classificação e análisa sua accuracy.  
</details>
<details><summary><b>Bloco 2 - Teste.ipynb</b></summary>
<p align="justify">
Esse arquivo presente nosso repositório não faz parte da lista de tarefas oficial do Bloco 2, mas foi necessário para estudarmos o comportamento dos dados de maneira gráfica com a utilização de uma 'target' diferente da original, uma vez que os gráficos plotados de Modelo de Previsão X Modelo Real estavam muito estranhos e ruins. Foi escolhida, dentre as possíveis no nosso Dataframe, uma menos complexa e, supostamente, mais fácil de prever, sendo essa, então, a Precipitação.
</p>
<p align="justify">
Sendo assim, separadamente, os modelos propostos no trabalho foram reproduzidos para essa nova target. Ao plotar todos os gráficos, realmente os modelos estão ruins, comom possível ver no arquivo. Surgimos assim, com algumas hipóteses sobre o que pode ter acontecido, podendo ser, inclusive, uma união de fatores:
</p>
<ol>
<h5>
<li>O primeiro ponto que pensamos, foi a pouca quantidade de features que coletamos, podendo influenciar fortemente nos resultados dos modelos, uma vez que não temos informações básicas como temperatura, umidade do ar e do solo e até o uso de solo;</li>
<li>Em segundo, a falta de especificação e diferenciação de dados numéricos em casas decimais pode ter causado essas linhas verticais de distâncias iguais em determinados valores de <i>x</i> com diversos pontos sobrepostos, de forma que o modelo compreendou que existem muitos valores de <i>y</i> de um mesmo fator para um único <i>x</i>;</li>
<li>Por fim, a falta de normalização de dados (que foi sugerida) em metade do código, em Bloco 2.ipynb, uma vez que os gráficos do modelo de Floresta Aleatória para dados normalizados está muito melhor que o gráfico dos dados não-normalizados.</li>
</h5>
</ol>
</details>

## Bloco 3
<p align="justify">
Neste bloco, trabalhamos com modelos de aprendizagem não-supervisionados. A aprendizagem não supervisionada consiste em identificar padrões nos dados não tabelados e agrupá-los com base nas similaridades e diferenças de valores. As principais tarefas associadas a esse método são agrupamento, associação e redução de dimensionalidade.
</p>

<details><summary><b> Redução de dimensionalidade </b></summary>
<p align="justify">
Iniciamos com o algoritmo de Análise de Componentes Principais (PCA), que reduz a dimensionalidade do conjunto de dados enquanto mantém o máximo de informações possível. O cada eixo resultante dessa análise é um vetor corresponde ao grau de variância dos dados em ordem crescente. Em nosso caso, a PC1 apresentou destaque em relação às outras e observamos que podemos selecionar até três princpais componentes para explicar a variância do nosso dataset. Dessa forma, a aplicação do PCA ajuda a evitar o overfitting do modelo.
</p>
</details>

<details><summary><b> Agrupamento (clustering) </b></summary>
<p align="justify"> O algoritmo de clustering é eficiente para exploração e análise de dados crus e não tabelados, pois agrupa os dados de acordo com suas similidades e diferenças, demonstrando assim o comportamento das diferentes atributos do dataset. Para isso, definimos os atributos e o número de clusters (avaliamos a quantidade adequada de clusters de acordo com a "curva do cotovelo") e plotamos para visualizar a relação entre os valores. 
</p>
</details>

<details><summary><b> Detecção de outliers </b></summary>
<p align="justify">
É um método de detecção de valores anômalos (outliers) com base na avaliação dos valores de cada ponto de dados em relação aos valores dos dados vizinhos mais próximos. Definimos hiperparâmetros para indicar quantos vizinhos devem ser levados em consideração e plotamos a dispersão dos mesmos.
</p>
</details>

## Bloco 4
<p align="justify">
Nesse último Bloco do projeto, tivemos como último aprendizado a utilização de estratégias para encontrar os melhores hiperparâmetros pra o nosso modelo de aprendizado de máquina. Sendo essa a reta final do projeto, o nosso maior foco foi preparar o código final e oficial, que ficará disponível para acesso neste repositório, além da realização de discussões importantíssimas para o planejamento da apresentação do projeto de conclusão do segundo semestre. 
</p>
<details><summary><b> Validação Cruzada </b></summary>
<p align="justify">
O método de validação cruzada é uma ferramenta que nos ajuda a encontrar hiperparâmetros razoáveis para o modelo. Com ela, é possível avaliar o ajuste do algoritmo ao modelo e previnir o sobreajuste (<i>overfitting</i>) - que hipergeneraliza os pontos conhecidos a ponto de comprometer a validade do acerto dos pontos de teste - e o subajuste (<i>underfitting</i>) - que pode não ser capaz de identificar sequer a relação entre os valores de entrada e de saída dos pontos de treinamento -. Dentre os tipos de validação cruzada, o mecanismo geral é basicamente o mesmo: o conjunto é dividido em <i>k</i> partes rotuladas, aleatórias e mutuamente exclusivas e essas partes são, então, utilizadas alternadamente entre treino, teste e validação. Em nosso notebook, realizamos validação k-fold e a de floresta aleatória. </p>
<p align="justify">
No total, utilizando apenas esses dois tipos de validação, realizamos 10 validações cruzadas, alternando o número de hiperparâmetros. Consideramos que melhor resultado obtido entre as validações da floresta aleatória foi o com 100 árvores e 4 CPU cores. Como visto nos blocos anteriores, nosso melhor resultado do modelo k-NN foi com o menor número possível de vizinhos, ou seja, apenas 1 vizinho. Isso se deve ao modo como nossos dados se comportam: é melhor relacionar os dados mais próximos para tentar predizer qual o risco de fogo de determinado locas. Esse fato explica o por quê do melhor pipeline ter sido o com NUM_VIZINHOS= 1
</p>
</details>


