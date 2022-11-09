<h1> Algumas anotações das aulas para iniciantes: </h1>

Apresentação do terminal <br/>
terminal é sensitivo ( diferencia maiúsculas de minúsculas)  <br/>

clear -> limpa a tela (tecla ctrl da esquerda + l)  <br/>
$ -> usuário com restrição # -> super usuário ou root   <br/>

<h3> >>>>>> NAVEDAR NOS DIRETÓRIOS</h3>
pwd >> mostra onde você esta (em que pasta)   <br/>
~   >> pasta do usuário   <br/>
/   >> diretório raiz   <br/>
cd  >> pra onde ir   <br/>
       cd / > raiz | cd .. > volta um diretório | cd .. /pasta  <br/>
       cd ~ > vai direto para a pasta do usuário  <br/>
ls  >> listar arquivos  <br/>
       ls -(esc,esc) para listar parametros   <br/>  <br/>

<h3> >>>>>> FILTRAR EXIBIÇÃO DE ARQUIVOS</h3>
cd  >> tab 2x mostra os diretórios, preenche o nome auto  <br/>
ls *>>  ls p* lista arquivos e diretórios com a letra p  <br/>
ls p?n*>> lista os arquivos que iniciam com p não sei a 2 letra e 3 é n*  <br/>
---- pode ser substituir qualquer letra ex: ?sh* -- ssh_  <br/>
ls []>> listar/copiar arquivos em sequecia ls arquivo[1-3]* / arquivo[2,5]  <br/>
	nao quero listar algum arquivo ls arquivo[^3,9]* ou intervalo[^1-3]  <br/>
ls --help>> lista os parametros e identifica o que faz  <br/>
man ls>> mesma função mas em forma de arquivo de texto, pra sair (q)  <br/>  <br/>
 
<h3> >>>>>> LOCALIZAR ARQUIVOS </h3>
find -parametro >> busca a partir do diretório local seguindo o parametro  <br/>
                ex: find -name arquivo* (vai buscar diretório/documento com o nome arquivo)  <br/>
		tem outros parametros find -(tab+tab) mostra todo os paramentros de busca  <br/>  <br/>

<h3> >>>>>> CRIAR DIRETÓRIOS</h3>
precisa ter permissão ou usar o root (sudo mkdir) em diretórios do sistema  <br/>
mkdir>>  ex: mkdir Documentos (cria pasta Documentos)   <br/>
    	 para criar com espaço ex: mkdir 'Meus Documentos'  <br/>
mv  >> mover ex: mv texto1.txt Documentos/   <br/>
cp  >> copia ex: cp texto3.txt Documentos/  <br/>
rm  >> remover:   <br/>
rmdir>> remove diretórios (vazios)  <br/>
rm -rf>> remove diretórios (não vazios)  <br/>  <br/>

<h3> >>>>>>> DAR SENHA PARA O ROOT (UBUNTU)</h3>
1- sudo passwd root   <br/>
2- digitar a senha do seu usuário  <br/>
3 4- digitar senha do root  <br/>
logar com o root: <br/>
5- su  <br/>
6- por a senha root (ja estará com o root@usuario#)  <br/>
sair do usuario root para o seu: <br/>
7- su nomedousuario  <br/>  <br/>

acesso root por ssh  <br/>
editar aquivo de permissão: sudo nano /etc/ssh/sshd_config  <br/>
#PermitRootLogin prohibit-password ---> PermitRootLogin yes (remover o comentário # e permitir)  <br/>  <br/>


<h3> >>>>>>> EDIÇÃO DE TEXTO POR LINHA DE COMANDO</h3>
caso não exista o aqruivo que você digitar os dois criam (vi, nano)  <br/>
vim/vi >> cria/edita arquivo + (i) habilita ISERT de texto + (esc):wq salva e sai da edição  <br/>
nano>> (ctrl+o) salva (ctrol+x) sair   <br/>
touch >> cria um arquivo em branco ex: arquivo1.txt   <br/>  <br/>
    

<h3> >>>>> HISTÓRICOS DE COMANDO</h3>
history   <br/>
history | grep "comando"   <br/>
para exibir mais detalher de cada comando, editar hambiente do history:  <br/>
export HISTTIMEFORMAT="%c"  <br/>

<h3> >>>>>>>>>>>>>>>>>>> CRIANDO USUÁRIOS</h3>
useradd --help  <br/>
userdel -f  <br/>
user add joao -m pasta do usuario / -c nome completo "João da Silva"/ -s /bin/bash / -e 15/11/2022 data de expiração /   <br/>
passwd usuario --- por senha  <br/>
usermod --- mudar configurações do usuario  <br/>
cat /etc/passwd --- consultar funções do usuario  <br/>
>>criando usuários por script:  <br/>
useradd convidado -m -s /bin/bash/ -p $(openssl passwd aa)  <br/>  <br/>


nano criar_usuarios.sh   <br/>

-------------------------------
#!/bin/bash  <br/>

echo:"Criando usuários do sistema...."  <br/>

useradd guest1 -c "usuario convidado" -s /bin/bash -m -p $(openssl passwd aa) -G grupo  <br/>
passwd guest1 -e   <br/>
#para usuario refazer a senha no 1 acesso  <br/>

useradd guest2 -c "usuario convidado" -s /bin/bash -m -p $(openssl passwd aa) -G grupo  <br/>

echo "Usuarios criados..."  <br/>

--------------------------------

para poder executar o script, precisa alterar a permissão do arquivo:  <br/>
chmod +x criar_usuarios.sh (vai mudar de cor quando der um ls)  <br/>
./criar_usuarios.sh >>>>>>pra executar o script  <br/>  <br/>

<h3> >>> adicionar usuários a grupos</h3>
usermod -G adm,sudo usuario  <br/>
>>> criando novos grupos  <br/>
cat /etc/group------> verificar os grupos existentes e seus usuários  <br/>
groupadd -----> adicona novos grupos  <br/>
usermor -G gruposdestino usuario ---> remover de todos os grupos atuais/mover para os grupos desejados  <br/>
gpasswd -d usuario grupoquequerremover -----> remove apenas do grupo indicado  <br/>  <br/>

<h2> >>>PERMISSÕES</h2>
drwxr-xr-x (- tipo --- dono --- grupo --- outros)  <br/>
-rw-rw-r--  <br/>
- arquivo  <br/>
d diretório  <br/>
r leitura (read)  <br/>
w gravação (write)  <br/>
x execução (execute)  <br/>
formas numericas para representar permissões:  <br/>
4 (r) leitura  <br/>
2 (w) gravação   <br/>
1 (x) execução  <br/>
0 (nenhuma)   <br/>  <br/>

permissão total: 7  <br/>
leitura e execução: 5  <br/>
nenhuma: 0  <br/>

ex:  <br/>
chmod 750 /diretório/ ---> dono (7) grupo (5) outros (0) novas permissões para o diretório/arquivo  <br/>
chown dono:grupo /diretório/  ---->> alterar dono e o grupo do diretório  <br/>


