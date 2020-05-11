---
description: Algo comum para os usuários linux e estranho quanto entrei para esse grupo.
---

# Make, Make Install, Play

### Obtendo o código da aplicação

  Vamos usar como exemplo o [Nodejs](https://nodejs.org), uma plataforma de execução de JavaScript do lado do servidor.

  Antes de proceder com a instalação vamos criar uma estrutura de diretórios aonde poderemos organizar o código fonte das nossas aplicações. Atenção isso e muito relevante principalmente se um dia desejarmos desinstalar um dos programas.

{% tabs %}
{% tab title="Bash" %}
```bash
~$ mkdir ~/opt
~$ mkdir ~/opt/node
```
{% endtab %}

{% tab title="Tree" %}
```bash
opt  # pasta aonde organizaremos o codigo das aplicações
└── node # pasta do codigo fonte e dos arquivos de build
```
{% endtab %}
{% endtabs %}

  Agora que já temos aonde guardar o código fonte, vamos baixar pelo [Git](https://git-scm.com) os fontes:

{% tabs %}
{% tab title="Bash" %}
```bash
~$ git clone https://github.com/nodejs/node.git sources
```
{% endtab %}

{% tab title="Tree" %}
```bash
opt  # pasta aonde organizaremos o codigo das aplicações
└── node  # pasta do codigo fonte e dos arquivos de build
    └── sources  # pasta com o codigo no Nodejs

```
{% endtab %}
{% endtabs %}



