ADVPLayL
========
Editor para fins educativos com compila‡?o online.

**o que vai precisar:**
- protheus

**o que reposit¢rio possui:**
- runtime.prw
- editor.aph
- explorer.aph


Como configurar
=============

Considerando que vocˆ saiba com compilar fontes no Protheus. Ap¢s compilar, 
apenas configurar o http server do protheus no appserver.ini da com as 
seguintes informa‡?es:

```
[HTTP]
ENABLE=1
PORT=80
PATH=C:\caminho\qualquer\da\sua\maquina
ENVIRONMENT=AMBIENTE_QUE_EXISTA
```


Como utilizar
=============

Ap¢s a configura‡?o apenas acessar em seu browser:

```
http://localhost/u_editor.aph
```

A interface consiste em um editor, onde o programa ser  escrito. E algumas 
caixas para interagir com o programa.

A caixa de stdout (sa¡da), ir  exibir o que o programa enviar para _U_Stdout()_
e _U_StdoutLn()_ onde a segunda automaticamente quebra uma linha. Os valores 
s?o automaticamente convertidos para string.

A caixa de stdout (sa¡da esperada), deve ser colocado o valor que vocˆ espera
exibir com o seu programa, assim a ferramenta compara sua sa¡da com a sa¡da
esperada e avisa se o algoritmo funcionou. Porem n?o ‚ obrigatorio preenche-lo.

A caixa de stdin (entrada), ‚ onde pode informar os dados que entram no 
programa, para cada chamada da fun‡?o _U_Stdin()_ a fun‡?o retorna uma linha 
desta caixa para dentro do programa. A fun‡?o sempre retorna uma string.

A caixa options, conta com o entry que ‚ o nome da primeira fun‡?o que ser 
chamada na execu‡?o. E tamb‚m filename, que guarda um arquivo no servidor com
esse nome. Que pode ser recuperado pelo explorer.

Para acessar o explorer:

```
http://localhost/u_explorer.aph
```


Detalhe do reposit¢rio
======================

**runtime.prw**

Possui a classe do RPO auxiliar e fun‡?es U_Stdout, U_StdoutLn e U_Stdin, 
tamb‚m a fun‡?o que recebe a requisi‡?o compila executa e devolve o retorno.

**editor.aph**

Possui o HTML da interface do usu rio com o editor e chama o runtime.

**explorer.aph**

Possui o HTML da interface do usu rio com o explorer de arquivos.


Extras
======

Caso vocˆ possua a chave de compila‡?o da Totvs ‚ poss¡vel remover os "U_" 
apenas removendo o define inicial USERFUNCTION do fonte runtime.prw


O que ser  feito
================
- um sistema para finalizar threads executando a muito tempo