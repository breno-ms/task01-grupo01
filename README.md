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