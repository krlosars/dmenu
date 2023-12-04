DMenu - Patches Aplicados
=========================

Este documento apresenta todos os patches que julguei úteis aplicar em relação ao código fonte da versão 5.2 do **Dmenu**.
Os três primeiros patches foram aplicados sem necessidade de qualquer correção. Os dois últimos precisaram de alguns ajustes,
mas nada realmente importante.

dmenu-grid-4.9.diff
-------------------

_Link:_ https://tools.suckless.org/dmenu/patches/grid

Este patch permite apresentar as opções em um formato de "grade", i.e., colunas e linhas (quando aplicado com a tag ***"-l"***)
através da implementação da tag ***"-g"***. Um exemplo:

```sh
seq 1 12 | dmenu -c -l 3 -g 4
```

O exemplo acima iria apresentar os números de um a doze para seleção, dispostos em uma grade contendo três linhas com quatro colunas.
Para maiores informações, siga o link de referência apresentado acima.

dmenu-gridnav-5.2.diff
----------------------

_Link:_ https://tools.suckless.org/dmenu/patches/gridnav

Patch aplicado para melhoria do patch anterior. Em sua versão original, o patch **dmenu-grid-4.9.diff** somente permitia avançar
e retroceder entre as opções apresentadas. Com a aplicação do patch **dmenu-gridnav-5.2.diff** é possível utilizar as teclas de
setas para movimentar o cursor de seleção nas quatro direções.

dmenu-center-5.2.diff
---------------------

_Link:_ https://tools.suckless.org/dmenu/patches/center

Este patch introduz a tag ***"-c"***. Esta tag permite centralizar o seletor do Dmenu na tela, tanto vertical quanto horizontalmente.
Isso é útil sobretudo quando utilizando o patch **dmenu-grid-4.9.diff** acima citado: confere ao seletor uma aparência semelhante à
do lançador de aplicativos **Rofi**.

dmenu-border-20230512-0fe460d
-----------------------------

_Link:_ https://tools.suckless.org/dmenu/patches/border

Mais um complemento ao primeiro patch: uma borda é traçada ao redor do seletor. Como dito anteriormente, é algo que faz muito mais
sentido quando utilizando uma exibição em linhas e colunas. Esta versão do patch implementada apresenta algumas possibilidades de
configuração que podem ser conhecidas utilizando o link de referência acima.

dmenu-separator-5.2.patch
-------------------------

_Link:_ https://tools.suckless.org/dmenu/patches/separator

Implementa a tag ***"-d"*** que permite criar entradas para o Dmenu com valores diferentes dos exibidos. Veja o exemplo abaixo:

```
echo -e "Desligar#sudo systemctl poweroff\nReiniciar#systemctl reboot" | dmenu -d "#"
```

Os comandos acima apresentariam as opções "Desligar" e "Reiniciar" ao usuário. O resultado da seleção, no entanto, seria
o valor descrito após o **"#"** em cada opção -- _"sudo systemctl poweroff"_ e _"systemctl reboot"_  respectivamente. Note
que o caractere utilizado como separador entre rótulos e valores é definido através da tag ***"-d"***.

dmenu-dracula-20211128-d78ff08.diff
-----------------------------------

Link: https://tools.suckless.org/dmenu/patches/dracula

Este patch implementa o tema "Dracula" para o Dmenu.
