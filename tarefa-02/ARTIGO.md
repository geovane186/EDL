# Linguagem de Programação R

## Origens e Influências
<p>Foi criada originalmente por Ross Ihaka e Robert Gentleman (Depto Estatística da Universidade de Auckland, Nova Zelândia) no ano de 1993 com o intuito de auxiliar o ensino de estatística a seus alunos, pois na época a maioria dos softwares utilizados eram pagos.</p>
<p>Em relação a parte sintática se inspira no S , que foi desenvolvida pela Bell Labs, na década de 70 que também era uma linguagem de voltada para cálculos estatísticos. E para a parte de implementação e semântica foi inspirada no Scheme (Hal Abelson e Gerald Sussman) que suporta programação funcional e procedural.</p>
<p>Em junho de 1995 R foi disponibilizado como um software livre e em 1997.</p>


## Classificação
<p>R é uma linguagem funcional, orientada a objetos e dinâmica (linguagem de scripting).</p>
<p>Devido ao fato de ser uma lingugem estatistica onde a maioria dos usuários que disponibilizam códigos online, não são ligados a área de computação, R possui baixa (Readability). Porém, possui alta (Writability) e é considerada uma linguagem fácil de ser escrita. Em relação à processamento e visualização de dados, R proporciona muitas possibilidades com muito pouco a ser escrito.</p>


## Avaliação Comparativa
<p>Vamos comparar R com a linguagem Python que também é utilizada para análise de dados. As duas lingugens possuem facil apredizado, porém R possui uma série de pacotes que aumentam o nivel de funcionalidades da linguagem e o nivel de integração com outras linguagens. Em relação a expressividade, temos 2 exemplos de comparação entre as linguagens.</p>
<p>No primeiro exemplo temos em R a funcionalidade de realizar multiplos cálculos simultaneos com vetores, uma vez que, R é uma linguagem baseada em vetores. Você pode pensar em um vetor como uma linha ou coluna de números ou texto. A lista de números {1,2,3,4,5}, por exemplo, poderia ser um vetor. Ao contrário da maioria das outras linguagens de programação, o R permite aplicar funções ao vetor inteiro em uma única operação, sem a necessidade de um loop explícito. Em python seria necessario a escrita de uma função, onde estaria descrito o loop.</p>
<p>No segundo temos um exemplo de como funciona o for loop em R comparado ao for loop em python, podemos observar a partir dos exemplos, que python é mais rapido que R para um numero de iterações menor que 1000, porém a partir desse valor, R passa a ser superior a Python, devida a sua funcionalidade de realizar loop com valores maiores.</p>


## Exemplos de código representativos

**Vetores**

<p> R
   <pre><code>
> x <- 1:5
> x + 6:10
[1] 7 9 11 13 15

> x + 2
[1] 3 4 5 6 7
</pre></code>
 </p> 
 
<p> Python
<pre><code>
v = [1,2,3,4,5]

for x in v:
	x=x+2
	print(x)

</pre></code>
 </p> 
 
**For Loop**

<p> R
   <pre><code>
> library(magrittr)
> #number of the loop iterations
> n_elements <- 1e5
> #probe points
> x <- c(10,100,1000,5000,10000,25000,50000,75000,100000)
> #for loop
> t <- Sys.time()
> vec <- NULL
> elapsed <- NULL
> for (i in seq_len(n_elements))
> {
>     vec <- c(vec, sample(i, size = 1, replace = T))
>     if(i %in% x) 
>         elapsed <- c(elapsed, as.numeric(difftime(Sys.time(), t, 'secs')))
> }
> #lapply function
> t <- Sys.time()
> vec <- NULL
> elapsed_sapply <- lapply(seq_len(n_elements), function(i) {
>     vec <- c(vec, sample(i, size = 1, replace = T))
>     if(i %in% x) 
>         return(as.numeric(difftime(Sys.time(), t, 'secs')))
> }) %>% Filter(Negate(is.null), .) %>% unlist()
</pre></code>
 </p> 
 
 <p> Python
  <pre><code>
from numpy import random as rand
import datetime as dt

#number of the loop iterations
n_elements = int(1e5)
#probe points
x = [10,100,1000,5000,10000,25000,50000,75000,100000]

#for loop
t = dt.datetime.now()
vec = []
elapsed = []

for i in range(n_elements):
    vec.append(rand.choice(i+1, size=1, replace=True))
    if i+1 in x:
        elapsed.append((dt.datetime.now() - t).total_seconds())
</pre></code>
</p>

## Referência Bibliografica

[Algebra Matricial](https://rpubs.com/adelmofilho/AlgebraMatricial)

[Vetores R](https://rpubs.com/paternogbc/47469)

[Linguagem R](https://www.devmedia.com.br/trabalhando-com-a-linguagem-r/33275)

[Comparativo: R vs Python](https://imasters.com.br/back-end/comparativo-r-vs-python-para-data-science)