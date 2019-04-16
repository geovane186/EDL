# Linguagem de Programação R

## Origens e Influências
<p>Foi criada originalmente por Ross Ihaka e Robert Gentleman (Depto Estatística da Universidade de Auckland, Nova Zelândia) no ano de 1993 com o intuito de auxiliar o ensino de estatística a seus alunos, pois na época a maioria dos softwares utilizados eram pagos.</p>
<p>Em relação a parte sintática se inspira no S , que foi desenvolvida pela Bell Labs, na década de 70 que também era uma linguagem de voltada para cálculos estatísticos. E para a parte de implementação e semântica foi inspirada no Scheme (Hal Abelson e Gerald Sussman) que suporta programação funcional e procedural.</p>
<p>Em junho de 1995 R foi disponibilizado como um software livre e em 1997.</p>


## Classificação
<p>R é uma linguagem funcional, orientada a objetos e dinâmica (linguagem de scripting).</p>
<p>Devido ao fato de ser uma lingugem estatistica onde a maioria dos usuários que disponibilizam códigos online, não são ligados a área de computação, R possui baixa (Readability). Porém, possui alta (Writability) e é considerada uma linguagem fácil de ser escrita. Em relação à processamento e visualização de dados, R proporciona muitas possibilidades com muito pouco a ser escrito.</p>


## Avaliação Comparativa
<p>Vamos comparar R com a linguagem Python que também é utilizada para análise de dados.As duas lingugens possuem facil apredizado, porém R possui uma série de pacotes que aumentam o nivel de funcionalidades da linguagem e o nivel de integração com outras linguagens. Em relação a expressividade, R é mais expressiva que Python.</p>


## Exemplos de código representativos

**Multiplicação Matricial**

<p> R
   <pre><code>
> M1 = matrix(data = 1:9, nrow = 3, ncol = 3)
> M2 = matrix(data = 1:9, nrow = 3, ncol = 3)
> 
> M3 = M1 %*% M2
> 
> print(M_prod)
</pre></code>
 </p> 
 
<p> Python
<pre><code>
def MultiplicaMatrix(m1, m2):
  ﻿  sizeLA = len(m1)
    sizeCA = len(m1[0])
    sizeCB = len(m2[0])
    m3 = []
    for i in range(sizeLA):
        m3.append([])
        for j in range(sizeCB):
            val = 0
            for k in range(sizeCA):
                    va﻿l += m1[i][k]*matrizB[k][j]
            m3[i].append(val)
    return m3﻿  
</pre></code>
 </p> 
 
**Redução de elementos duplicados em vetores** =>

<p> R
   <pre><code>
> vetor<-c(1,2,1,2)
> vetor<-unique(vetor)
</pre></code>
 </p> 
 
 <p> Python
  <pre><code>
def RemoveDuplicados(vet):
    vet2 = []
    # removendo duplicados
    for x in vet:
        if x not in vet2:
            vet2.append(x)
			
    return vet2
</pre></code>
</p>

## Referência Bibliografica

[Algebra Matricial](https://rpubs.com/adelmofilho/AlgebraMatricial)

[Vetores R](https://rpubs.com/paternogbc/47469)

[Linguagem R](https://www.devmedia.com.br/trabalhando-com-a-linguagem-r/33275)