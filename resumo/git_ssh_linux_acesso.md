<h1> PROCESSO: </h1>
<li> 0- instalar o git na sua máquina (local ou virtual p.r.e.c.i.s.a, em cada máquina, sem choro!:sob:) </li> <br/>
<li> 1- gerar par de chaves (publica-privada) pelo terminal  (gere e guarde, pode ser em um repositório privado ex.) </li> <br/>
<li> 2- adicionar no github (chave publica) no web site do github   </li> <br/>
<li> 3- iniciar o SSH agent via terminal e fazer autenticação com a chave privada  </li> <br/>
<li> 4- usar o GIT/GITHUB localmente xuxuzinhos (bora lá)  </li> <br/><br/>


<h1> 0- INSTALAR O GIT NA MÁQUINHA </h1>
>> https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git <br/>
sudo apt-get install git-all -y (estou usando UBUNTU na minha MV) <br/>
git --version ---> se foi instalado corretamente vai mostar a versão <br/><br/>


<h1> 1- GERAR PAR DE CHAVES </h1>
ssh-keygen -t ed25519 -C seuemaildogithub
>>vai pedir um nome para sua chave, caso não coloque ele vai gerar nome padrão ed25519
>>vai pedir uma senha para sua chave
>>confirme a senha (tente lembrar dessa senha kkkkk :clown_face:)
>> ele vai salvar o par de chaves no caminho indicado no prompt o meu foi (/c/Users/Bruna/.ssh) esteja dentro da pasta ou saiba o caminho correto para o prox. passo:
cat suachave.pub ----> vai imprimir no terminal o conteúdo da chave, copie para por no github, na proxima etapa. <br/><br/>


<h1> 2- ADICIONAR CHAVE PUBLICA NO GITHUB (ONLINE) </h1>
vá ate sua foto perfil, settings (https://github.com/settings/keys)
>new ssh key
>>Title: coloque o apelido da sua chave, para identificar qual é (qual máquina por exemplo)
>>Key: cole o que copiou da chave publica aqui, e salva...(voltando pro prompt) <br/><br/>


<h1> 3- INICIAR SSH AGENT E AUTENTICAR COM CHAVE PRIVADA </h1>
eval $(ssh-agent -s) ------> vai dar uma mensagem de agent pid **** algum numero ok) <br/>
ssh-add chaveprivada ----> (importante estar na pasta da chave, facilita, caso não passe o caminho da chave), <br/>
>>vai pedir a senha, se a autenticação der certo deve aparecer a seguinte mensagem: <br/>
Identity added: id_ed25519 (seuemaildogithub) <br/><br/>

protinho a autenticação foi feita, para usar o git agora lembre-se sempre de navegar para a pasta onde <br/>
quer clonar seu repositório, eu não fiz isso, então meu repositório ficou dentro da pasta das chaves hehehe <br/>
furada né! (NAVEGUE ATÉ A PASTA DO SEU PROJETO PARA CLONAR O REPOSITÓRIO LÁ) <br/><br/>

Na pasta que você quer clonar seu repositório dê os comandos do passo a passo do github  <br/> <br/>

 
Esses aqui, serão sempre executados: <br/>
git config --global user.email "seu@email" <br/>
git config --global user.name "usuariogithub"<br/> <br/>

 1- Se deseja "subir arquivos locais para um repositório vazio no github" <br/>

git init  <br/>
git add    --->(NOME DO SEU ARQUIVO, OU PARA TODOS BASTA POR UM .) <br/>
git commit -m "SUA MENSAGEM DE COMMIT" <br/>
git branch -M main <br/>
git remote add origin (O LINK DO SEU REPOSITÓRIO, VERIFICAR LINK COM SSH) <br/>
git push -u origin main <br/>

<br/><br/>

2- Se deseja "baixar arquivos do github para sua máquina local" <br/>
git init (para dar inicio no git no repositório local) <br/>
git clone  (O LINK DO SEU REPOSITÓRIO, VERIFICAR LINK COM SSH) <br/>

<br/><br/>

3- SEMPRE que tiver alterações locais faça o passo 1, caso as alterações estejam no github faça sempre o pull pra manter atualizado na sua máquina local.<br/>
git pull  (baixa do github as "atualizações) <br/>

<br/><br/>

Eu utilizo o github desktop no minha máquina Windows, altero os arquivos pelo VScode, faço meu push (subo as alterações para o github). <br/>
Na nos meus servidores de estudo (VirtualBox, AWS) faço o pull, e mantem sempre atualizado os scripts. <br/>

<br/><br/>

Espero ter te ajudado ;D <br/>
