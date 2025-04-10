**Grupo de 4 pessoas**, um integrante do grupo criara um repositório público no github, com o nome que quiser, e adicionara os outros integrantes do grupo a este repositório para poderem fazer *push*. 
O grupo criara um *gitflow* básico, uma branch **main**, com um arquivo readme.md contendo o nome de todos os integrantes do grupo (em ordem alfabética), depois será criado uma branch **dev** e será encerido "Linha Raiz" ao final do arquivo, na branch **dev** é para ficar assim

```plain
Fulano de Tal
John Doe
Mario Rossi
Monsieur Untel

Linha Raiz
```

Cada Integrante deverá criar uma nova branch a partir do dev com o nome seguindo este padrão: ***feature/<sua posição na lista>*** para alterar a "linha raiz" colocando seu nome no final, e o número 1 (um) no final:

```plain
Fulano de Tal
John Doe
Mario Rossi
Monsieur Untel

Linha Raiz - Fulano de Tal - 1
```

Deverá ser feito um `merge` de todas as branchs **feature/<algum número>** na branch dev, porém, a informação que deve persistir é a do primeiro integrante, neste caso, do Fulano de Tal. Depois disso, deverá ser feito um `merge` usando o parâmetro `--squash` na branch main (mensagem do commit deverá ser o nome e a posição do integrante `ex: Fulano de Tal - 1`).

Depois disto, deverá ser realizado o mesmo processo, porém, agora o número que será colocado no final do nome é o 2 (dois) e o nome que terá que prevalecer é do segundo integrante, será feito a mesma coisa para o terceiro e quarto integrante.