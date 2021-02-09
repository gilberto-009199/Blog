---
description: >-
  Nesse artigo vamos fazer a construção de um cliente torrent do zero, sem
  nenhum framework ou biblioteca.
---

# Torrent Client

{% hint style="info" %}
Esse artigo ainda esta sendo criado aguarde, mas ara aqueles com mais interesse utilizem os links a baixo:

* [Implementação do protocolo bittorrent](http://www.bittorrent.org/)
* [Wiki bit Torrent](https://wiki.theory.org/index.php/Main_Page)
{% endhint %}

 Para começar vamos necessitar do protocolo bitTorrent, através dele poderemos saber como nos comunicar com a rede torrent. 

###  Oque é um protocolo?

  No nosso caso vamos utilizar o protocolo [BitTorrent BEB 3](https://www.bittorrent.org/beps/bep_0003.html) dentro dele existe as especificações e padrões para a comunicação.

  Em termos gerais um protocolo e um metodo de transmitir e/ou agir dentro de um relacionamento entre 2 ou mais maguinas.

###  Criando e entendendo a estrutura basica

   Vamos começar pelas entidades\(Modelos\) dentro da especificação _bencoding metainfo files_, _trackers_, _peer protocol_ e _peer messages_.

  Vamos começar com as estruturas de dados dos _trackers nessa estruruta será guardado  a url necessario para a conexão com um servidor que anunciara a nossa presença  pela rede tor._

#### _Trackers\(Rastreadores\)_

    _Essa entidade vai conter os seguintes atributos:_

| Atributo | Tipo | Descrição |
| :--- | :--- | :--- |
| info\_hash |  |  |
| peer\_id |  |  |
| uploaded |  |  |
| downloaded |  |  |
| compact |  |  |
| left |  |  |

