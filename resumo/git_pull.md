# == Git Pull

## O Git pull é uma operação que baixa as alterações de um repositório remoto para a sua cópia local do projeto. Ele é usado para atualizar a cópia local do projeto com as alterações feitas por outras pessoas no repositório remoto.

- Para realizar um pull, você precisa ter um repositório remoto configurado com o qual deseja sincronizar as alterações. 

- Isso é geralmente feito usando o comando git remote add, que adiciona um novo repositório remoto ao projeto local.

- Para baixar as alterações do repositório remoto, basta usar o comando git pull seguido pelo nome do repositório remoto e pelo nome da branch que deseja baixar. Por exemplo:

$ git pull origin master
- Isso baixará todas as alterações feitas na branch "master" do repositório remoto chamado "origin" e as aplicará à sua cópia local do projeto.

### Observe que, depois de realizar um pull, pode ser necessário resolver conflitos se houver alterações conflitantes entre a cópia local e a cópia remota do projeto. Isso pode ser feito manualmente editando os arquivos em conflito e adicionando-os novamente com o comando git add antes de realizar um commit das alterações com o comando git commit.



