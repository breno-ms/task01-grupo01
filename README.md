# task01-grupo01
Repositório para a realização da primeira atividade do Vem Ser, onde os membros do grupo deverão explicar o funcionamento de alguns comandos do git.


# Git cherry pick
## Funcionamento
- Serve para copiar os dados de um ou mais commits especificos de uma branch para outra, aplicando-os.

Para utilizar precisa: 
1. Identificação dos commits
-- Pode obter o identificador único do commit (hash) a partir do histórico de commits usando comandos como **git log**. 

*O comando git log é usado para exibir o histórico de commits em um repositório Git. Ele mostra informações detalhadas sobre cada commit, como autor, data, mensagem e o identificador único (hash)*

## Sintaxe
- git cherry-pick <commit-hash> // Aplicar um único commit em um branch
- git cherry-pick <commit-hash1> <commit-hash2> <commit-hash3> //Aplicar vários commits em um branch


## Aplicação do comando
Usado para aplicar alterações específicas de commits em um branch diferente. É útil para corrigir bugs, incorporar funcionalidades específicas, evitar mesclagens desnecessárias e reorganizar commits.



# Git Revert
## Funcionamento

- O comando git revert pode ser considerado um comando do tipo "desfazer"; no entanto, ele não é uma operação tradicional de desfazer. Em vez de remover o commit do histórico do projeto, ele descobre como inverter as alterações introduzidas pelo commit e anexa um commit novo com o conteúdo resultante. Assim, ele evita que o Git perca o histórico, o que é importante para a integridade do histórico de revisão e para uma colaboração confiável.

- O processo de reversão deve ser usado quando você quer aplicar o inverso do commit do histórico do projeto. Isso pode ser útil, por exemplo, se você estiver acompanhando um bug e descobrir que ele foi introduzido por um único commit. Em vez de ir até ela por conta própria, corrigir e confirmar um novo snapshot, você pode usar o git revert para fazer tudo isso na hora.

## Sintaxe

- git revert HEAD~3
Reverta as alterações especificadas pelo quarto último commit em HEAD e crie um novo commit com as alterações revertidas.

- git revert -n master~5..master~2
Reverta as alterações feitas por commits do penúltimo commit no master (incluído) para o penúltimo commit no master (incluído), mas não crie nenhum commit com as alterações revertidas. A reversão apenas modifica a árvore de trabalho e o índice.

## Aplicação do comando

O comando git revert é uma operação de desfazer avançada que oferece um método seguro de desfazer alterações. Em vez de excluir ou tornar commits órfãos no histórico de commits, uma reversão vai criar um commit novo que inverte as alterações especificadas. O git revert é uma alternativa mais segura que o git reset em relação à perda de trabalho. Para demonstrar os efeitos do git revert, foram abordados outros comandos que têm uma documentação mais aprofundada nas páginas individuais: git log, git commit e git reset.

# Git rebase: 

## Sobre a troca de base do Git

### Um exemplo de uso de git rebase:

O comando git rebase permite alterar com facilidade uma variedade de commits, modificando o histórico do seu repositório. É possível reordenar, editar ou combinar commits por squash.
Normalmente, você usará git rebase para:
Editar mensagens anteriores do commit
Combinar vários commits em um
Excluir ou reverter commits que não são mais necessários

### Fazer rebase de commits em um branch

Para fazer rebase de todos os commits entre outro branch e o estado do branch atual, você pode inserir o seguinte comando no shell (ou o prompt de comando para Windows, ou o terminal para Mac e Linux):

`git rebase --interactive OTHER-BRANCH-NAME`

## Comandos disponíveis ao fazer rebase

Há seis comandos disponíveis para fazer rebase:

### pick
pick significa simplesmente que o commit está incluído. A reorganização da ordem dos comandos pick altera a ordem dos commits quando a troca de base está em andamento. Se você optar por não incluir um commit, será preciso excluir a linha toda.

### reword
O comando reword é semelhante a pick, mas depois que você usá-lo, o processo de troca de base será colocado em pausa e dará a você a chance de alterar a mensagem de commit. As alterações feitas pelo commit não são afetadas.

### edit
Se você optar por edit um commit, terá a chance de alterar o commit, o que significa que pode adicionar ou alterar o commit por completo. Também é possível fazer mais commits antes de continuar com o rebase. Isso permite que você divida um commit grande em commits menores ou remova alterações equivocadas feitas em um commit.

### squash
Esse comando permite combinar dois ou mais commits em um único commit. Um commit é combinado por squash no commit acima dele. O Git permite que você grave uma nova mensagem do commit descrevendo ambas as alterações.

### fixup
Isso é semelhante a squash, mas o commit a ser mesclado tem a mensagem descartada. O commit simplesmente sofre merge no commit acima dele, e a mensagem do commit anterior é usado para descrever ambas as alterações.

### exec
Permite que você execute comandos de shell arbitrários em um commit.

## Um exemplo de uso de git rebase

Independentemente do comando usado, o Git iniciará o editor de texto padrão e abrirá um arquivo que fornece detalhes dos commits no intervalo escolhido. Esse arquivo é parecido com este:

pick 1fc6c95 Patch A
pick 6b2481b Patch B
pick dd1475d something I want to split
pick c619268 A fix for Patch B
pick fa39187 something to add to patch A
pick 4ca2acc i cant' typ goods
pick 7b36971 something to move before patch B

## Rebase 41a72e6..7b36971 onto 41a72e6
#
### Commands:
###  p, pick = use commit
###  r, reword = use commit, but edit the commit message
###  e, edit = use commit, but stop for amending
###  s, squash = use commit, but meld into previous commit
###  f, fixup = like "squash", but discard this commit's log message
###  x, exec = run command (the rest of the line) using shell
#
### If you remove a line here THAT COMMIT WILL BE LOST.
### However, if you remove everything, the rebase will be aborted.


## Ao dividir essas informações, de cima para baixo, observamos que:

- Sete commits são listados, o que indica que houve sete alterações entre nosso ponto de partida e o estado do nosso branch atual.

- Os commits escolhidos para rebase são classificados na ordem das alterações mais antigas (no topo) para as mais recentes (na base).

- Cada linha lista um comando (por padrão, pick), o SHA do commit e a mensagem de commit. Todo o procedimento git rebase gira em torno da manipulação dessas três colunas. As alterações feitas tem a base trocada no repositório.

- Após os commits, o Git informa o intervalo de commits com o qual estamos trabalhando (41a72e6..7b36971).

Por fim, o Git fornece alguma ajuda informando a você os comandos que estão disponíveis ao fazer rebase dos commits.


# Git squash
## Funcionamento
O Squash é utilizado para combinar vários commits em um único commit. 

Ele é útil quando você deseja simplificar o histórico de um branch, agrupando várias alterações relacionadas em um único commit coeso - o que faz com que seu histórico fique mais legível.

## Sintaxe
A sintaxe básica para realizar o "squash" é a seguinte:

`git rebase -i <commit-anterior-que-deseja-squash>
`

Ao executar esse comando, um editor de texto será aberto com uma lista de commits que serão editados. Você pode escolher qual commit deseja combinar com o commit anterior a ele.

Para combinar commits, você precisa substituir "pick" por "squash" (ou "s" para abreviar) nos commits que deseja squashar.

## Aplicação
- É geralmente útil quando você está trabalhando em uma *feature branch* e deseja simplificar o histórico antes de mesclá-lo ao *main branch*.

- Ajuda a manter um histórico de commits limpo e organizado, com mais clareza nas alterações implementadas.

- Pode ser usado para agrupar commits relacionados a uma única correção ou adição de recurso, facilitando a revisão de código e a compreensão do trabalho realizado.
