# Linguagem de Programação R

## Origens e Influências
<p>Foi criada originalmente por Ross Ihaka e Robert Gentleman (Depto Estatística da Universidade de Auckland, Nova Zelândia) no ano de 1993 com o intuito de auxiliar o ensino de estatística a seus alunos, pois na época a maioria dos softwares utilizados eram pagos.</p>
<p>Em relação a parte sintática se inspira no S , que foi desenvolvida pela Bell Labs, na década de 70 que também era uma linguagem de voltada para cálculos estatísticos. E para a parte de implementação e semântica foi inspirada no Scheme (Hal Abelson e Gerald Sussman) que suporta programação funcional e procedural.</p>
<p>Em junho de 1995 R foi disponibilizado como um software livre e em 1997.</p>


## Classificação
<p>R é uma linguagem funcional, orientada a objetos e dinâmica (linguagem de scripting).</p>
<p>Devido ao fato de ser uma lingugem estatistica onde a maioria dos usuários que disponibilizam códigos online, não são ligados a área de computação, R possui baixa (Readability). Porém, possui alta (Writability) e é considerada uma linguagem fácil de ser escrita. Em relação à processamento e visualização de dados, R proporciona muitas possibilidades com muito pouco a ser escrito.</p>


## Avaliação Comparativa
<p>Vamos comparar R com a linguagem Python que também é utilizada para análise de dados.As duas lingugens possuem facil apredizado, porém R possui uma série de pacotes que aumentam o nivel de funcionalidades da linguagem e o nivel de integração com outras linguagens. Em relação a expressividade, temos 2 exemplos de comparação entre as linguagens.</p>
<p>No primeiro temos um exemplo da aplicação do algoritmo K-Means, usado para clusterização, para utiliza-lo é preciso verificar e limpar a existencia de valores não numéricos , em R é testado em cada iteração de coluna, em seguida aplicamos o algoritmo, mas em python os métodos get_numeric_data e dropna são usados para remorer os dados não-numéricos, e em seguida aplicamos o algoritmo.</p>
<p>No segundo temos um exemplo de calculo de média, onde podemos observar que em R o retorno para colunas onde temos strings ao invés de números é NA (Not Available). Porém em Python é ignorado por default operações de média para grupos de valores não-numéricos, portanto vemos que R é mais formal no tratamento estatístico e retorna a indisponibilidade do cálculo de forma explícita.</p>


## Exemplos de código representativos

**K-Means: Algoritmo Clusterização**

<p> R
   <pre><code>
> planilha <- read.csv("planilha.csv")
> library(cluster)
> set.seed(1)
> dadoUtil <- function(col){
>    sum(is.na(col)) == 0 && is.numeric(col) 
> }
> dadosUTeis <- sapply(planilha, dadoUtil)
> clusters <- kmeans(planilha[,dadosUteis], centers=5)
> labels <- clusters$cluster
</pre></code>
 </p> 
 
<p> Python
<pre><code>
import pandas

planilha = pandas.read_csv("planilha.csv")

from sklearn.cluster import KMeans

kmeans_model = KMeans(n_clusters=5, random_state=1)

dadosUTeis = planilha._get_numeric_data().dropna(axis=1)

kmeans_model.fit(dadosUTeis)

labels = kmeans_model.labels_
</pre></code>
 </p> 
 
**Calculo de Média**

<p> R
   <pre><code>
> planilha <- read.csv("planilha.csv")
> sapply(planilha, mean, na.rm=TRUE)
</pre></code>
 </p> 
 
 <p> Python
  <pre><code>
import pandas

planilha = pandas.read_csv("planilha.csv")
planilha.mean()
</pre></code>
</p>

## Referência Bibliografica

[Algebra Matricial](https://rpubs.com/adelmofilho/AlgebraMatricial)

[Vetores R](https://rpubs.com/paternogbc/47469)

[Linguagem R](https://www.devmedia.com.br/trabalhando-com-a-linguagem-r/33275)

[Comparativo: R vs Python](https://imasters.com.br/back-end/comparativo-r-vs-python-para-data-science)