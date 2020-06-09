---
description: Programa de Gerenciamento de SGBD's
---

# DBeaver

DBeaver é um programa feito em java que utiliza a JPA e jdbc para conectar em diversos bancos de dados como MySQL, Postgress, SQL Server, ORACLE e etc.

Para começar precisaremos do código fonte, para isso vamos clonar o repositório:

```text
$ git clone https://github.com/dbeaver/dbeaver.git dbeaver
$ cd dbeaver
$ mvn package   # ou mvn install
```

Depois disso as releases estarão em `product/standalone/target/products/` , dentro da pasta terá um compila do para Linux, MacOS e Windows.

Mas como o executável para cada plataforma não é um jar? Ao invés de um arquivo binário executável para cada plataforma, na realidade o DBeaver se utilizou do `tycho` usado pelo eclipse se você quiser saber mais acesso esse [link](https://git.eclipse.org/c/tycho/org.eclipse.tycho-demo.git/tree/itp01/tycho.demo.itp01/src/tycho/demo/itp/Application.java).

{% hint style="info" %}
Em desenvolvimento
{% endhint %}

