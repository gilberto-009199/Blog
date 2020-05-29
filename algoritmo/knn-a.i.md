---
description: >-
  Esse algoritmo e usado no aprendizado de maquina com aprendizado
  supervisionado.
---

# Algoritmo KNN

  Algoritmo KNN e utilizado no aprendizado de maquina supervisionado, basicamente nesse Artigo vamos implementar esse algoritmo em um cenário de um restaurante internacional.

#### Montar o cenário

  Estamos em um ilustre restaurante Italiano dentro do Aeroporto Internacional John F. Kennedy na cidade de New York, nosso cliente possui um clientela internacional bastante variada sendo composta por Americanos, Brasileiros,  Espanhóis e Franceses. O nosso cliente deseja abrir uma filial, mas não sabe em qual nação seus Cardápio Italiano serão mais apreciados.

  Para auxilia lo nosso cliente te enviou as comandas de 5 dias de trabalho com a respectiva quantidade em gramas de Carne vermelha , Carne Banca , Massas, Frutas e Vegetais por pessoa.

{% hint style="warning" %}
Atenção nesse cenário existem varias variáveis  que precisamos considerar, mas não vamos abordar essas questões, para facilitar a implementação do algoritmo. Além é claro que nosso cliente poderia simplesmente perguntar ao cliente qual sua naturalidade.
{% endhint %}

  Como fonte dos hábitos alimentares dos Americanos, Brasileiros , Espanhóis e Franceses você utilizou um estudo da _International Scientific Institute of Biology and Agriculture_.

#### Comece bonitão! Go Horse!

  Tendo agora um arquivo com a media de consumo de cada nacionalidade em gramas e a quantidade consumida, construa um programa que leia o arquivo com as medias de cada nacionalidade e as comandas e faça o cruzamento dos dados devolvendo a nacionalidade com mais clientes.

{% file src="../.gitbook/assets/mediapornasci.knn.algoritmo.txt" caption="Scientific Institute of Biology and Agriculture." %}

{% file src="../.gitbook/assets/comandas.knn.algoritmo.txt" caption="Comandas do Restaurante" %}

  Esta na hora de produzir o código que usara a media do estudo e as comandas para através da distancia euclidiana definir a nacionalidade de cada cliente.

![Vis&#xE3;o dos DataSet](../.gitbook/assets/imagemdosdados.png)

  Para ser mais abrangente em termos de linguagem eu farei o Script em Javascript, Python e JAVA, para assegurar que a maioria compreenda em sua linguagem mais familiar.

  Antes de procedermos saiba que as descrições podem estar um tanto complexas para falar a verdade, então não exite em pegar uma café e/ou ler uma 2° vez.

#### Função da Distancia Euclidiana

  Para pensar em distancia nos termos da distancia euclidiana, pense que a distancia de uma entidade para outra nada mais é do que o quanto as diferenças de uma entidade possui em relação a outra entidade.

* Pegar a diferença entre as propriedades das entidades

  Primeiro vamos pegar o cliente A que é Americano e consumiu 10.00 g de carne vermelha e vamos pegar a diferença com o cliente B que consumiu 08.00 g de carne vermelha oque nos da: 

| Carne Vermelha A | Carne Vermelha B | Diferença |
| :---: | :---: | :--- |
| 10.0 g | 08.0 g | 02.0 g |

* Elevar ao quadrado a diferença 

  Agora com a diferença 2.0 g vamos elevar ao quadrado.

| Diferença | Quadrado |
| :---: | :---: |
| 02.0 g | 04.0 g |

* Somar as diferenças 

10.00 10.00 07.24 03.50 02.10 America 

08.00 11.00 06.24 03.64 03.00 America

| Cliente |  Carne vermelha | Carne Banca  | Massas | Frutas | Vegetais |
| :---: | :---: | :---: | :---: | :---: | :---: |
| A | 10.00 g | 10.00 g | 07.24 | 03.50 | 02.10 |
| B | 08.00 g | 11.00 g | 06.24 | 03.64 | 03.00 |
| A - - - - B | 02.00 g |  -01.00 g | 01.00 | 00.14 | -00.90 |
| x² | 4.0 | 1.0 | 1.0 | 0.019 | 0.810 |

* Fazer a raiz quadrada







{% tabs %}
{% tab title="JavaScript" %}
```text
function getEuclidiana( cliente0 , cliente1){
	/*
		a distância euclidiana é a raiz quadrada da soma das
		diferenças dos valores dos atributos elevado ao quadrado
	*/

	let soma = (cliente0.carnes_vermelhas - cliente1.carne_vermelha ) ** 2
					 + (cliente0.carnes_brancas   - cliente1.carnes_brancas ) ** 2
					 + (cliente0.massas           - cliente1.massas         ) ** 2
				   + (cliente0.frutas           - cliente1.frutas         ) ** 2
				   + (cliente0.vegetais         - cliente0.vegetais       ) ** 2;
	
	return soma ** (1/2);
}
```
{% endtab %}

{% tab title="Python" %}
```text

```
{% endtab %}

{% tab title="JAVA" %}
```

```
{% endtab %}
{% endtabs %}







{% hint style="info" %}
Em desenvolvimento
{% endhint %}

