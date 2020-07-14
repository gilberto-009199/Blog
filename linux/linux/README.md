# Basíco

{% hint style="info" %}
Em desenvolvimento
{% endhint %}

  Escrever e organizar um software não é uma tarefa fácil,  ainda mais quando o sistema vai crescendo e ficando cada fez mais complexo, sendo assim a complexidade da sua organização deve ir crescendo junto. Sendo assim vamos dar uma olhada sobre como os sistema operacional\(OS\) linux organizam suas aplicações e registros.

  Conforme você for trabalhando em um sistema operacional Linux, você acabará descobrindo como o sistema se organiza e saber como manipular isso.

  Tudo começa com o `/`  a raiz de todo o sistema operacional e suas aplicações ela se assemelha ao `C:\` no windows.

### /ETC

{% hint style="info" %}
O diretório `/etc` originalmente significava "etc" e/ou "outros" na documentação inicial do Bell Labs e costumava conter arquivos que não pertenciam a nenhum local. Nas distribuições modernas do Linux, o diretório `/etc` geralmente contém arquivos de configuração estática, conforme definido pelo File Hierarchy Standard \(ou "FHS"\).
{% endhint %}

  Arquivos de Configuração do sistema.

### /opt - 

### /srv - 

### /bin - 

### /sbin - 

### /lib - 

### /usr - 

#### /usr/bin - 

#### /usr/sbin - 

#### /usr/lib - 

#### /usr/local - 

#### /usr/src -

#### /boot - 

#### /tmp - 

#### /dev - 

#### /mnt - 

#### /media - 

### /home - 

#### /home/bob/

#### /home/bob/.local

### /root - 

### /proc - 

### /var - 

#### /var/log - 

#### /var/lock - 

#### /var/run -

#### /var/spool - 

#### /var/mail - 

#### /var/cache -

## Mas para que isso?

  Bem na primeira vista da maioria, para nada, mas vou dar uma exemplo de uso em montando um cenário , aonde você é um programador e precisará utilizar seu conhecimento do diretório `/proc` para ajudar a salvar a reputação da sua empresa.

#### Montando o cenário

  A empresa em que você trabalha esta patrocinando um evento junto com outras grandes do mercado de TI. O evento para retribuir o seu patrocínio permite que todos os patrocinadores coloquem disponibilizem um link para um formulário aonde poderão pegar o currículo ou o contato de um cliente.

  Mas ocorreu um erro na inserção dos dados entre a aplicação e o banco de dados é os usuários estão apontando para uma mensagem esquisita de `SQL ERROR` na tela , infelizmente o programador  da aplicação chamado `Bob` foi almoçar e só volta quando o evento acabar. 

  Para solucionar isso você deve ler a variável que contem o sql incorreto e alterar a variável padrão da memoria do programa pelo correto.

#### Hora de implementar! Go horse!

  Primeiro precisamos do `PID`\(Identificador do processo\) que ira nos ajudar a encontrar a memoria que a  aplicação esta usando no momento.

{% hint style="info" %}
Em desenvolvimento
{% endhint %}

