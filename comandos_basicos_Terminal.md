# Por que usar um terminal?
- Conhecer o terminal de comandos é um recurso interessante, pois muitas ferramentas no setor de desenvolvimento não possuem uma interface gráfica.

## Abrir o prompt de comando
- O primeiro passo é abrir um terminal (ou console). No mundo Windows, esse terminal se chama Prompt de comando ou, abreviando, cmd. 
- Para abrir um novo terminal, devemos ir em Todos os Programas (ícone do Windows que normalmente fica no canto inferior esquerdo), digitarmos cmd e apertarmos Enter. Outra forma de abrir o Prompt é pelo atalho Botão Iniciar + R e no campo de pesquisa digitar cmd.

## Listando arquivos
- Para listar todos os arquivos em diretórios, usamos o comando dir e então recebemos uma lista dos arquivos e pastas existentes.

## Navegando entre diretórios
- Para mudarmos de pasta, utilizamos o comando cd (change directory) seguido do nome da subpasta. Por exemplo: cd Documents. Para voltarmos ao diretório anterior, usamos o comando cd ...

## Criando diretórios
- Para criarmos diretórios, usamos o comando mkdir (make directory). Lembre-se de evitar acentos e espaços nos nomes de arquivos e diretórios. Uma boa boa prática é usar o caractere _ ao invés do espaço ao criar diretórios.

## Trabalhando com arquivos
- Para mover arquivos ou pastas, utilizamos o comando move e indicamos o arquivo com o nome completo (incluindo o caminho dos diretórios). Por exemplo: move ..\Desktop\texto.txt . Já para conferir o conteúdo de um arquivo, usamos o comando type, como em type texto.txt.

- Para a função de copiar um arquivo, utilizamos o comando copy, como em copy texto.txt texto2.txt. Já para renomear um arquivo, utilizamos o comando rename seguido do nome original do arquivo e o nome que desejamos aplicar, como em rename texto2.txt mensagem.txt. E, por fim, para apagar um arquivo, utilizamos o comando del seguido do nome do arquivo que se deseja deletar, por exemplo, del texto.txt.

## Limpando o terminal
- Com o tempo, o terminal vai ficar poluído com comandos antigos, que tiram o foco e dificultam a legibilidade. Para limpar o terminal, utilizamos cls (clear screen).
