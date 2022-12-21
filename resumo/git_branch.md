# Git Branch

## Git branch é uma funcionalidade do Git que permite a criação de uma nova linha de desenvolvimento em um projeto. 

### Quando você cria uma nova branch, você está criando uma cópia do código em um ponto específico no tempo, e pode fazer alterações no código na nova branch sem afetar o código na branch principal (geralmente chamada de "master"). Isso permite trabalhar em vários recursos ou correções de bugs ao mesmo tempo sem afetar a base de código principal.

# Para criar uma nova branch no Git, você pode usar o comando **git branch** seguido pelo nome da nova branch. Por exemplo:

$$
git branch nova-funcionalidade 
- Isso criará uma nova branch chamada "nova-funcionalidade" com base no estado atual do código.

#### Para mudar para uma branch diferente, você pode usar o comando git checkout seguido pelo nome da branch para a qual deseja mudar. Por exemplo:

$$
git checkout nova-funcionalidade
- Isso mudará para a branch "nova-funcionalidade" e você poderá fazer alterações no código nessa branch.

### Quando estiver pronto para mesclar as alterações da branch de volta para a base de código principal, você pode usar o comando git merge para mesclar as alterações da branch na branch principal.
