====================================
PROCESSO:
0- instalar o gir na sua máquina (local ou virtual p.r.e.c.i.s.a, em cada máquina, sem choro!)
1- gerar par de chaves (publica-privada) pelo terminal
2- adicionar no github (chave publica) na web site do github 
3- iniciar o SSH agent via terminal e fazer autenticação com a chave privada
4- usar o GIT/GITHUB localmente xuxuzinhos (bora lá)

========================================================================
************************************************************************
========================================================================

0- INSTALAR O GIT NA MÁQUINHA
>> https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git
sudo apt-get install git-all -y
git --version ---> se foi instalado vai mostar a versão

========================================================================
************************************************************************
========================================================================

1- GERAR PAR DE CHAVES
ssh-keygen -t ed25519 -C seuemaildogithub
>>vai pedir o nome para sua chave, caso não coloque ele vai gerar nome padrão ed25519
>>vai pedir uma senha para sua chave
>>confirme a senha (tente lembrar dessa senha kkkkk)
>> ele vai salvar o par no caminho indicado no prompt o meu foi (/c/Users/Bruna/.ssh) esteja dentro da pasta ou saiba o caminho correto para o prox. passo:
cat suachave.pub ----> vai imprimir no terminal o conteúdo da chave, copie para por no github, na proxima etapa.

========================================================================
************************************************************************
========================================================================

2- ADICIONAR CHAVE PUBLICA NO GITHUB (ONLINE)
vá ate sua foto perfil, settings (https://github.com/settings/keys)
>new ssh key
>>Title: coloque o apelido da sua chave, para identificar qual é (qual máquina por exemplo)
>>Key: cole o que copiou da chave publica aqui, e salva...(voltando pro prompt)

========================================================================
************************************************************************
========================================================================

3- INICIAR SSH AGENT E AUTENTICAR COM CHAVE PRIVADA
eval $(ssh-agent -s) ------> vai dar uma mensagem de agent pid **** algum numero ok)
ssh-add chaveprivada ----> (importante estar na pasta da chave, facilita, caso não passe o caminho da chave),
>>vai pedir a senha, se a autenticação der certo deve aparecer a seguinte mensagem:
Identity added: id_ed25519 (seuemaildogithub)

protinho a autenticação foi feita, para usar o git agora lembre-se sempre de navegar para a pasta onde
quer clonar seu repositório, eu não fiz isso, então meu repositório ficou dentro da pasta das chaves hehehe
furada né! (NAVEGUE ATÉ A PASTA DO SEU PROJETO PARA CLONAR O REPOSITÓRIO LÁ)

Na pasta que você quer clonar seu repositório dê os comandos do passo a passo do github

Aqui eu personalizei o meu hehehe


git add REDME.md     --->(NOME DO SEU ARQUIVO, OU PARA TODOS BASTA POR UM .)
git commit -m "SUA MENSAGEM DE COMMIT"
git branch -M main
git remote add origin (O LINK DO SEU REPOSITÓRIO, VERIFICAR LINK COM SSH)
git push -u origin main


====================================
