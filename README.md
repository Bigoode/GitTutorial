# Usando o Git e Github na prática

## Instalando o GIT

- [Link com os downloads](https://git-scm.com/downloads)

## Verificando versão do GIT e se o mesmo foi corretamente instalado

- Abra o prompt de comando (_cmd_)

  Para acessar o prompt de comando, você pode pressionar ao mesmo tempo as teclas _WINDOWS + R_ para abrir a janela "executar". Aí é só digitar _CMD_ na barra de pesquisa e clicar em "Enter".
  <br>
  Outra opção é digitar _CMD_ diretamente na barra de pesquisa, ao lado do botão Iniciar na barra de tarefas.

- Digite `git --version`

  Se aparecer a versão e por que foi instalado corretamemte.

  - ex: `git version 2.31.1.windows.1`.

## Criando um novo projeto

- Crie uma nova pasta no PC

- Abra o VSCode nessa pasta

- Crie um novo arquivo `README.md`

  - ex: `echo "#TituloDaPagina">> README.md`.

  _.md_ é a exentção Markdown, que é uma linguem de marcação.

- Escreva algo dentro dele

  - ex: Usando o Git e Github na prática

- Salve o arquivo

## Usando o Git

- Abra o Git Bash que foi instalado na sua máquina, ou utilize o terminal do VSCode.

- Vá até o diretório da pasta

  - ex: `cd DiretórioDaPasta`

- Digite o comando `git init` para inicializar o repositório

  Foi criada uma pasta `.git` e é ali que todo acontece, então não apague-a!

- Digite o comando `git add README.md` para colocar o arquivo na área de stagging ou `git add .` para colocar todos os arquivos na área de stagging

  <img src="https://i1.wp.com/www.markus-gattol.name/misc/mm/si/content/git_git_add.png">

- Esse `add` é necessário antes de darmos o commit de fato

- Digite o comando `git status` para verificar o status do arquivo

  O `git status` Verifica quais os estados que os arquivos estão. Se existe algum arquivo modificado, adiciona ou removido

- Dê `git commit -m "primeiro commit"` para de fato dar o commit no repositório

  Os commits são as unidades estruturais de um cronograma de projeto Git. Podem ser considerados instantâneos ou marcos ao longo do cronograma de um projeto Git. São criados com o comando `git commi` para capturar o estado de um projeto naquele momento.

- Dê `git branch -M "main"` para alterar o nome da branch principal de `master` para `main` (isso é uma boa prática atualmente recomendada)

  _Branch_ , em tradução literal, significa “ramo”. No mundo da programação, ela tem o mesmo significado: uma branch é uma ramificação do seu projeto.

## Interfaces Git

Existem algumas [interfaces legais do git](https://git-scm.com/downloads/guis) que você pode fazer o download para poder visualizar de fato como está o projeto, o que foi alterado em cada commit, quando foi alterado etc.

## Repositório no Github

- Crie uma conta na plataforma

- Depois de ter criado a conta na plataforma, você irá em `Criar novo repositório`

- Preencha com as informações do projeto,

  <img src="https://media.discordapp.net/attachments/831974152667398214/836828773067915274/unknown.png">

- Logo depois aparecera essa página, apenas copie o link

  <img src="https://media.discordapp.net/attachments/831974152667398214/836828905859186708/unknown.png?width=1440&height=141">

- Para passar o _commit_ do repositório local (sua máquina) para um repositório na plataforma do Github, usamos o `git remote add origin <link do repositório>`

  - `git` é para ser feito um comando no _git_

  -`remote` é o a conexão local com o repositório do _GitHub_

  - `add` para adicionar o repositório

  - `origin` é o nome utilizado para referenciar o nosso repositório

- Já temos o um repositório local conectado com o respositório do Github, porém o `commit` que damos na máquina não sobe automaticamente para a plataforma

- Para isso precisaremos empurrar, enviar para lá com o `git push -u origin main`

  - `push` significa empurra

  - `main` e a branch que queremos salvar

- Agora se recarregarmos a página veremos o arquivo na plataforma!

## Alterar é adicionar arquivo

- Adicione alguma alteração no arquivo

  - ex: Adicione a frase no arquivo `Essa é uma alteração`

- Crie um novo arquivo

  - ex: `Projeto.md`

- Escreva algo nele

  - ex: Escreva a frase no arquivo `Esse é o arquivo onde desenvolverei o meu projeto`

- Subir as alterações

  - Dê `git add .` (para dicionara todos os arquivos)

  - Dê `git commit -m "Primeira alteração"`

- Para alterar algo no respositório do Github precisamos dar o push com `git push origin main`

- O código no Github já foio alterado

- Clicando no nome do `commit`, podemos ver exatamente as alterações que foram feitas nele.

  - O verde com `+` e o vermelho com `-` mostra, os conteúdos que foram adicionados e editados dentro do código.

- No botão abaixo pode ser visto todos os commits já feitos anteriormente, se clicar em algum deles, pode ser visto o que havia sido alterado, além de, vermos o código como era.

  <img src="https://media.discordapp.net/attachments/831974152667398214/836830443617648670/unknown.png">

## Branch

    "Branch" , em tradução literal, significa “ramo”. No mundo da programação, ela tem o mesmo significado: uma branch é uma ramificação do seu projeto.

- Até agora só alteramos e mandamos de o commit, na `main`, que é aquela linha do tempo principal.

- Agora vamos criar uma branch e depois juntar ela ao código que já está na `main` (ela é uma linha cronológica adicional/alternativa a principal)

  - A branch pode ser criada tanto para quando você for fazer uma alteração em um arquivo, quando para adicionar outro arquivo dentro do projeto ou mesmo excluir.

- Vamos adicionar um novo arquivo

  - ex: desenvolver feature (característica) `Botão`

- Dê `git checkout -b "NomeDaBracsh"`, assim criando uma nova _branch_

  - ex: `git checkout -b "botao"`

  - Esse comando além de criar a branch já entra nela com o checkout

- crie um o arquivo,

  - ex: `botão.md` "aqui eu crio o botão"

- coloque a alteração em stagging com o `git add .` e commite com o `git commit -m "botao"`

- Para enviarmos agora usaremos `git push origin botao` (não será mais`git push orgin main`, pois mudamos de branch, _main_ era branch principa)

- Agora o nosso Github, tem 2 branches, a `main` e a `botao`

  <img src="https://media.discordapp.net/attachments/812313742192279612/836820670037622854/unknown.png">

- Vamos supor que o desenvolvimento do botão ainda não estivese terminado, assim poderia retomar tranquilamente na branch `botao` até terminar!

- Se for preciso voltar na branch `main` e desenvolver a partir do ponto que parou basta dar `git checkout main`, e pra voltar para branch `botao` é só dar `git checkout botao`

## Merge

    Merge -> Unir
    Mesclagem é o jeito do Git de unificar um histórico bifurcado. O comando git merge permite que você pegue as linhas de desenvolvimento independentes criadas pelo git branch e as integre em uma ramificação única.

- Juntando a branch `main` com a branch `botao`, após acabar o desenvolvimento na branch `botao`

- Entre na branch principal `git checkout main` e lá será feito o _merge_ com a branch `botao`, dê `git merge botao`

- Agora toda a alteração na branch `botao` juntou com a `main`

- Agora dê o _push_ para mande tudo para o Github com `git push origin main`

## Clone

- Ao entrar em um repositório, seu ou de outra pessoa, terá esse botão `Code`, que quando você clica aparece um link:

  <img src="https://media.discordapp.net/attachments/812313742192279612/836823564513705994/unknown.png">

- Você irá copiar esse link e levar ele para o terminal

- O comando para puxar o projeto para a sua máquina é o `git clone linkDoRepositório`

  - Não é necessário criar um repositório antes disso, como o `git init`. Basta abrir o terminal e clonar o projeto e tudo aparecerá!

## Pull

    Pull -> Puxar
    O pull request, é o pedido para que o repositório original, ou uma branch do repositório original, faça a ação de pull (puxar) as atualizações do repositório fork ou de um branch do próprio repositório

- Para puxar uma atualizar feita no projeto principal basda dar um pull request

- Dê o comando `git pull`, ele irá puxar todas as alterações feitas no repositório do Github para o seu repositório local

## Fork

    - A ferramenta `fork`, nada mais é que uma cópia de um repositório. Esta cópia vira um clone do estado atual do repositório, fazendo assim com que você possa experimentar mudanças e feature novas sem precisar utilizar o repositório principal.

  <img src="https://media.discordapp.net/attachments/831974152667398214/836826687634407434/unknown.png">

## Pull request

    O pull request, é o pedido para que o repositório original, ou uma branch do repositório original, faça a ação de pull (puxar) as atualizações do repositório fork ou de um branch do próprio repositório

- Após ter dado um fork no projeto e ele ter ido pra sua conta, você poderá alterar o projeto e adicionar as funcionalidades que deseja

- Depois disso, você poderá salvar o projeto, dar o `git add .`, `git commit -m "validação de botões"` e `git push origin main`

- No seu Github, haverá uma mensagem parecida com a seguinte:

  <img src="https://media.discordapp.net/attachments/831974152667398214/838990983852458035/unknown.png">

- Isso significa que a branch do seu repositório está 1 commit "na frente" da branch original

- Haverá um botão que aparece em seguida

  <img src="https://media.discordapp.net/attachments/831974152667398214/838991711249235998/unknown.png">

- Ele serve para você enviar para o dono do repositório original uma solicitação de pull, ou seja, fazer com que ele puxe as alterações que você fez no seu repositório para o repositório dele, original

- Ao clicar no botão, você será direcionado para uma página que fará a avaliação se esse `pull request` terá conflitos ou não com o código no repositório original. Caso não tenha, bastão clicar no botão de `Create pull request`

  <img src="https://media.discordapp.net/attachments/831974152667398214/838992584893399100/unknown.png">

  - Você irá colocar um nome intuitivo, que demonstre a funcionalidade adicionada e o ideal é que você também crie uma boa descrição do que desenvolveu, não somente explicando o que é, mas ensinando ao dono do repositório original a forma como ele poderá testar também

- Depois disso, basta esperar para que o dono da branch original aceite o seu pull request

## Finalização

Existem diversas outras funcionalidades do Git e do Github, porém tenho certeza que com tudo isso que vocês viram hoje vocês já conseguem desenvolver um projeto de uma forma bem legal

Recomendo sempre vocês darem uma olhada na [documentação do Git](https://git-scm.com/doc), pois qualquer dúvida que apareça pode ser respondida por lá na explicação
