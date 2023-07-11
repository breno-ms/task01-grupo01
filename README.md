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


# `git squash`

## Funcionamento
O Squash é utilizado para combinar vários commits em um único commit. 

Ele é útil quando você deseja simplificar o histórico de um branch, agrupando várias alterações relacionadas em um único commit coeso - o que faz com que seu histórico fique mais legível. O squash é especialmente útil antes de enviar um pull request ou mesclar um ramo em outro ramo principal.