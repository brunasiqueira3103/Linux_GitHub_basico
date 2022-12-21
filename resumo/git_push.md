# == Git Push

## O Git push é uma operação que envia as alterações localmente realizadas para um repositório remoto. Ele é usado para publicar as alterações que você fez em sua cópia local do projeto no repositório remoto, onde outras pessoas podem ver e acessar as alterações.

- Para realizar um push, você precisa ter um repositório remoto configurado com o qual deseja sincronizar as alterações. Isso é geralmente feito usando o comando git remote add, que adiciona um novo repositório remoto ao projeto local.

- Para enviar suas alterações para o repositório remoto, basta usar o comando git push seguido pelo nome do repositório remoto e pelo nome da branch que deseja enviar. Por exemplo:

$ 
git push origin master
- Isso enviará todas as alterações que você fez na branch "master" localmente para o repositório remoto chamado "origin".


### Observe que, antes de realizar o push, é necessário fazer um commit das alterações localmente com o comando git commit. Isso inclui as alterações em um commit, o que as torna permanentes na história do projeto e as torna prontas para serem enviadas para o repositório remoto.
