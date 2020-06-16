---
description: >-
  Esse algoritmo e usado no aprendizado de maquina com aprendizado
  supervisionado.
---

# Algoritmo KNN

  Algoritmo KNN é utilizado na aprendizagem de maquina supervisionado, basicamente nesse artigo vamos implementar esse algoritmo em um cenário de um restaurante internacional.

## Montar o cenário

![Vis&#xE3;o dos DataSet](../.gitbook/assets/imagemdosdados.png)

  Estamos em um ilustre restaurante Italiano dentro do Aeroporto Internacional John F. Kennedy na cidade de New York, nosso cliente possui um clientela internacional bastante variada sendo composta por Americanos, Brasileiros, Espanhóis e Franceses. O nosso cliente deseja abrir uma filial, mas não sabe em qual nação seu Cardápio Italiano sera mais apreciados.

  Para auxilia lo nosso cliente te enviou as comandas de 5 dias de trabalho com a respectiva quantidade em gramas de Carne vermelha , Carne Branca , Massas, Frutas e Vegetais por pessoa.

{% hint style="warning" %}
Atenção nesse cenário existem varias variáveis que precisamos considerar, mas não vamos abordar essas questões, para facilitar a implementação do algoritmo. Além é claro que nosso cliente poderia simplesmente perguntar ao cliente qual sua nacionalidade.
{% endhint %}

  Como fonte dos hábitos alimentares dos Americanos, Brasileiros , Espanhóis e Franceses você utilizou um estudo da _International Scientific Institute of Biology and Agriculture_.

## Comece bonitão! Go Horse!

  Tendo agora um arquivo com a media de consumo de cada nacionalidade em gramas e a quantidade consumida, construa um programa que leia o arquivo com as medias de cada nacionalidade e as comandas e faça o cruzamento dos dados devolvendo a nacionalidade com mais clientes.

{% file src="../.gitbook/assets/mediapornasci.knn.algoritmo.txt" caption="Scientific Institute of Biology and Agriculture." %}

{% file src="../.gitbook/assets/comandas.knn.algoritmo.txt" caption="Comandas do Restaurante" %}

  Esta na hora de produzir o código que usara a media do estudo e as comandas para através da distancia euclidiana definir a nacionalidade de cada cliente.

  Para ser mais abrangente em termos de linguagem eu farei o Script em Javascript, Python e JAVA, para assegurar que a maioria compreenda em sua linguagem mais familiar.

  Antes de procedermos saiba que as descrições podem estar um tanto complexas para falar a verdade, então não exite em pegar uma café e/ou ler uma 2° vez.

### Função da Distancia Euclidiana

  Para pensar em distancia nos termos da distancia euclidiana, pense que a distancia de uma entidade para outra nada mais é do que quantas diferenças uma entidade possui em relação a outra entidade.

* Pegar a diferença entre as propriedades das entidades

{% tabs %}
{% tab title="JavaScript" %}
```javascript
// Função que retorna a distancia euclidiana de 2 clientes
function getEuclidiana( cliente0 , cliente1){
    /*
        Distância euclidiana é a raiz quadrada da soma das
        diferenças dos valores dos atributos elevado ao quadrado
    */

    let soma = (cliente0.carnes_vermelhas - cliente1.carnes_vermelhas)** 2
                     + (cliente0.carnes_brancas   - cliente1.carnes_brancas)** 2
                     + (cliente0.massas           - cliente1.massas        )** 2
                   + (cliente0.frutas           - cliente1.frutas        )** 2
                   + (cliente0.vegetais         - cliente1.vegetais      )** 2;

    return Math.sqrt(soma, 2); // ou soma ** (1/2);
}
```
{% endtab %}

{% tab title="Python" %}
```python
import math;

# Função que retorna a distancia euclidiana de 2 clientes
def getEuclidiana( cliente0 , cliente1 ):
  """
      Distância euclidiana é a raiz quadrada da soma das
     diferenças dos valores dos atributos elevado ao quadrado
  """
  soma =  (cliente0['carnes_vermelhas'] - cliente1['carnes_vermelhas'])**2
  soma += (cliente0['carnes_brancas'] - cliente1['carnes_brancas'])**2
  soma += (cliente0['massas'] - cliente1['massas'] )** 2
  soma += (cliente0['frutas'] - cliente1['frutas'] )** 2
  soma += (cliente0['vegetais'] - cliente1['vegetais'] )** 2

  return math.sqrt(soma, 2); # ou soma ** (1/2);
```
{% endtab %}

{% tab title="JAVA" %}
```java
public double getEuclidiana(Cliente cliente0 , Cliente cliente1){
 /*
      Distância euclidiana é a raiz quadrada da soma das
     diferenças dos valores dos atributos elevado ao quadrado
 */

 double soma = 0;
 soma+=Math.pow((cliente0.carnes_vermelhas - cliente1.carnes_vermelhas),2);
 soma +=Math.pow((cliente0.carnes_brancas   - cliente1.carnes_brancas), 2);
 soma +=Math.pow((cliente0.massas           - cliente1.massas        ), 2);
 soma +=Math.pow((cliente0.frutas           - cliente1.frutas        ), 2);
 soma +=Math.pow((cliente0.vegetais         - cliente1.vegetais      ), 2);

 return Math.sqrt(soma);
}
```
{% endtab %}

{% tab title="C++" %}
```cpp
double getEuclidiana(Cliente cliente0 , Cliente cliente1){
 /*
      Distância euclidiana é a raiz quadrada da soma das
     diferenças dos valores dos atributos elevado ao quadrado
 */

    double soma = 0;
    soma += pow((ind1.getA() - ind2.getA()), 2); 
    soma += pow((ind1.getB() - ind2.getB()), 2); 
    soma += pow((ind1.getC() - ind2.getC()), 2); 
    soma += pow((ind1.getD() - ind2.getD()), 2);


    return sqrt(soma);
}
```
{% endtab %}
{% endtabs %}

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

| Cliente | Carne vermelha | Carne Branca | Massas | Frutas | Vegetais |
| :---: | :---: | :---: | :---: | :---: | :---: |
| A | 10.00 g | 10.00 g | 07.24 | 03.50 | 02.10 |
| B | 08.00 g | 11.00 g | 06.24 | 03.64 | 03.00 |
| A - - - - B | 02.00 g | -01.00 g | 01.00 | 00.14 | -00.90 |
| x² | 4.0 | 1.0 | 1.0 | 0.019 | 0.81 |

* Fazer a raiz quadrada

{% hint style="info" %}
Para os Curiosos e entusiasmados por programação, a função de raiz na maioria das linguagens que eu conheço implementam uma função com nome de `sqrt( x, 2)` ao invés de `²√x` para as operações, então para evitar aprender a utilizar uma em cada linguagem eu sempre uso a potenciação: `x ** ( 1 / 2 )`  .

`sqrt( x, 2 ) == x ** ( 1 / 2 )` ou `sqrt( x, 3 ) == x ** ( 1 / 3 )`
{% endhint %}

| Carne vermelha | Carne Branca | Massas | Frutas | Vegetais | Soma | Raiz |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 4.0 | 1.0 | 1.0 | 0.019 | 0.81 | 6,829 | 46.63 |

### Função da Classificação

  Dentro dessa função vamos comparar o cliente que precisa ser identificado com os clientes que já sabemos a nacionalidade.

 Depois criar uma vetor que indexe as relações de distancia entre as entidades cliente não identificadas\(Comanda\) para os clientes do estudo.

####   Pegando os dados

  Começamos lendo os dados nos dois arquivo e adicionando nas nossas listas. para isso vamos criar uma função para ler e montar os dados.

{% tabs %}
{% tab title="Python" %}
```python
def le_arquivo(nome):
    # Lista com os dados pegos linha por linha
    listDados = [];
    # Abre o arquivo para leitura 'r'
    with open( nome,'r') as arquivo:
        # Le o arquivo linah por linha
        for line in arquivo:
            # Corta o texto da linha para pegar cada dado
            carne_vermelha  = float(line[4:9]);
            carne_branca    = float(line[13:18]);
            massa           = float(line[22:27]);
            fruta           = float(line[31:36]);
            vegetais        = float(line[40:45]);
            nascionalidade  = line[50:57];
            # Monta o Cliente e adiciona na lista 
            listDados.append({  'carnes_vermelhas':carne_vermelha,
                                'carnes_brancas':carne_branca,
                                'massas':massa,
                                'frutas':fruta,
                                'vegetais':vegetais,
                                'nascionalidade':nascionalidade
                             });
        # Fecha o arquivo aberto
        arquivo.close();
    # Retorna as informação guardadas na lista
    return listDados;
```
{% endtab %}
{% endtabs %}

Agora que já podemos ler vamos pegar os dados do estudo que esta no arquivo de nome`mediaPorNasci.knn.algoritmo.txt` e os dados das comandas não identificadas no arquivo `comandas.knn.algoritmo.txt` , e começar a comparação.

{% hint style="info" %}
Em desenvolvimento
{% endhint %}

