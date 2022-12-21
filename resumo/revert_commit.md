# ==== como reverter um commit ====

## --- Online:

Para reverter um commit no GitHub, você pode usar o recurso de "revert commit" do GitHub. Aqui estão os passos para fazer isso:
Vá até a página de commit que você deseja reverter no GitHub. Você pode encontrar a página de commit seguindo o link para o commit
na página de histórico de commits ou clicando no número do commit na lista de commits.

- Clique no botão "Revert this commit" na página de commit.

- Crie um novo commit de reverter. Você pode fazer isso clicando no botão "Create a new commit" na página de confirmação de reverter commit. 
Isso criará um novo commit que reverte as alterações do commit original.

- Envie o novo commit de reverter para o repositório. Você pode fazer isso clicando no botão "Push changes" na página de confirmação de reverter commit. 
Isso enviará o novo commit de reverter para o repositório e revertê as alterações do commit original.


## --- Linha de comando:
Para reverter um commit no GitHub usando o CLI (interface de linha de comando), você pode usar o comando git revert. Aqui estão os passos para fazer isso:

- Abra o terminal e navegue até o diretório do seu repositório local.

- Use o comando 'git log' para ver a lista de commits no seu repositório. Anote o ID do commit que você deseja reverter.

- Use o comando 'git revert' seguido do ID do commit para reverter o commit. Por exemplo: 'git revert abc123'. Isso criará um novo commit que reverte as 
alterações do commit original.

- Envie o novo commit de reverter para o repositório. Você pode fazer isso com os comandos 'git push' se você estiver usando o GitHub remoto ou 
'git push origin master' se estiver usando outro servidor remoto.


## Observação: 
o revert commit cria um novo commit que reverte as alterações do commit original. Isso é diferente de excluir o commit original, 
que apagará as alterações do commit da história do repositório.



