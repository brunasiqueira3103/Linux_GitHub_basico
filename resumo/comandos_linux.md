<h1> Algumas anotações das aulas para iniciantes: </h1>

Apresentação do terminal
terminal é sensitivo ( diferencia maiúsculas de minúsculas ) 

clear -> limpa a tela (tecla ctrl da esquerda + l)
$ -> usuário com restrição # -> super usuário ou root

<h3> >>>>>> NAVEDAR NOS DIRETÓRIOS</h3>
pwd >> mostra onde você esta
~   >> pasta do usuário
/   >> diretório raiz 
cd  >> pra onde ir 
       cd / > raiz | cd .. > volta um diretório | cd .. /pasta
       cd ~ > vai direto para a pasta do usuário
ls  >> listar arquivos
       ls -(esc,esc) para listar parametros 

<h3> >>>>>> FILTRAR EXIBIÇÃO DE ARQUIVOS</h3>
cd  >> tab 2x mostra os diretórios, preenche o nome auto
ls *>>  ls p* lista arquivos e diretórios com a letra p
ls p?n*>> lista os arquivos que iniciam com p não sei a 2 letra e 3 é n*
---- pode ser substituir qualquer letra ex: ?sh* -- ssh_
ls []>> listar/copiar arquivos em sequecia ls arquivo[1-3]* / arquivo[2,5]
	nao quero listar algum arquivo ls arquivo[^3,9]* ou intervalo[^1-3]
ls --help>> lista os parametros e identifica o que faz
man ls>> mesma função mas em forma de arquivo de texto, pra sair (q)
 
<h3> >>>>>> LOCALIZAR ARQUIVOS </h3>
find -parametro >> busca a partir do diretório local seguindo o parametro
                ex: find -name arquivo* (vai buscar diretório/documento com o nome arquivo)
		tem outros parametros find -(tab+tab) mostra todo os paramentros de busca

<h3> >>>>>> CRIAR DIRETÓRIOS</h3>
precisa ter permissão ou usar o root (sudo mkdir) em diretórios do sistema
mkdir>>  ex: mkdir Documentos (cria pasta Documentos) 
    	 para criar com espaço ex: mkdir 'Meus Documentos'
mv  >> mover ex: mv texto1.txt Documentos/ 
cp  >> copia ex: cp texto3.txt Documentos/
rm  >> remover: 
rmdir>> remove diretórios (vazios)
rm -rf>> remove diretórios (não vazios)

<h3> >>>>>>> DAR SENHA PARA O ROOT (UBUNTU)</h3>
1- sudo passwd root 
2- digitar a senha do seu usuário
3 4- digitar a nosa senha do root
logar com o root 5- su
6- por a senha root (ja estará com o root@usuario#)
sair do usuario root para o seu 7- su nomedousuario

acesso root por ssh
editar aquivo de permissão: sudo nano /etc/ssh/sshd_config
#PermitRootLogin prohibit-password ---> PermitRootLogin yes (remover o comentário # e permitir)


<h3> >>>>>>> EDIÇÃO DE TEXTO POR LINHA DE COMANDO</h3>
caso não exista o aqruivo que você digitar os dois criam (vi, nano)
vim/vi >> cria/edita arquivo + (i) habilita ISERT de texto + (esc):wq salva e sai da edição
nano>> (ctrl+o) salva (ctrol+x) sair 
touch >> cria um arquivo em branco ex: arquivo1.txt 
    >> 

<h3> >>>>> HISTÓRICOS DE COMANDO</h3>
history 
history | grep "comando" 
para exibir mais detalher de cada comando, editar hambiente do history:
export HISTTIMEFORMAT="%c "

<h3> >>>>>>>>>>>>>>>>>>> CRIANDO USUÁRIOS</h3>
useradd --help
userdel -f
user add joao -m pasta do usuario / -c nome completo "João da Silva"/ -s /bin/bash / -e 15/11/2022 data de expiração / 
passwd usuario --- por senha
usermod --- mudar configurações do usuario
cat /etc/passwd --- consultar funções do usuario
>>criando usuários por script:
useradd convidado -m -s /bin/bash/ -p $(openssl passwd aa)


nano criar_usuarios.sh 

#!/bin/bash

echo:"Criando usuários do sistema...."

useradd guest1 -c "usuario convidado" -s /bin/bash -m -p $(openssl passwd aa) -G grupo
passwd guest1 -e 
#para usuario refazer a senha no 1 acesso

useradd guest2 -c "usuario convidado" -s /bin/bash -m -p $(openssl passwd aa) -G grupo

echo "Usuarios criados..."

para poder executar o script, precisa alterar a permissão do arquivo:
chmod +x criar_usuarios.sh (vai mudar de cor quando der um ls)
./criar_usuarios.sh >>>>>>pra executar o script

<h3> >>> adicionar usuários a grupos</h3>
usermod -G adm,sudo usuario
>>> criando novos grupos
cat /etc/group------> verificar os grupos existentes e seus usuários
groupadd -----> adicona novos grupos
usermor -G gruposdestino usuario ---> remover de todos os grupos atuais/mover para os grupos desejados
gpasswd -d usuario grupoquequerremover -----> remove apenas do grupo indicado

<h2> >>>PERMISSÕES</h2>
drwxr-xr-x (- tipo --- dono --- grupo --- outros)
-rw-rw-r--
- arquivo
d diretório
r leitura (read)
w gravação (write)
x execução (execute)
formas numericas para representar permissões:
4 (r) leitura
2 (w) gravação 
1 (x) execução
0 (nenhuma) 

permissão total: 7
leitura e execução: 5
nenhuma: 0

ex:
chmod 750 /diretório/ ---> dono (7) grupo (5) outros (0) novas permissões para o diretório/arquivo
chown dono:grupo /diretório/  ---->> alterar dono e o grupo do diretório


