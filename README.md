![Editor](img/tela.png?raw=true)

ADVPLayL
========
Editor para fins educativos com compilação online.

**o que vai precisar:**
- protheus

**o que repositório possui:**
- runtime.prw
- editor.aph
- explorer.aph


Como configurar
=============

Considerando que você saiba com compilar fontes no Protheus. Após compilar, 
apenas configurar o http server do protheus no appserver.ini da com as 
seguintes informaçães:

```
[HTTP]
ENABLE=1
PORT=80
PATH=C:\caminho\qualquer\da\sua\maquina
ENVIRONMENT=AMBIENTE_QUE_EXISTA
```


Como utilizar
=============

Após a configuração apenas acessar em seu browser:

```
http://localhost/h_editor.aph
```

A interface consiste em um editor, onde o programa ser  escrito. E algumas 
caixas para interagir com o programa.

A caixa de stdout (saída), ir  exibir o que o programa enviar para _U_Stdout()_
e _U_StdoutLn()_ onde a segunda automaticamente quebra uma linha. Os valores 
são automaticamente convertidos para string.

A caixa de stdout (saída esperada), deve ser colocado o valor que você espera
exibir com o seu programa, assim a ferramenta compara sua saída com a saída
esperada e avisa se o algoritmo funcionou. Porem não é obrigatorio preenche-la.

A caixa de stdin (entrada), é onde pode informar os dados que entram no 
programa, para cada chamada da função _U_Stdin()_ a função retorna uma linha 
desta caixa para dentro do programa. A função sempre retorna uma string.

A caixa options, conta com o entry que é o nome da primeira função que ser 
chamada na execução. E também filename, que guarda um arquivo no servidor com
esse nome. Que pode ser recuperado pelo explorer.

Para acessar o explorer:

```
http://localhost/u_explorer.aph
```


Detalhe do repositório
======================

**runtime.prw**

Possui a classe do RPO auxiliar e funçães U_Stdout, U_StdoutLn e U_Stdin, 
também a função que recebe a requisição compila executa e devolve o retorno.

**editor.aph**

Possui o HTML da interface do usu rio com o editor e chama o runtime.

**explorer.aph**

Possui o HTML da interface do usu rio com o explorer de arquivos.


Extras
======

Caso você possua a chave de compilação da Totvs é possível remover os "U_" 
apenas removendo o define inicial USERFUNCTION do fonte runtime.prw


O que ser  feito
================
- um sistema para finalizar threads executando a muito tempo
