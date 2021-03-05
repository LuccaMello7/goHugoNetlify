# Análise sobre a Criminalidade e Violência no Estado do RJ

Desde os anos 70, o Estado do RJ passa por um problema gravíssimo: aumento da violência, péssimos indicadores sociais e também uma grande…

Desde os anos 70, o Estado do RJ passa por um problema gravíssimo: **aumento da violência**, péssimos indicadores sociais e também uma grande desigualdade territorial.

#### [Rio está entre as 10 metrópoles mais desiguais do mundo](https://g1.globo.com/rj/rio-de-janeiro/noticia/2020/07/13/rio-esta-entre-as-10-metropoles-mais-desiguais-do-mundo-diz-estudo-da-casa-fluminense.ghtml)

Isso se deve também ao fato de inúmeras gestões malsucedidas e enormes problemas de corrupção nos seus governos. Essas ações fizeram esses dados que já eram alarmantes, se acentuarem.

![](https://cdn-images-1.medium.com/max/800/1*yi-MFtvMqAwg02osOtGHdQ.jpeg)
undefined

### Obtendo os dados para a nossa análise

Para realizarmos essa análise da criminalidade do estado do Rio de Janeiro, vamos utilizar os dados fornecidos publicamente através do Portal ISPDados. No portal podemos acessar as bases de dados de registros criminais e de atividade policial no estado.

As estatísticas divulgadas no site são construídas a partir dos Registros de Ocorrência (RO) lavrados nas delegacias da Secretaria de Estado de Polícia Civil do Rio de Janeiro (SEPOL). Os Registros de Ocorrência são submetidos ao controle de qualidade realizados pela Corregedoria Geral de Polícia (CGPOL) da Secretaria de Estado de Polícia Civil, e após isso, são consolidados no ISP. Nessa análise, utilizaremos o dataset que pode ser baixado aqui: [Violência no Rio de Janeiro](https://raw.githubusercontent.com/carlosfab/dsnp2/master/datasets/violencia_rio.csv).

undefined
undefined

Uma vez que importamos os pacotes necessários para nossa análise, já podemos importar o nosso dataset.

undefined
undefined

Para checar a porcentagem de valores ausentes no dataset e fazer a importação dos mesmos em um gráfico podemos rodar os seguintes comandos:

undefined
undefined![](https://cdn-images-1.medium.com/max/800/1*aimVWYXMBwhgeL-Z6dHsOg.png)
undefined

E podemos visualizar os dados faltantes do nosso dataset no gráfico acima.

### Informações Estatística do Mapa da Violência no Rio de Janeiro

Abaixo colheremos alguns dados estatísticos que nos ajudarão a compreender o nosso conjunto de dados. Essas informações como media, mediana, valores máximo e mínimo vão nos fornecer ideias importantes para fazer a compreensão desse estudo.

Para que isso aconteça, vamos rodar o comando abaixo.

df.describe()

![](https://cdn-images-1.medium.com/max/800/1*Cz5Uo0H_6bbWIRgBkgPMiw.png)

Com os nossos dados já tratados e limpos — veja no link do projeto no [Github](https://github.com/LuccaMello7/AnaliseCriminalidadeEstadoDoRJ/blob/main/RioAnalysis.ipynb) — podemos destacar que:

*   A média de roubos de veículos é de: 2448.7
*   A média de furtos de veículos é de: 1674.67
*   A média de veículos que foram recuperados é de: 1772.24

![](https://cdn-images-1.medium.com/max/800/1*e2UlIAV1TmvB991kJi21xA.png)

Desde 1991, primeiro registro do nosso Dataset, podemos averiguar que o maior quantidade de roubos data de Abril de 2017, com o expressivo número de 23203 roubos. Assim como a maior quantidade de furtos data de Março de 2014, com 18003 furtos. Esses números alarmantes vão em frente também com as péssimas gestões dos governos de 1991 pra cá, duplicada nos anos 2000, como mostra o gráfico abaixo.

![](https://cdn-images-1.medium.com/max/800/1*3GlaBTCf22eKxFLpYhHZhA.png)
undefined

Um fato muito curioso que ronda o Palácio Guanabara é que:

*   **5 dos 7** Governadores do Estado do Rio de Janeiro desde 1982 **estão na mira da Justiça** — leia a matéria da exame [aqui](https://exame.com/brasil/5-dos-7-governadores-do-rio-desde-82-estao-na-mira-da-justica/). _Há dois governadores restantes estão mortos_ e não contabilizam para esses dados analisados pela Exame.
*   Todos os governadores eleitos do RJ nos últimos 20 anos foram presos, clique [aqui](https://noticias.r7.com/brasil/todos-os-governadores-eleitos-do-rj-nos-ultimos-20-anos-foram-presos-29112018)

**ps**: Não entrarei em detalhes sobre as graves suspeitas de corrupção para não alongar o texto.

Além de delegar a proteção aos cidadãos e com uma politica de flexibilização de acesso as armas por parte do Governo Federal, o Estado abdica da sua função de proteção e terceiriza essa ação para o cidadão comum.

Essas ações ou falta delas, desencadeadas (hoje) pelo Governo Federal e cascateada para outras esferas, ajuda a acentuar os crimes vistos nesse trabalho de pesquisa. Como já é de conhecimento de boa parcela da população a posse de armas está mais acessível com os decretos publicados pelo atual Presidente da República — e isso, não resolve os graves problemas de segurança pública, apenas se trata de uma ação unicamente populista por parte do expotente máximo do Executivo Brasileiro.

Para se ter ideia, conforme apurado pelo Instituto de Pesquisa Econômica Aplicada, **a difusão de armas de fogo aumenta para o número de homicídios** no país **e não possui efeito sobre a taxa de crimes contra a propriedade**. (Para ler o estudo, clique [aqui](https://www.ipea.gov.br/portal/index.php?option=com_content&view=article&id=17514&catid=8&Itemid=6)).

O estudo contrapõe o ato de que, segundo o Executivo, os números acima poderiam ser ainda menores no Território Nacional.

Veja também:

*   [Menos Armas, Menos Crimes — Instituto de Pesquisa Economica Aplicada](https://www.ipea.gov.br/portal/index.php?option=com_content&view=article&id=15101&catid=170)
*   [Decreto do porte de arma trasfere papel da segurança, argumenta OAB](https://www.campograndenews.com.br/brasil/cidades/decreto-do-porte-de-arma-transfere-papel-de-seguranca-argumenta-oab)
*   [OAB acredita que flexibilização de porte de armas vai aumentar criminalidade](https://br.sputniknews.com/opiniao/201512293189328-OAB-acredita-flexibilizacao-porte-armas-vai-aumentar-criminalidade/)

### Comparativo entre Roubos e Furtos do Estado do Rio de Janeiro

Abaixo vemos o gráfico relacionado a roubos no Estado do RJ e seus tipos de roubos mais recorrentes.

![](https://cdn-images-1.medium.com/max/800/1*BsIjSIs6SNFEKuHQzG6gUQ.png)
undefined

Dentre eles:

*   Roubo a Transeunte
*   Roubo a Veículos
*   Roubo de Celulares
*   Roubo a Comercio

Assim como o gráfico verde abaixo em relação a incidência de furtos e suas subdivisões:

![](https://cdn-images-1.medium.com/max/800/1*bwNyWl3NPG2GAV66mLLwoA.png)
undefined

Repare que ao cruzar os dados da totalidade de roubos e furtos podemos tirar as seguintes conclusões:

![](https://cdn-images-1.medium.com/max/800/1*uiSqMVVb0FQBsrtfL-fa-Q.png)
undefined

*   A época do ano que ocorre o maior numero de roubos é no final do verão — entre março e maio.
*   Em abril o numero de furtos passa a ser mais baixo, assim como no inicio do Inverno passa a ter a menor média do ano.
*   Durante o aniversário da capital do Estado do RJ — 1 de Março — , é onde ocorrem o maior pico de furtos e roubos.

### Correlação entre as variáveis

Abaixo vamos implementar e verificar o quanto uma variável impacta nos dados de outra variável.

Cada quadrado mostra a correlação entre as variáveis em cada eixo. A correlação `varia` de `-1 a 1`. Valores **mais próximos de zero** **significam que não há tendência linear entre as duas variávei**s.

Quanto mais próxima de 1 a correlação é, mais positivamente correlacionados eles são; isto é, à medida que um aumenta, o outro aumenta e **quanto mais próximo de 1, mais forte é a relação.**

Uma correlação mais próxima de -1 é semelhante, mas em vez de aumentar uma variável diminuirá à medida que a outra aumenta

undefined
undefined![](https://cdn-images-1.medium.com/max/800/1*8p-4SF5pY657aCrEEbp1zQ.png)

Sendo assim, plotaremos essa matriz em um gráfico de calor para que possamos visualizar ela de uma melhor forma, tomando conhecimento dos pontos levantados anteriormente sobre a definição de correlação.

![](https://cdn-images-1.medium.com/max/800/1*J-_EahxxHbk08u6EIKuOZQ.png)
undefined

Uma vez que plotamos o mapa de calor das correlações listadas acima, o que facilita o nosso entendimento de qual variável tem um impacto positivo ou negativo em outra variável.

Podemos analisar algumas curiosidades, tais como:

*   A variável de `roubo_cargas` tem uma forte relação com a variável de `posse_drogas`, sendo ela diretamente proporcional.
*   Assim como `hom_doloso` tem uma relação inversamente proporcional a: `apreensao_drogas`

Com o gráfico acima, deixo para você leitor encontrar mais relações diretas e indiretas que possam nos ajudar a entender ainda mais a Criminalidade no Rio de Janeiro.

Já com o gráfico abaixo, podemos verificar o gráfico de dispersão entre homicídio doloso e apreensão de drogas.

undefined
undefined![](https://cdn-images-1.medium.com/max/800/1*y8JGvpDWBCrJ3u-AuqnE-A.png)
undefined

### Conclusão

Identificamos que existe um grande crescimento no numero de roubos principalmente nos últimos 15 anos. Um contraponto esta no numero de furtos, que vem decaindo. O que nos leva a crer, de certa forma, que o modus-operandi vem mudando para uma forma mais abrupta — ainda que sejam crimes similares na sua essência.

Analisamos que os roubos que mais ocorrem hoje no Estado do Rio de Janeiro são:

*   Roubo a Transeunte
*   Roubo a Veículos
*   Roubo de Celulares
*   Roubo a Comercio

Assim como os furtos mais praticados pelos criminosos são os furtos de:

*   Furto de Veículos
*   Furto a Transeunte
*   Furto de Celulares
*   Furto em Coletivos

Caso queira dar uma olhadinha no projeto com mais dados e gráficos, fique a vontade, ele esta disponivel no seguinte link:

*   [Github](https://github.com/LuccaMello7/AnaliseCriminalidadeEstadoDoRJ/blob/main/RioAnalysis.ipynb)

Espero que esses dados possam ajudar outros analistas, estudantes e curiosos sobre o tema cruzando esses dados com outros dados que podem nos ajudar a mitigar a violência no Estado. Essa breve analise faz parte de uma continuação dos meus estudos com Data Science, e, portanto, será revisitada num futuro não tão distante para aprofundamento das técnicas e uma melhor visualização dos dados.

[**LuccaMello7 - Overview**  
_Support Engineer @SAP. LuccaMello7 has 19 repositories available. Follow their code on GitHub._github.com](https://github.com/LuccaMello7 "https://github.com/LuccaMello7")[](https://github.com/LuccaMello7)

By [Lucca Mello](https://medium.com/@lucca) on [March 2, 2021](https://medium.com/p/a594f60f1d85).

[Canonical link](https://medium.com/@lucca/an%C3%A1lise-sobre-a-criminalidade-e-viol%C3%AAncia-no-estado-do-rj-a594f60f1d85)

Exported from [Medium](https://medium.com) on March 5, 2021.