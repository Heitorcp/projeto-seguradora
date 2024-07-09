# Tendências e Padrões na Compra de Seguros de Veículos 

### Projeto final da disciplina SME0878 - Mineração Estatística de Dados - ICMC USP

## Introdução 

A indústria de seguros automotivos desempenha um papel crucial na proteção financeira e segurança dos proprietários de veículos, oferecendo cobertura contra uma variedade de riscos, desde acidentes de trânsito até danos causados por eventos naturais. Compreender os padrões e tendências relacionados à compra de seguros de veículos é fundamental para as companhias de seguros, permitindo-lhes adaptar suas estratégias de precificação, marketing e gestão de riscos.

Este relatório apresenta uma análise detalhada da compra de seguros de veículos com base no conjunto de dados disponibilizado. O objetivo principal é investigar os principais fatores que influenciam as decisões de compra de seguros automotivos pelos consumidores. Para alcançar esse objetivo, exploramos uma variedade de variáveis relacionadas ao perfil do comprador.

Ao longo deste relatório, utilizamos técnicas de análise de dados estatísticos e visualização para identificar correlações, tendências e insights significativos que podem orientar as estratégias de negócios das seguradoras. Visamos ainda a análise de diferentes modelos de regressão binária e classificação a fim de definir aquele que melhor se ajusta aos dados apresentados.

A compreensão aprofundada dos padrões de compra de seguros de veículos não apenas beneficia as companhias de seguros na otimização de seus produtos e serviços, mas também fornece informações valiosas aos consumidores, permitindo-lhes tomar decisões mais informadas sobre suas necessidades de proteção veicular. 

## Análise Exploratória

A partir das análises exploratórias, pudemos identificar características de interesse no conjunto de dados. Visando o interesse da companhias de seguros, notamos que o segmento de cliente que apresenta a maior conversão de compras do seguro completo é o de mulheres no ambiente urbano. Além disso, as campanhas da empresa devem considerar que a idade é a variável com maior desvio-padrão, indicando a necessidade de segmentação para atingir todas as faixas etárias de maneira eficiente. Deve ser considerando ainda que os clientes são em sua grande maioria proprietários dos veículos. Por fim, considerando que a maior parte dos clientes nesses conjunto de dados são homens ($75.25\%$), é de proveito da companhia de seguros a elaboração de planos de ação que visem aumentar a proporção de compras de seguro completo dentro desse segmento.

## Agrupamentos

As técnicas de agrupamento indicaram que as variáveis $MEN$, $URBAN$ e $SENIORITY$ são as principais responsáveis pela divisão dos grupos.

Os grupos em que houve o maior acionamento dos seguros, como por exemplo na divisão pelo DBScan foram os grupos formados por mulheres que trafegam tanto em ambiente rural quanto urbano, com uma idade média de 42 anos e uma senioridade média de 9 anos.

Adicionamos ainda um algoritmo que utiliza predição conformal para detectar observações que se distânciam das classes apresentadas. Esse tipo de método pode oferecer uma maior segurança às predições feitas uma vez que permite separar essas observações atípicas para uma análise mais minuciosa.

## Modelagem

Iniciamos o processo de modelagem e, nossos ajustes refletem os indicativos observados nos agrupamentos.

Ou seja, os coeficientes de regressão tendem a apresentar maiores valores para os níveis, Mulher; trafegar em ambiente urbano e ter uma maior senioridade.
Desse modo, ao menos a partir do modelo logístico ajustado, sabemos que mulheres que trafegam em ambiente urbano e possuem uma maior senioridade, tem maiores chances de pertaencerem à classe positiva.

Também ajustamos um modelo baseado em árvore que apresentou um desempenho, semelhante, mas um pouco inferior à regressão logística clássica. Apresentamos também técnicas de Boosting.

O limiar de classificação para o modelo logístico que corresponde ao ponto de máximo da nossa curva ROC, foi de 0.29. Nós, sabemos que esse pode ser um limiar bem baixo, a depender do contexto do negócio.

Dito isso, enfatizamos que o processo de Ciência de Dados deve se iniciar e terminar sempre a apartir da definição do objetivo do negócio/análise buscando sempre entender o contexto presente. De acordo com o custo de um FN, por exemplo, o limiar pode ser ajustado de modo a favorecer mais a sensibilidade, especificidade ou a precisão do modelo.

Por fim, recomendaríamos o uso do modelo de Regressão Logística, como modelo final para classificação dos clientes mais propensos à ativação do seguro completo. Em relação ao balanceamento, dado que não estamos em um cenário de produção e dada as baixas diferenças entre o modelo usual e sua versão balanceada, não podemos assegurar a superioridade do modelo balanceado.

## Sugestões para a continuação da análise

Possíveis abordagens para a continuação deste trabalho seriam ajustar outras famílias de modelos bayesianos visando avaliar o impacto da incorporação de informação à priori nos modelos criados.