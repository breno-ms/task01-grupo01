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