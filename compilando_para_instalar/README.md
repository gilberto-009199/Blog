---
description: >-
  A Compilação é um processo natural e vital em cada sistema operacional que
  começa na instalação do SO(Sistema Operacional) até sua descontinuação pelo
  seu desenvolvedor e/ou usuário.
---

# Compilar

### Por que não é familiar?

   A maioria de nos nasce em com um Windows e aprendi a baixar programas já compilados ou com instaladores que não especificam suas operações internas, mas isso é um erro? Não, a responsabilidade de mostrar ao usuário oque você como desenvolvedor esta operando na maquina do usuário  de modo que qualquer um entenda não e sua responsabilidade, mas convenhamos que isso poderia trazer uma nova visão  de usuários e também permitir que usuários possam resolver problemas do software em relação ao seu computador.

### Operações internas

Por mais magico que um compilador possa parecer o mesmo também é um programa que assim como todos os outros foi compilado.

Para ser mais especifico vou abortar as operações básicas de um compilador e no fim vamos compilar um gcc.  

#### Leitura do código e sintaxe

  Nessa etapa as linhas de codigo são lidas e a sintaxe da linguagem é aplicada , por exemplo abrir chaves\( { \) deve ser sequido por um fechar chaves\( } \) identificando um bloco de execução.

{% tabs %}
{% tab title="Code" %}
```text
function Somar(val0, val1){
   alert(val0 + val1); 
```
{% endtab %}

{% tab title="Result" %}
```text
function Somar(val0, val1){ <-- Sintax error
   alert(val0 + val1);
```
{% endtab %}
{% endtabs %}



#### Unir arquivos e lincar bibliotecas 

Conteudo

