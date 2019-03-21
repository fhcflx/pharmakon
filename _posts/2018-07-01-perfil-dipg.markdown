---
layout: post
title: Perfil dos sobreviventes de tumores difusos de tronco cerebral
date: '2018-07-01T22:03:00.000-03:00'
author: Francisco H C Felix
lang: pt-br
ref: dipg
tags:
- DIPG
- Sobreviventes
---

Os tumores difusos de tronco cerebral são conhecidos pela sigla em inglês DIPG
(_diffuse intrinsic pontine glioma_) e, desde 2016, podem ser clasificados como _gliomas difusos de linha média H3K27M+_ (através de patologia{% include histologia.html %} de biópsia cirúrgica). Independente da nomenclatura, trata-se do glioma{% include glioma.html %} maligno mais frequente da pediatria e também o câncer{% include cancer.html %} cerebral de crianças e adolescentes que mais mata.
<!--more-->

Um estudo da _Société Internationale d’Oncologie Pédiatrique_(SIOP), publicado
no _Journal of Clinical Oncology_, mostrou o perfil de crianças e adolescentes
que sobreviveram ao DIPG.

Para isso, os pesquisadores avaliaram 1130 casos de DIPG confirmado radiologicamente, tratados na Europa e nos EUA. Deste total de pacientes, 122 casos foram excluídos do estudo. do restante (1008 casos), 101 (10%) sobreviveram mais do que 2 anos (sobreviventes de longo prazo).

A sobrevida do grupo todo foi de 43% em 1 ano após o diagnóstico, 9,6% em 2 anos
e 2,2% em 5 anos. Os sobreviventes de longo prazo tinham, mais frequentemente,
ou menos que 3 anos ou mais que 10 anos, além de duração de sintomas mais longa.
Por outro lado, os pacientes com menor sobrevida tinham mais paresia de pares cranianos, captação anelada de contraste, necrose e extensão extrapontina.

Os sobreviventes de longo prazo receberam quimioterapia{% include quimio.html %} com mais frequência e apresentavam a mutação do gene HIST1H3B.

Esses achados se aproximam do modelo preditivo de sobrevida do DIPG proposto em 2015 por Jansen _et al_. Os autores do modelo examinaram um grupo de 316 pacientes com DIPG tratados na Holanda e fizeram um estudo estatístico definindo fatores de prognóstico que influenciaram a sobrevida dos pacientes. Os fatores que mostraram significância estatística na sua análise (veja tabela abaixo) foram incluídos no modelo final.

Em um trabalho posterior (Veldhuijzen van Zanten _et al_, 2017), o mesmo grupo publicou um estudo de validação desse modelo analisando um grupo independente de 249 pacientes com DIPG. Nesse caso, eles não conseguiram reproduzir os mesmos resultados do trabalho anterior e a validação do modelo falhou em mostrar a significância estatística dos mesmos fatores preditivos usados.
<br/><br/>

| Fator modelo preditivo | HR (IC 95%) | Trabalho SIOP - OR (IC 95%) |
| --- | --- | ---:|
| Idade > 3 anos | 1,95 (1,01 - 3,8) | 3,98 (2,46 - 6,46) |
| Duração dos sintomas | 0,92 (0,86 - 0,97) | |
| Captação anelada | 1,41 (1,07 - 1,84) | 2,07 (1,28 - 3,36) |
| Quimioterapia | 0,65 (0,49 - 0,99) | 0,40 (0,22 - 0,75) |

_Tabela: fatores preditivos do modelo de Jansen (2015), com a razão de riscos (**hazard ratio**_{% include hr.html %} _**- HR**) e seu intercalo de confiança_{% include ic.html %} _95%. Razão de possibilidades (**odds ratio**_{% include or.html %} _**- OR**) calculada a partir dos dados publicados no trabalho da SIOP._

Afinal, estes fatores são importantes ou não para classificar os pacientes com DIPG e prever seu risco? Essa resposta é complicada pelo fato de que a metodologia do trabalho do SIOP foi diferente da metodologia usada para definir o modelo preditivo de Jansen. Mesmo assim, chama a atenção a semelhança entre os fatores. Analisar a importância disto requer um pouco de senso crítico.

Em primeiro lugar, os fatores avaliados no trabalho da SIOP não foram escolhidos casualmente, nem foram selecionados aleatoriamente entre muitos outros. Os autores desta avaliação da SIOP usaram estes fatores _porque outros trabalhos anteriores, incluindo o modelo de Jansen, tinham mostrado sua possível importância._ Ou seja, a escolha dos fatores foi dirigida e a semelhança entre os fatores encontrados nos diferentes trabalhos não é coincidência.

Além disso, um dos parâmetros mais importantes a ser avaliado quando se analisa fatores de prognóstico (e uma das coisas mais negligenciadas) é o _intervalo de confiança_. Do que se trata isso? Bom, de forma direta, quando se fala em _intervalo de confiança 95%_ (IC95) entende-se que se fizermos um número _n_ de amostragens aleatórias na população que estamos estudando, 95% das médias devem ficar dentro do IC95. Nesse caso particular, isso significa que, se repetíssemos a mesma investigação em 100 grupos diferentes de pacientes, a média de 95 destas repetições deveria ficar dentro do IC95 que calculamos. Na estatística, isso é um dos pontos mais próximos da verdade que podemos chegar.

Bem, então vamos ver os IC95 dos fatores avaliados no modelo de Jansen e no trabalho da SIOP. No modelo de Jansen, a idade maior que 3 anos correlacionou-se com um aumento da _razão de risco (HR)_. Como o valor de HR foi de quase 2, podemos dizer que _o risco de falecer era quase o dobro em crianças maiores de 3 anos, em comparação com menores_. Mas observe o IC95, ele varia de 1,01 a 3,8. No caso de um HR igual a 1,01 (que, pela definição do IC95, poderíamos encontrar numa repetição aleatória do estudo), o aumento de risco em maiores de 3 anos seria de apenas 1%!

O que podemos entender disso? Que, mesmo que a _idade maior que 3 anos_ tenha sido classificada como fator preditivo no modelo de Jansen, _isso não nos dá muita certeza_ de um efeito grande! Um por cento de risco não parece grande coisa, e nesse caso não é, realmente. Quando os IC95 de _medidas de efeito_ (como o HR ou o OR) são muito amplos, isso indica uma falta de certeza no tamanho desse efeito. Se observarmos os IC95 dos HR do modelo de Jansen, todos são bem amplos, o que indica que o tamanho dos efeitos medidos pode ser muito variável e inclusive ser muito pequeno.

Isso pode ser explicado de várias maneiras. A primeira coisa a se pensar é se a metodologia do trabalho foi adequada. Quando se trata de medidas de efeito, é muito importante saber se o estudo teve _poder estatístico_{% include pe.html %} para detectar o efeito desejado. Esse poder estatístico é calculado de antemão, quando se planeja um estudo. Infelizmente, por descuido, muitos trabalhos acabam sendo realizados com _baixo poder estatístico_. Isso poderia explicar a falta de certeza no tamanho do efeito e o IC95 muito grande. Para consertar isso, somente repetindo o estudo, dessa vez com um _poder estatístico_ adequado.

O estudo do modelo de Jansen foi feito com poder estatístico suficiente? Os autores do trabalho não informam o poder estatístico das análises realizadas e isso exige cálculos que fogem ao assunto deste texto. A falta deste tipo de informação é muito frequente e nos leva a indagar se uma das limitações do modelo de Jansen não teria sido baixo poder estatístico.

Outra explicação possível para um IC95 exagerado e falta de confiança no tamanho do efeito observado é a existência de outros fatores ainda desconhecidos, que não foram lembrados e que poderiam afetar o modelo preditivo. A existência de fatores ocultos pode fazer com que um modelo fique incompleto e reduzir a confiabilidade dele. Como fazer para descobrir isso? Realizar mais estudos e tentar descobrir fatores que ainda não levamos em conta.

No caso das OR que calculamos a partir dos dados do trabalho do SIOP, o poder estatístico está OK, e mesmo assim os IC95 são bastante amplos. Isso indicaria a existência de possíveis fatores de prognóstico ocultos, talvez mais importantes do que os fatores já encontrados, que poderiam completar o quadro que se tem no momento. Isso mostra a necessidade de mais estudos, mais pesquisas, incluindo pesquisa básica para descobrir novos fatos que ainda são desconhecidos hoje em dia. É para isso que a pesquisa médica serve: para salvar vidas através da investigação científica.

![](https://upload.wikimedia.org/wikipedia/commons/0/09/Typical_MRI_appearance_of_diffuse_intrinsic_pontine_glioma_%28DIPG%29_-_Fonc-02-00205-g002.jpg)

_Figura: glioma pontino intrínseco difuso (imagem de ressonância magnética). Créditos Katherine E. Warren (2012) [CC BY 3.0](https://creativecommons.org/licenses/by/3.0), via Wikimedia Commons_

_Esta postagem não representa sugestão de tratamento. Apenas um especialista pode judiciosamente decidir quais informações divulgadas podem modificar de alguma forma um esquema de tratamento, e de que forma._

Leia a publicação do modelo da SIOP:
- Lindsey M. Hoffman, _et al_. Clinical, Radiologic, Pathologic, and Molecular Characteristics of Long-Term Survivors of Diffuse Intrinsic Pontine Glioma (DIPG): A Collaborative Report From the International and European Society for Pediatric Oncology DIPG Registries. Journal of Clinical Oncology 2018 36:19, 1963-1972, [doi:10.1200/JCO.2017.75.9308](https://doi.org/10.1200/JCO.2017.75.9308)

Leia também as publicações do modelo de Jansen e sua validação:
- Marc H. Jansen, _et al_. Survival prediction model of children with diffuse intrinsic pontine glioma based on clinical and radiological criteria. Neuro-Oncology 17(1), 160–166, 2015 [doi:10.1093/neuonc/nou104](https://doi.org/10.1093/neuonc/nou104)
- Sophie E. M. Veldhuijzen van Zanten, _et al_. External validation of the diffuse intrinsic pontine glioma survival prediction model: a collaborative report from the International DIPG Registry and the SIOPE DIPG Registry. J Neurooncol (2017) 134:231–240 [doi:10.1007/s11060-017-2514-9](https://doi.org/10.1007/s11060-017-2514-9)
