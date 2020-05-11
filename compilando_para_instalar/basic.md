---
description: Algo comum para os usuários linux e estranho quanto entrei para esse grupo.
---

# Make, Make Install, Play

### Obtendo o código da aplicação

  Vamos usar como exemplo o [Bash](https://www.gnu.org/software/bash/) um interpretador de comandos muito usado do no linux.

  Antes de proceder com a instalação vamos criar uma estrutura de diretórios aonde poderemos organizar o código fonte das nossas aplicações. Atenção isso e muito relevante principalmente se um dia desejarmos desinstalar um dos programas.

{% tabs %}
{% tab title="Bash" %}
```bash
~$ mkdir ~/opt
~$ mkdir ~/opt/bash
```
{% endtab %}

{% tab title="Tree" %}
```bash
opt  # pasta aonde organizaremos o codigo das aplicações
└── bash # pasta do codigo fonte e dos arquivos de build
```
{% endtab %}
{% endtabs %}

  Agora que já temos aonde guardar o código fonte, vamos baixar pelo [Git](https://git-scm.com) os fontes:

{% tabs %}
{% tab title="Bash" %}
```bash
~$ git clone https://git.savannah.gnu.org/git/bash.git source
```
{% endtab %}

{% tab title="Tree" %}
```bash
opt  # pasta aonde organizaremos o codigo das aplicações
└── bash  # pasta do codigo fonte e dos arquivos de build
    └── source  # pasta com o codigo do Bash

```
{% endtab %}
{% endtabs %}

 Agora com o código fonte em mão vamos ver nossas opções, para ser claro dependendo do software a ser instalado podemos usar :

```bash
# Caso seja em python
~$ python setup.py install
```

e ou

```bash
# Esse é o mais comum e se aplica na maioria dos feitos em c
~$ ./configure #script de configuração
~$ make    #programa executa o script de compilação Makefile
~$ make install # move os arquivos compilados
```

   Mas por que temos essa diferença, na realidade para instalar um software você muitas vezes você precisará usar iniciar um programa que ira organizar e configurar os arquivos do programa desejado.

   Normalmente todos os script de configuração fornecem algumas opções entre elas as mais comuns são

* --prefix=&lt;{  Diretório de instalação }&gt;
* --target=&lt;{ Arquitetura da compilação como i686-elf }&gt;

  No nosso caso vamos utilizar o --prefix para guardar a compilação no diretório `~/opt/bash/build`.

{% tabs %}
{% tab title="Bash" %}
```bash
# Dizendo para o configure aonde queremos instalar
~$ ./configure --prefix="$HOME/opt/bash/build"
~$ make
~$ make install
```
{% endtab %}

{% tab title="Second Tab" %}
```text
opt  # pasta aonde organizaremos o codigo das aplicações
└── bash  # pasta do codigo fonte e dos arquivos de build
    ├── build # pasta com o programa gerado
    └── source # pasta dos codigos fontes

```
{% endtab %}
{% endtabs %}

 Pronto, para testar é só rodar no terminal

```bash
~$ cd ~/opt/bash/build/bin/
~$ ./bash
bash-5.0$ 
```

 Bem agora que podemos usar o software vamos **desinstalar** o mesmo, para desinstalar usamos o comando `make uninstall` no diretório do código fonte.

```bash
~$ cd ~/opt/bash/source/
~$ make uninstall
```

 Concluindo, aqui esta uma uma lista completa dos comandos.

```bash
~$ mkdir ~/opt
~$ mkdir ~/opt/bash
~$ ./configure --prefix="$HOME/opt/bash/build"
~$ make
~$ make install
~$ cd ~/opt/bash/build/bin/
~$ ./bash
bash-5.0$ exit
~$ cd ~/opt/bash/source/
~$ make uninstall
```

