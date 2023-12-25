# Anotações - Estudos

## GIT: Estados do GIT (cmd: git status)
**Unmodified:** Está salvo no último commit, commitados e vistos pelo Git. <br>
**Modified:** O arquivo está modoficado e talvez eu queira commitar essas mudanças. <br>
**Staged:** Área preparatória para dar o commit. Limbo antes do commit. (cmd: git add README.MD) <br>
**Untracked:** Não rastreado. <br><br>
![lifecycle](https://github.com/barbarafsena/anotacoes/assets/104398945/3400b7a9-de66-4518-9350-109740a53337)
<br><br>

## GIT: Comandos
`Git init:` Para inicializar um repositório do Git. <br>
`git config`: Informa quem é você para que ele armazene corretamente os dados do autor de cada uma das alterações no código <br>
- git config --local user.name "Seu nome aqui"<br>
- git config --local user.email "seu@email.aqui" <br><br>
`Git status`: Mostra o estado do nosso repositório, ou seja, quais arquivos foram alterados, ou não. <br>
`Git add:` Adiciona um arquivo para ser monitorado.
`Git commit -m:` Commita, salva as modificações.
<br>

- Existe um arquivo especial do Git, chamado **.gitignore**, e todas as linhas que estiverem nele serão lidos e ignorados pelo Git. Se temos um arquivo denominado **ide-config** que queremos que seja ignorado, por exemplo, basta o incluirmos em **.gitignore**, digitando **ide-config** simplesmente. Da mesma forma, se tivéssemos uma pasta ide, incluiríamos **ide/**, em uma nova linha.

![image](https://github.com/barbarafsena/anotacoes/assets/104398945/1146a6ea-0c96-4828-9461-1457b5499da9)

- **Obs.:** Precisaremos adicioná-lo, com git add .gitignore e git commit -m "Adicionando .gitignore"

`Git diff:` vê as linhas modificadas e mantidas. <br>
`Git commit -m "":` alterações prontas para salvar o estado desse projeto, fazendo um snapshot dele. <br>
`Git log:` Mostra o historico de alterações, cada mensagem de commits feitos, o andamento do projeto. <br>
`Git push:` Manda para a branch do github. <br>
`Git pull:` Pega as alterações do repositorio remoto e fazer um merge. <br>
`Comando git fetch:` verifica o que está no repositorio remoto que é diferente do meu. <br>
`Comando git diff:` mostra a mudança que foi feita no repositorio. <br>
`Git log --oneline --decorate:` Indica onde está a HEAD (o ponteiro). Qual branch estamos. <br>
`Git log --oneline`: Commits de forma resumida.
`Git branch nome_da_branch:` Cria a nova branch. <br>
`Git checkout nome_da_branch:` Joga a HEAD para a branch que você quer. <br>
`Git checkout -b nome_da_branch:` Cria uma nova branch e jogar a HEAD para ela. <br>
`Git branch:` Mostra todas as branches existentes. <br>
`Git merge nome_da_branch:` Juntas as branches para a branch atual (a que está a HEAD está apontando no momento). <br>
`Git rebase nome_da_branch:` O rebase atualiza a branch, mantendo o trabalho dela como sendo o último.
`git init --bare:` Cria um repositório que não terá a working tree, ou seja, não conterá uma cópia dos nossos arquivos. O repositório servirá apenas como servidor, para que outros membros da equipe sincronizem seus trabalhos. <br>
`git remote add nome-repositorio caminho/para/o/repositorio:` Ligação entre os repositórios: o local e o servidor.<br>
`git remoto rename origin local:` Troca o nome do repositório remoto de ORIGIN para LOCAL. <br>
`git push LOCAL [nome do repositorio remoto] MASTER [branch do repositorio remoto]:` Envia os dados para a branch do servidor remoto. <br>
`git pull LOCAL [nome do repositorio remoto] MASTER [branch do repositorio remoto]:` Trás os dados da branch do servidor remoto para o meu repositório local. <br>
`git push -u ORIGIN [nome do repositorio remoto] MASTER [branch do repositorio remoto]:` É muito comum que o nome do repositório remoto seja ORIGIN. O -u indica que sempre iremos dar push para esse repositorio e branch, por isso é bom retirá-lo do comando. <br>
`Git checkout -- nome_do_arquivo`: Descarta as alterações que ainda não foram commitadas. <br>
`Git reset HEAD nome_do_arquivo`: Descarta as alterações após ter dado git add no arquivo. <br>
`Git revert hash_do_commit`: Desfaz um commit já realizado. <br>
`Git stash`: Guarda a alteração para depois ser trabalho novamente. <br>
`Git list`: Lista os stashes. <br>
`Git stash apply numero_do_stash_depois_do_@`: Recupera o trabalho com as alterações guardadas. <br>
`Git stash drop`:  Remove <br>
`Git stash pop`:  Faz ambas as ações ao mesmo tempo, ou seja, pega a última alteração adicionada à stash e já remove. <br>
`Git checkout hash_do_commit`: É uma forma de navegar pelos commits. A mensagem que se exibe indica que estamos em um estado de cabeça (HEAD) desanexado (detached) do controle de versões. Isto é, não estamos mais em nenhum branch, e sim em um commit específico, portanto os commits feitos nesse estado são perdidos. Se quisermos manter os commits feitos a partir deste ponto, será necessário criar uma nova branch. <br>
`Git diff hash_do_commit.. hash_do_commit:` mostra as diferenças entre dois commits. <br>
`Git tag -a (add) v0.1.0 -m "lançando a primeira versão":` Cria uma tag que indica a versão da aplicação. <br>
`Git tag:` São exibidos todos marcos disponíveis. <br>
`Git push origin v0.1.0:` Envia a tag ao servidor. Isso gera uma Release no Github, ou seja, conseguimos baixar um arquivo compactado com o nosso código neste ponto <br>
## Diferença rebase vs merge
O `merge` integra o conteúdo da branch de trabalho (por exemplo titulo ou lista) com a branch master. Nesse caso apenas a branch master é alterada para adicionar as mudanças e o histórico da branch de trabalho permanece inalterado e um novo commit dessa junção é adicionado ao histórico. <br><br>
<b>Exemplo merge:</b>
![Screenshot from 2023-12-25 19-10-56](https://github.com/barbarafsena/anotacoes/assets/104398945/17771d75-db0b-480b-ba3b-3bbeff5cd883)
<br><br>
O `rebase` move a base da branch de trabalho para o final da branch master; ou seja, Nesse caso, o código também é integrado, porém ele faz isso transformando duas branches em uma só. Assim, a linha do tempo das alterações de código permanece sempre como uma linha contínua da branch master, apagando a branch de trabalho. <br><br>
<b>Exemplo rebase:</b>
![Screenshot from 2023-12-25 19-09-26](https://github.com/barbarafsena/anotacoes/assets/104398945/82018564-29e3-492e-b0ab-0b109185d6ec)
<br><br>
O merge junta os trabalhos e gera um merge commit. O rebase aplica os commits de outra branch na branch atual.

## Comandos git bash

<br>

- O sinal **~/** acompanhado do nome do diretório informa que qualquer comando que eu inserir no terminal, vai estar relacionado ao diretório “/c/Users/Alura/Desktop” ou seja, no diretório Desktop. <br>
![GitBash](https://github.com/barbarafsena/anotacoes/assets/104398945/b0b97c21-18b4-4daa-89da-f9b1285a376f)
- **pwd**: saber em qual diretório está ou mesmo quiser se certificar que está trabalhando no diretório correto;
- **cd nome_da_pasta**: Para navegar para uma pasta dentro do diretório atual
- **cd ..** :Para navegar para a pasta pai (diretório superior) 
- **cd /caminho/para/a/pasta**: Para navegar para um diretório específico fornecendo o caminho absoluto 
- **cd git/**: Para acessarmos o diretório git, que está no interior de Solides.
- **ls:** Para listar todo o conteúdo do diretório.
  
## Kanban
### Erros mais comuns
- Andar contra o fluxo
- Ter uma coluna para on hold
- Não ter limite para WIP
- Não mapear todos os itens de trabalho
<hr><br>
- Sistema puxado: Para entrar mais trabalho num sistema, algo tem que sair.

## Agilidade: promovendo a transformação ágil
###  Por que surgiu o método ágil?
- Surgiu de outras engenharias. A engenharia de software por ser uma engenharia que veio depois de outras, herdou muito do mindset de outras engenharias.
- Engenharia civil: Análise -> fundação -> pilares | Nada muda, não tem como alterar a planta. (Waterfall) Assim, a engenharia de software, seguiu esse tipo de projeto dividido em fases.
- Não é interessante para o desenvolvimento de software, as coisas mudam e o cliente quer mudanças. Ao seguir o modelo Waterfall, não há como voltar.

###  Diferenças agile x waterfall
- Na metodologia ágil, não se define tudo a priori, se faz aos poucos.
- Não é priorizado por etapa, faz as funcionalidades, um pouco de cada etapa o tempo todo p/ ter a resposta do cliente o tempo todo.
- <b>Principais diferenças:</b> priorização, fluxo e feedback.
<hr>
<br>

###  O que é ser ágil?
Ser ágil é entregar <b>valor mais rapidamente.</b>





