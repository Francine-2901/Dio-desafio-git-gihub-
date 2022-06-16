### Entendendo o que é Git e sua importância:

Git é um sistema de direcionamento de código.
Ex. de jornalista que tem que entregar um reportagem, faz rascunhos de redações, vai apresentando ao chefe/supervisor verificar e vai criando outros rascunhos com as alterações e depois quando estiver alinhado da forma correta é gerado a redação final.



### Comandos básicos para um bom desempenho no terminal:

GUI - Graphical User Interface interage por meio de interface gráfica, clicar, teclar, arrastar é diferente do CLI - Command line interface que interage com um linha de comando, é usado nesta aula sobre Git.

Aprendemos alguns comandos: usados no Prompt de comando(no próprio pc)

cd -para navegar entres as pastas e pastas de pastas...
dir - para listas o que tem dentro da pasta que está usando
mkdir - para criar um nova pasta ou arquivo
del ou rmdir - para deletar
cls - para limpar o terminal

**Dica:** Quando for digitar o nome de alguma pasta ou arquivo, quando digita o início e apertar o TAB, ele automaticamente identifica a pasta e completa o nome, ajuda a reduzir o tempo.



### Realizando a instalação do GIT:

Usando o site oficial: https://git-scm.com/
Passo a passo:

Downloading for windows (versão deste período foi 2.33.0.2)>
Escolher o instalador, vai abrir um popup, clicar em next >
Verificar se as opções Git Basch Here e Git GUI Here estão seleciondas e next
Depois selecionar o editor padrão, recomendado ‘Vim’ e next
Na tela seguinte, é recomendado deixar em “Let Git decide” e next
As próximas 3 fases mantêm e clica em next
Na tela seguinte, se for windows na primeira opção ou se for Mac na segunda e next
Next nas 2 próximas telas > É recomendado usar a “Git credential manager core” e next
Next e install. Ok

Para se certificar que foi instalado, clicar no simbolo do windows no teclado ou na tela e digitar “Git”



### Tópicos fundamentais para entender o funcionamento do Git:

A sigla <u>SHA</u> significa Secure Hash Algorithm, é um conjunto de funções hash criptográficas projetadas pela NSA (agência de segurança nacional dos EUA). Se tem um arquivo de texto roda o arquivo no Git ele gera um caracteres de identificador de 40 dígitos, se for alterado uma vírgula, gera outro identificado diferente.
É uma forma curta de representar um arquivo.

Na área de trabalho clicar como direito do mouse e clicar em Git Bash Here.

**Nota Fran**: Ideal criar um arquivo com um textinho curto ou frase para usar no bloco de notas para testar como funciona um SHA1.

Digita openssl sha1 texto.txt(nome do arquivo do bloco de notas) e enter>
Em seguida vai mostrar o código de 40 caracteres. podem ser feitos testes alterando um vírgula/letra e fazer o mesmo processo, vai mostrar outro identificador de 40 caracteres.
O Git é um sistema distribuído seguro



### Objetos internos do Git:

*São 3 tipos básicos:*

**Blobs** - Tem o tipo do objeto, o tamanho da string/arquivo usa \0 e o arquivo. Apresenta o nome do tipo de objeto, tamanho por sha1(códigos específicos 40 caract) 

**Trees** - Armazena e apontando p os tipos de blobs diferentes ou outras árvores, tem o \0. Já as árvores apresentam ñ somente apresenta como sha1 como, nome, pasta específica.

**Commit** - Junta tudo e dá sentido à interação do Git. O sha1 desse commit é o hash de toda essa informação.



### Chave SSH e Token:

São formas de autenticação seguras do GitHub
**Chave SSH** - é uma forma de estabelecer uma conexão segura encriptada entre duas máquinas.

**Token de acesso pessoal** - Se assemelha mais ao processo de digitar nickname e senha, não tem a vantagem de não requerer senha como no SSH. Sempre que fizer um commit o Git pede usuário e senha.

Nota Fran: Ideal criar um cadastro no site do github para ir praticando junto com as aulas.

Aprendemos alguns comandos: usado no GitBash instalado no pc.

- cd - para navegar entres as pastas e pastas de pastas...

- ls - para listas o que tem dentro da pasta que está usando

- mkdir - para criar um nova pasta ou arquivo

- rm -rf (nome da pasta/arquivo).git - para deletar/remover

- -a para ver arquivos ocultos

- ctrl + L - para limpar

  

<u>Agora entrado no GitBash vamos criar SSH</u>

ssh-keygen -t ed(código) -C (email cadastrado no github.com) e enter >Enter novamente
Em seguida vai mostrar as informações de Identificação e chave pública foram salvas. E a imagem de um tipo de criptografia usada (The key fingerprint’)

Usar o seguinte comando

cd /c/Users/(nome user do pc)/.ssh/ e enter > ls (LS), enter e vão mostrar as chaves

Usar outro comando para ver a o código da chave pública

cat id_ed(código).pub e enter. Vai mostrar o código. Vamos copiar esse código e colar no Github (site) para gerar uma chave.

Agora no site, vai em na setinha para baixo▼ ao lado da foto de perfil e em settings/definições

No lado esquerdo terá um coluna, clicar na opção ‘SSH and GPS keys’

Digitar o título, colar aquele código da chave pública copiado anteriormente e ‘Add SSH key’
Obs: Em alguns casos pode solicitar uma senha para autenticação antes de gerar.

ls e enter > cd(nome da pasta usada 'ex.domentos') e enter > ls e entar > cd. ssh/ e enter

Depois pode usar o comando pwd para ver o caminho completo > pwd e enter > /c/Users/ (nome user do pc)/.ssh

Digitar eval $(ssh-agent -s) e enter. Vai mostrar o número que está startando um processo
Agente pid (código - esse número pode variar). E continua com o seguinte comando

ls e enter > mostra as duas chaves.

ssh-add id_ed(código) e enter.
Pode pedir uma senha digitar ou só apertar o enter e ok. Vai confirmar que foi adicionada ao email cadastrado nos comandos e no site do Github.

Para “colocar pra funcionar" vamos clonar um repositório do site do GitHub.

Antes disso criar um repositório, caso já tenha pode clonar um já existente.

P criar vamos na setinha ▼ ao lado da foto de perfil e settings/definições
Na coluna do lado esquerdo ir em repositories/repositórios.

Em Repositórios, clicar em novo repositório. > Digitar um nome, neste caso é recomendado usar privado, pode já criar um arquivo README.md clicando na opção e ‘Criar repositório'

Clica em code/ código, clicar em SSH e copiar o link

Volta para o Git instalado no pc e criar 1 pasta chamada ‘ssh-test’

Agora acessar esta pasta

cd e enter > ls e enter > cd workspace > ls e enter > cd ssh-test e enter. Ok

Digitar o seguinte comando para clonar:

git clone (colar o link copiado no site do git) e enter
Vai mostrar algumas infos e uma pergunta que responderemos “yes” e enter.
Vai confirmar que clonou por meio da chave SSH

Digita ls e enter, vai mostrar o repositório > Voltando no GitHub a chave passa a ficar verde e confirmando a última vez que foi usada.



<u>Agora vamos usar uma senha Token.</u>

P criar vamos na setinha ▼ ao lado da foto de perfil e settings/definições
Na coluna do lado esquerdo ir em "developer settings/ config. do desenvolvedor”

Depois em Token de acesso pessoal e gerar novo token > Depois vai criar um nome, e neste caso ticar a opção “repo/ repositório” e ‘gerar token’ no final da tela.

**Anotar em um local seguro**, pois se sair da tela do código token e voltar ñ aparece novamente e precisará criar um novo código token.

Agora vamos no repositório, no mesmo local, setting > Repositórios > clica no rep já criado, ir em code e copiar código de HTML.

Volta para o Git instalado no pc e criar 1 pasta chamada ‘token-test’

cd e enter > ls e enter > cd workspace > ls e enter > mkdir token-test e enter.

Agora acessar esta pasta

cd e enter > ls e enter > cd workspace > ls e enter > cd token-test e enter. Ok

Digitar o seguinte comando para clonar:

git clone (link do código HTML do repositório) e enter

Vai pedir o token (personal access token), cola e enter.

Mostra o repositório clonado por meio do token de acesso pessoal.



### Iniciando o Git e criando um commit:

Para iniciar um repositório, vamos usar o ‘git init’
Para mover arquivos, atualizar e dar início, vamos usar o ‘git add’
Para criar commit vamos usar o ‘git commit ‘

**Criando um repositório.**

Acessar a pasta do diretório C: e ver se já foi criada a pasta workspace, caso ñ criar, antes de acessar a pasta , clicar com o direito em algum espaço em brando e depois clicar em “Git Bash Here”

Digitar ls e enter > cd workspace > ls e enter. Ok

Criar uma pasta, neste exemplo: mkdir livro-receitas e enter > cd livro-receitas e enter

Agora iniciar o git: git init e enter > ls e enter, não vai mostrar nada.

Usamos o comando -a para ver arquivos ocultos: ls -a e enter > mostra ./ ../ .git/

Criar um “link de conexão” entre o Git local e o Git remoto
git config --global user.email (email cadastrado no Github)
git config --global user.name (nome cadastrado no Github)

**Markdown**, é uma forma "mais humana" de se inscrever um arquivo HTML
As # definem o tamanho da letra, quanto mais # é usada o título fica menor.

Usar o <u>.md</u> para arquivos <u>markdown</u>

<u>Cont. criando um commit:</u>
Na pasta de livro-receitas no pc, clicar com o direito> novo> documento de texto
Colocar o nome de strogonoff.md, neste exemplo.

Abrir o programa Typora > digital para # para o título principal, neste caso,  # Strogonoff de Frango e enter. > para o 2º título usa, neste caso, ## Ingredientes
Terminar de digitar, formatar e salvar.

**Outros comandos:**

- Usar ** para negrito/destaque. Ex. **flor** fica flor
- Usar _ para itálico. Ex. _ flor_ fica *flor*
- Usar : para emoticons. Ex. :Flor vai mostrar as opções e selecione o emoticon 🌻
- Usar - e espaço para criar listas Ex. - espaço e flor fica • flor



Para mais funções de formatação, ir na barra de ferramentas, clicar em ‘help/ajuda’ > depois em ‘markdown reference’ e vai abrir um guia de instruções.

Usando o git add * e enter > git commit -m “commit inicial” e enter, para gerar o commit no git bash mostram o início número  de 40 caracteres do SHA1 identificando o commit.



### Passo a passo no ciclo de vida:

<u>Tracked</u> são arquivos que podem ser rastreados no git pode ter 3 estágios diferentes:

**<u>Unmodified</u>** - É o arquivo que ainda não foi modificado. Se ele não for usado e for removido ele vira Untracked.

**<u>Modified</u>** - É o que sofreu alguma modificação, o git sabe através do SHA1 que foi modificado, comparando os números de SHA1.

**<u>Staged</u>** - São os arquivos que estão se preparando para fazer parte de outro tipo de agrupamento. Acontecem em arquivo que estão em modified e acionamos o ‘git add *’ vai automaticamente para Stage esperando ser usado/ entrar em ação.
Esse agrupamento que ele pode ser usado para fazer parte de um commit/ Objeto, que retorna para unmodified com todos os arquivos dentro dele, para começar o ciclo novamente, confirmar que acabou com as alterações desses arquivos e salva esse arquivo com o código até o momento que foi alterado novamente, que inicia o ciclo novamente

**Untracked** - Arquivos que criamos mas o git não sabe da existência, como o arquivo strogonoff que foi criado na pasta do pc com o .md, depois que foi acionado/ ‘rodado’ o comando ‘git add *’ foi movido direto p staged.

Trabalhamos com <u>2 ambientes</u>

**O servidor** (site do git)

**O ambiente  de desenvolvimento** (tudo o que está na máquina/ pc git instalado e a pasta usada).



**Working Directory** - arquivos de trabalho (neste caso livro-receitas);
**Staging area** - Área de preparação, quando dá o ‘git add *’ o arquivo livro-receita vai transitar na área de staging e working directory ‘um ciclo’ (Unmodified>Modified>Staged);
**Local Repository/ repositório local** - Quando cria o commit desses arquivos, entra no ciclo de staging area e local repository. Depois disso pode fazer a modificação do repositório local no remoto.

O comando ‘git status’ para ver em qual fase está o arquivo.

<u>Cont. criando um commit:</u>

Usamos o ls e enter> mostra o arquivo strogonoff.md > git status e enter p ver como está.

Criar um pasta: mkdir receitas e enter > ls e enter >
mostra os arquivos receita/    strogonoff.md

Vamos mover o repositório strogonoff.md p dentro deste outro repositório chamado receitas:
Digita mv strogonoff.md ./receitas/ e enter

Verificamos com ls se foi movido corretamente, como abaixo. Depois ‘cd ..’ p voltar para a pasta livro-receitas.

Se dermos o git status e enter > mostra que o arquivo foi deletado ao invés de modificado, pois não informamos isso ao git para informar usamos o ‘git add ’.

Então fica: git add * “strogonoff.md receitas/’ e enter.

Confirma que foi adicionado e aí criamos o commit

git commit -m “ cria pasta receitas, move arquivo para pasta receitas” e enter
Confirma a criação do commit e damos vamos confirmar o status

git status e enter > Vai mostrar que está clean/limpo

Criar um arquivo ls e enter> echo > README.md e enter > ls e enter p confirmar
git status e enter > Mostra que tem um arquivo untracked/ (criado e ñ usado)

Agora na pasta do pc abrir o arquivo README.md no Typora

Dentro do Typora digita o que será a cara do livro de receitas, usando os comandos

Se dermo git status vai mostrar que continua untracked pois não atualizamos no git

Então: git add * e enter > confirma que foi adicionado > ls e enter
Mostra os arquivos README.md receitas/

git status e enter > E vamos criar um commit

git commit -m “adiciona index” e enter . Confirmar que foi criado


<u>Nota Fran:</u> Ao tentar continuar a próxima aula tive um problema devido ao ‘name’ que cadastrei diferente do github no site.

Então use o seguinte comando para remover o que quero alterar
git config --global --unset user.(o que quero remover)

git config --global --unset user.name e enter > se der git config --list vai listar e ñ aparece mais o  que foi removido no caso ‘name’

Agora vou cadastrar o correto conforme o site:
git config --global user.name “nome” e enter >
Se der git config --list vai mostrar o name correto. OK

Após correções:

Vamos criar um repositório com nome de “livro-receitas” e descrição ‘meu livro de receitas’ passo a passo na pág 38, mas dessa vez será publica.
Copiar o link e voltar para terminar

ls e enter > Mostra README.md receitas/

Agora vamos apontar o repositório da máquina loca/ local repository para o remoto:
git remote add origin (cola o link copiado no site do git) e enter.
usamos o seguinte comando para listar os repositórios remotos

git remote - v e enter > Vai mostrar o repo remoto

ls e enter > Mostra README.md receitas/

Agora vamos apontar o repositório da máquina loca/ local repository para o remoto:
git remote add origin (cola o link copiado no site do git) e enter.
usamos o seguinte comando para listar os repositórios remotos

git remote - v e enter > Vai mostrar o repo remoto. Ok

Voltando no GitHub remoto/site verificamos que aparece o arquivo formatado no Typora.
Também conseguimos ver o inicio do nº SHA1
Clicando em cima desse inicio do nº SHA1, abre o histórico e tudo o que foi alterado.
Também aparece o nº de SHA1 completo.

