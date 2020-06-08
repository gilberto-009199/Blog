---
description: >-
  A criação de script é um processo vital para todas as empresas que usam
  hospedagem VPS.
---

# Script

  As aplicações muitas vezes vão precisar executar operações que não estão relacionadas com a logica de negocio de seus cliente, mas com a propria funcionamento da aplicação como backup, limpeza de logs e remoção de arquivos como imagens não mais utilizadas. 

###   Para solucionar isso?

  Alguns desenvolvedores preferem usar suas línguas nativas como javascript, java, php e etc, para criar as rotinas necessárias, mas como sou um usuário de Debian e Manjaro prefiro utilizar o Bash, pois ele já possui um serie de ferramentas já implementadas dentro do sistema operacional, além de ser bem mais fácil e rápido codificar programas que operem com arquivos já que pode ser testado rapidamente.

####   Montando o cenário

  Você é um programador Nodejs recém saído do curso técnico, na sua primeira empresa, depois de muitos dias de testes e cruds que você fez para sua nova empresa, chega o dia em que só tem você para subir suas alterações para produção.

   Nesse momento o responsável pela qualidade e o sênior permitem você subir em produção é te enviam a chave ssh para a conexão, depois de se conetar você se pergunta aonde esta o diretório de produção? O sênior lé diz que fica em `/opt/workspace` . imediatamente você entra no diretório e da os famosos `git pull origin master` e executa `nodemon ou pm` para reiniciar a aplicação.

####   Ideia

  Pensando sobre isso, antes de dormir você pensa como teria sido mais eficiente se assim que você entra se aparece se uma mensagem dizendo aonde esta o diretório da aplicação.

###   Implementação

  Primeiro vamos criar um arquivo, chamado MyScript que conterá a mensagem do dia\( Só os fortes entenderão\).

```bash
~$ touch MyScript
```

 Depois vamos escrever `#!/bin/bash`  para dizer qual será o nosso interpretador, ficando assim:

{% tabs %}
{% tab title="Bash" %}
```bash
~$ echo "#!/bin/bash" >> MyScript
```
{% endtab %}

{% tab title="MyScript" %}
```bash
#!/bin/bash
```
{% endtab %}
{% endtabs %}

  Agora que temos o nosso script, vamos colocar a nossa mensagem.

```bash
#!/bin/bash
#  Diretorio de trabalho
work="/opt/workspace";
# Menssagem do dia kkkk
echo " Bem-vindo, $USER ";
echo " Shell: $SHELL ";
echo " Work: $work ";
echo " Para ir Digite: work ";

work(){
  cd "$work";
}
```

