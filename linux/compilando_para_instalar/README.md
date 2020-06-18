---
description: >-
  A Compilação é um processo natural e vital em cada sistema operacional que
  começa na instalação do SO(Sistema Operacional) até sua descontinuação pelo
  seu desenvolvedor e/ou usuário.
---

# Compilar Programas

## Por que não é familiar?

A maioria de nos nasce em com um Windows e aprendi a baixar programas já compilados ou com instaladores que não especificam suas operações internas, mas isso é um erro? Não, a responsabilidade de mostrar ao usuário oque você como desenvolvedor esta operando na maquina do usuário de modo que qualquer um entenda não e sua responsabilidade, mas convenhamos que isso poderia trazer uma nova visão de usuários e também permitir que usuários possam resolver problemas do software em relação ao seu computador.

## Operações internas

Por mais magico que um compilador possa parecer o mesmo também é um programa que assim como todos os outros foi compilado.

Para ser mais especifico vou abortar as operações básicas de um compilador e no fim vamos compilar um gcc.

### Leitura do código e sintaxe

Nessa etapa as linhas de código são lidas e a sintaxe da linguagem é aplicada , por exemplo abrir chaves\( **`{`** \) deve ser seguido por um fechar chaves\( **`}`** \) identificando um bloco de execução.

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

É e nessa etapa aonde entra os analisadores Léxico, sintático, semântico e o gerador de código.

Analisador **Léxico** responsável por organizar as palavras e símbolos reservados da linguagem como `function`.

Analisador **Sintático** se encarrega de verificar a sequencia de símbolos esta correta como `+, -, *, / e etc`, exemplo: `val0 + val1 == 22` .

Por fim o analisador Semântico gera um mapa\(Uma estrutura de dados\) com a estrutura do programa e o gerador de código lé a estrutura passando da estrutura para uma linguagem de baixo nível seja ela C ou Assemble para por fim montar ou chamar um compilador que monte o programa uma descrição mais completa se encontra nesse [link](https://sites.icmc.usp.br/delamaro/slidescompiladores/compiladoresfinal.pdf).

### Compilando GCC

> Em desenvolvimento consulte [OSdev.org](https://osdev.org) para mais informações

Primeiramente precisamos Obter o compilador GCC para isso execute:

{% tabs %}
{% tab title="Bash" %}
```text
~$ wget https://ftp.gnu.org/gnu/gcc/gcc-10.1.0/gcc-10.1.0.tar.gz
```
{% endtab %}

{% tab title="Result" %}
```text
--2020-05-16 09:39:34--https://ftp.gnu.org/gnu/gcc/gcc-10.1.0/
gcc-10.1.0.tar.gz
Carregou certificado CA "/etc/ssl/certs/ca-certificates.crt"
Resolvendo ftp.gnu.org (ftp.gnu.org)...
 209.51.188.20, 2001:470:142:3::b
Conectando-se a ftp.gnu.org (ftp.gnu.org)|209.51.188.20|:443
... conectado.
A requisição HTTP foi enviada, aguardando resposta... 200 OK
Tamanho: 131174790 (125M) [application/x-gzip]
Salvando em: “gcc-10.1.0.tar.gz”

gcc-10.1.0.tar.gz   100%[===================>] 125,10M      
 5,78MB/s    em 21s

2020-05-16 09:39:56 (5,96 MB/s) - “gcc-10.1.0.tar.gz” salvo 
[131174790/131174790]
```
{% endtab %}
{% endtabs %}

Depois de obter o arquivos `gcc-10.1.0.tar.gz`, vamos descompacta-lo usando o comando:

{% tabs %}
{% tab title="Bash" %}
```text
~$ tar -xf gcc-10.1.0.tar.gz
```
{% endtab %}

{% tab title="Result" %}
```text
dir
├── gcc-10.1.0
└── gcc-10.1.0.tar.gz
```
{% endtab %}
{% endtabs %}

Agora, Vamos compilar e por fim rodar uma aplicação

{% tabs %}
{% tab title="Bash" %}
```text
~$ cd gcc-10.1.0/
~$ ./configure 
--target=i686-elf
--prefix="$HOME/build"
--enable-languages=c,c++
--without-headers
```
{% endtab %}

{% tab title="Result" %}
```text

```
{% endtab %}
{% endtabs %}

Opções utilizadas:

* --target=i686-elf                          \#Arquitetura 
* --prefix="$HOME/build"             \# Local da instalação
* --enable-languages=c,c++        \# Linguagens que serão suportadas 
* --without-headers                       \# diz ao [GCC](https://wiki.osdev.org/GCC) para não confiar em nenhuma biblioteca C \(padrão ou tempo de execução\) presente já que sera um compilador cruzado

Agora vamos compilar e mover para o diretório de instalação, Alias isso pode demorar bastante.

```text
make all-gcc
make all-target-libgcc
make install-gcc
make install-target-libgcc
```

Mas já podemos compilar um `hellowWord.o` ? Não, falta um conjunto de bibliotecas e ferramentas para lincar as bibliotecas e etc ao executável.

Vamos começar por compilar e implementar o Binutis para obter as ferramentas.

{% hint style="info" %}
Em desenvolvimento
{% endhint %}

