Esse guia traz alguns comandos que vão ajudar no dia a dia nas duvidas de como usar o Git.

Esse guia foi editado a partir do gist de leocomelli
<https://gist.github.com/leocomelli/2545add34e4fec21ec16>

Menu:
<!-- TOC -->

- [Github-Guide-to-code](#github-guide-to-code)
    - [Estados dos seus arquivos no git](#estados-dos-seus-arquivos-no-git)
    - [Comandos Ajuda Github](#comandos-ajuda-github)
    - [Comandos de Configuração do GIT](#comandos-de-configuração-do-git)
        - [Geral](#geral)
            - [Configurar usuário](#configurar-usuário)
            - [Configurar email](#configurar-email)
            - [Configurar editor](#configurar-editor)
            - [Configurar ferramenta de merge](#configurar-ferramenta-de-merge)
            - [Setar arquivos a serem ignorados](#setar-arquivos-a-serem-ignorados)
            - [Listar configurações](#listar-configurações)
        - [Ignorar Arquivos](#ignorar-arquivos)
        - [Repositório](#repositório)
            - [Criar novo repositório](#criar-novo-repositório)
            - [Verificar estado dos arquivos/diretórios](#verificar-estado-dos-arquivosdiretórios)
            - [Adicionar um arquivo em específico](#adicionar-um-arquivo-em-específico)
            - [Adicionar um diretório em específico](#adicionar-um-diretório-em-específico)
            - [Adicionar todos os arquivos/diretórios](#adicionar-todos-os-arquivosdiretórios)
            - [Adicionar um arquivo que esta listado no .gitignore (geral ou do repositório)](#adicionar-um-arquivo-que-esta-listado-no-gitignore-geral-ou-do-repositório)
        - [Comandos para comitar arquivo/diretório](#comandos-para-comitar-arquivodiretório)
            - [Comitar um arquivo](#comitar-um-arquivo)
            - [Comitar vários arquivos](#comitar-vários-arquivos)
            - [Comitar informando mensagem](#comitar-informando-mensagem)
        - [Comandos para remover arquivo/diretório](#comandos-para-remover-arquivodiretório)
            - [Remover arquivo](#remover-arquivo)
            - [Remover diretório](#remover-diretório)
        - [Visualizar hitórico](#visualizar-hitórico)
            - [Exibir histórico](#exibir-histórico)
            - [Exibir histórico com diff das duas últimas alterações](#exibir-histórico-com-diff-das-duas-últimas-alterações)
            - [Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-))](#exibir-resumo-do-histórico-hash-completa-autor-data-comentário-e-qtde-de-alterações--)
            - [Exibir informações resumidas em uma linha (hash completa e comentário)](#exibir-informações-resumidas-em-uma-linha-hash-completa-e-comentário)
            - [Exibir histórico com formatação específica (hash abreviada, autor, data e comentário)](#exibir-histórico-com-formatação-específica-hash-abreviada-autor-data-e-comentário)
            - [Exibir histório de um arquivo específico](#exibir-histório-de-um-arquivo-específico)
            - [Exibir histórico de um arquivo específico que contêm uma determinada palavra](#exibir-histórico-de-um-arquivo-específico-que-contêm-uma-determinada-palavra)
            - [Exibir histórico modificação de um arquivo](#exibir-histórico-modificação-de-um-arquivo)
            - [Exibir histório de um determinado autor](#exibir-histório-de-um-determinado-autor)
            - [Exibir revisão e autor da última modificação de uma bloco de linhas](#exibir-revisão-e-autor-da-última-modificação-de-uma-bloco-de-linhas)
        - [Comandos para Desfazer operações](#comandos-para-desfazer-operações)
            - [Desfazendo alteração local (working directory)](#desfazendo-alteração-local-working-directory)
            - [Desfazendo alteração local (staging area)](#desfazendo-alteração-local-staging-area)
        - [Repositório Remoto](#repositório-remoto)
            - [Exibir os repositórios remotos](#exibir-os-repositórios-remotos)
            - [Vincular repositório local com um repositório remoto](#vincular-repositório-local-com-um-repositório-remoto)
            - [Exibir informações dos repositórios remotos](#exibir-informações-dos-repositórios-remotos)
            - [Renomear um repositório remoto](#renomear-um-repositório-remoto)
            - [Desvincular um repositório remoto](#desvincular-um-repositório-remoto)
            - [Enviar arquivos/diretórios para o repositório remoto](#enviar-arquivosdiretórios-para-o-repositório-remoto)
            - [Atualizar repositório local de acordo com o repositório remoto](#atualizar-repositório-local-de-acordo-com-o-repositório-remoto)
            - [Atualizar os arquivos no branch atual](#atualizar-os-arquivos-no-branch-atual)
            - [Buscar as alterações, mas não aplica-las no branch atual](#buscar-as-alterações-mas-não-aplica-las-no-branch-atual)
            - [Clonar um repositório remoto já existente](#clonar-um-repositório-remoto-já-existente)
        - [Tags](#tags)
            - [Criando uma tag leve](#criando-uma-tag-leve)
            - [Criando uma tag anotada](#criando-uma-tag-anotada)
            - [Criando uma tag assinada](#criando-uma-tag-assinada)
            - [Criando tag a partir de um commit (hash)](#criando-tag-a-partir-de-um-commit-hash)
            - [Criando tags no repositório remoto](#criando-tags-no-repositório-remoto)
            - [Criando todas as tags locais no repositório remoto](#criando-todas-as-tags-locais-no-repositório-remoto)
        - [Branches](#branches)
            - [Criando um novo branch](#criando-um-novo-branch)
            - [Trocando para um branch existente](#trocando-para-um-branch-existente)
            - [Criar um novo branch e trocar](#criar-um-novo-branch-e-trocar)
            - [Voltar para o branch principal (master)](#voltar-para-o-branch-principal-master)
            - [Resolver merge entre os branches](#resolver-merge-entre-os-branches)
            - [Apagando um branch](#apagando-um-branch)
            - [Listar branches](#listar-branches)
            - [Listar branches com informações dos últimos commits](#listar-branches-com-informações-dos-últimos-commits)
            - [Listar branches que já foram fundidos (merged) com o master](#listar-branches-que-já-foram-fundidos-merged-com-o-master)
            - [Listar branches que não foram fundidos (merged) com o master](#listar-branches-que-não-foram-fundidos-merged-com-o-master)
            - [Criando branches no repositório remoto](#criando-branches-no-repositório-remoto)
            - [Criando um branch remoto com o mesmo nome](#criando-um-branch-remoto-com-o-mesmo-nome)
            - [Criando um branch remoto com nome diferente](#criando-um-branch-remoto-com-nome-diferente)
            - [Baixar um branch remoto para edição](#baixar-um-branch-remoto-para-edição)
            - [Apagar branch remoto](#apagar-branch-remoto)
        - [Rebasing](#rebasing)
            - [Fazendo o rebase entre um o branch bug-123 e o master.](#fazendo-o-rebase-entre-um-o-branch-bug-123-e-o-master)
        - [Stash](#stash)
            - [Criar um stash](#criar-um-stash)
            - [Listar stashes](#listar-stashes)
            - [Voltar para o último stash](#voltar-para-o-último-stash)
            - [Voltar para um stash específico](#voltar-para-um-stash-específico)
            - [Criar um branch a partir de um stash](#criar-um-branch-a-partir-de-um-stash)
        - [Reescrevendo o histórico](#reescrevendo-o-histórico)
            - [Alterando mensagens de commit](#alterando-mensagens-de-commit)
            - [Alterar últimos commits](#alterar-últimos-commits)
            - [Alterando os três últimos commits](#alterando-os-três-últimos-commits)
            - [Juntando vários commits](#juntando-vários-commits)
            - [Remover todo histórico de um arquivo](#remover-todo-histórico-de-um-arquivo)
        - [Bisect](#bisect)
            - [Iniciar pequinsa binária](#iniciar-pequinsa-binária)
            - [Marcar o commit atual como ruim](#marcar-o-commit-atual-como-ruim)
            - [Marcar o commit de uma tag que esta sem o bug/inconsistência](#marcar-o-commit-de-uma-tag-que-esta-sem-o-buginconsistência)
            - [Marcar o commit como bom](#marcar-o-commit-como-bom)
            - [Marcar o commit como ruim](#marcar-o-commit-como-ruim)
            - [Finalizar a pesquisa binária](#finalizar-a-pesquisa-binária)

<!-- /TOC -->

## Estados dos seus arquivos no git

* Modificado (modified);
* Preparado (staged/index)
* Consolidado (comitted);

## Comandos Ajuda Github

```console
git help <Comando específico>
```

```console
git help add
```

```console
git help commit
```

```console
git help <qualquer_comando_git>
```

## Comandos de Configuração do GIT

### Geral

As configurações do GIT são armazenadas no arquivo .gitconfig localizado dentro do diretório do usuário do Sistema Operacional. As configurações realizadas através dos comandos abaixo serão incluídas no arquivo .gitconfig

#### Configurar usuário

```console
git config --global user.name "Victor Caldas"
```

#### Configurar email

```console
git config --global user.email contatos.caldas@gmail.com
```

#### Configurar editor

```console
git config --global core.editor vim
```

#### Configurar ferramenta de merge

```console
git config --global merge.tool vimdiff
```

#### Setar arquivos a serem ignorados

```console
git config --global core.excludesfile ~/.gitignore
```

#### Listar configurações

```console
git config --list
```

### Ignorar Arquivos

Os nomes de arquivos/diretórios ou extensões de arquivos listados no arquivo .gitignore não serão adicionados em um repositório. Existem dois arquivos .gitignore, são eles:

* Normalmente armazenado no diretório do usuário do Sistema Operacional. O arquivo que possui a lista dos arquivos/diretórios a serem ignorados por todos os repositórios deverá ser declarado conforme citado acima. O arquivo não precisa ter o nome de .gitignore.

* Por repositório: Deve ser armazenado no diretório do repositório e deve conter a lista dos arquivos/diretórios que devem ser ignorados apenas para o repositório específico.

### Repositório

#### Criar novo repositório

```console
git init
```

#### Verificar estado dos arquivos/diretórios

```console
git status
```

#### Adicionar um arquivo em específico

```console
git add meu_arquivo.txt
```

#### Adicionar um diretório em específico

```console
git add meu_diretorio
```

#### Adicionar todos os arquivos/diretórios

```console
git add .
```

#### Adicionar um arquivo que esta listado no .gitignore (geral ou do repositório)

```console
git add -f arquivo_no_gitignore.txt
```

### Comandos para comitar arquivo/diretório

#### Comitar um arquivo

```console
git commit meu_arquivo.txt
```

#### Comitar vários arquivos

```console
git commit meu_arquivo.txt meu_outro_arquivo.txt
```

#### Comitar informando mensagem

```console
git commit meuarquivo.txt -m "minha mensagem de commit"
```

### Comandos para remover arquivo/diretório

#### Remover arquivo

```console
git rm meu_arquivo.txt
```

#### Remover diretório

```console
git rm -r diretorio
```

### Visualizar hitórico

#### Exibir histórico

```console
git log
```

#### Exibir histórico com diff das duas últimas alterações

```console
git log -p -2
```

#### Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-))

```console
git log --stat
```

#### Exibir informações resumidas em uma linha (hash completa e comentário)

```console
git log --pretty=oneline
```

#### Exibir histórico com formatação específica (hash abreviada, autor, data e comentário)

```console
git log --pretty=format:"%h - %an, %ar : %s"
```

%h: Abreviação do hash;
%an: Nome do autor;
%ar: Data;
%s: Comentário.
Verifique as demais opções de formatação no Git Book

#### Exibir histório de um arquivo específico

```console
git log -- <caminho_do_arquivo>
```

#### Exibir histórico de um arquivo específico que contêm uma determinada palavra

```console
git log --summary -S<palavra> [<caminho_do_arquivo>]
```

#### Exibir histórico modificação de um arquivo

```console
git log --diff-filter=M -- <caminho_do_arquivo>
```

O pode ser substituido por: Adicionado (A), Copiado (C), Apagado (D), Modificado (M), Renomeado (R), entre outros.

#### Exibir histório de um determinado autor

```console
git log --author=usuario
```

#### Exibir revisão e autor da última modificação de uma bloco de linhas

```console
git blame -L 12,22 meu_arquivo.txt 
```

### Comandos para Desfazer operações

#### Desfazendo alteração local (working directory)

Este comando deve ser utilizando enquanto o arquivo não foi adicionado na staged area.

```console
git checkout -- meu_arquivo.txt
```

#### Desfazendo alteração local (staging area)

Este comando deve ser utilizando quando o arquivo já foi adicionado na staged area.

```console
git reset HEAD meu_arquivo.txt
```

Se o resultado abaixo for exibido, o comando reset não alterou o diretório de trabalho.

```console
Unstaged changes after reset:
M	meu_arquivo.txt
```

A alteração do diretório pode ser realizada através do comando abaixo:

```console
git checkout meu_arquivo.txt
```

### Repositório Remoto

#### Exibir os repositórios remotos

```console
git remote
```

```console
git remote -v
```

#### Vincular repositório local com um repositório remoto

```console
git remote add origin git@github.com:victorcaldas/projetoAndroid-git.git
```

#### Exibir informações dos repositórios remotos

```console
git remote show origin
```

#### Renomear um repositório remoto

```console
git remote rename origin curso-git
```

#### Desvincular um repositório remoto

```console
git remote rm curso-git
```

#### Enviar arquivos/diretórios para o repositório remoto

O primeiro push de um repositório deve conter o nome do repositório remoto e o branch.

```console
git push -u origin master
```

Os demais pushes não precisam dessa informação

```console
git push
```

#### Atualizar repositório local de acordo com o repositório remoto

#### Atualizar os arquivos no branch atual

```console
git pull
```

#### Buscar as alterações, mas não aplica-las no branch atual

```console
git fecth
```

#### Clonar um repositório remoto já existente

```console
git clone git@github.com:victorCaldas/projetoAndroid-git.git
```

### Tags

#### Criando uma tag leve

```console
git tag vs-1.1
```

#### Criando uma tag anotada

```console
git tag -a vs-1.1 -m "Minha versão 1.1"
```

#### Criando uma tag assinada

Para criar uma tag assinada é necessário uma chave privada (GNU Privacy Guard - GPG).

```console
git tag -s vs-1.1 -m "Minha tag assinada 1.1"
```

#### Criando tag a partir de um commit (hash)

```console
git tag -a vs-1.2 9fceb02
```

#### Criando tags no repositório remoto

```console
git push origin vs-1.2
```

#### Criando todas as tags locais no repositório remoto

```console
git push origin --tags
```

### Branches

O master é o branch principal do GIT.

O HEAD é um ponteiro especial que indica qual é o branch atual. Por padrão, o HEAD aponta para o branch principal, o master.

#### Criando um novo branch

```console
git branch bug-123
```

#### Trocando para um branch existente

```console
git checkout bug-123
```

Neste caso, o ponteiro principal HEAD esta apontando para o branch chamado bug-123.

#### Criar um novo branch e trocar

```console
git checkout -b bug-456
```

#### Voltar para o branch principal (master)

```console
git checkout master
```

#### Resolver merge entre os branches

```console
git merge bug-123
```

Para realizar o merge, é necessário estar no branch que deverá receber as alterações. O merge pode automático ou manual. O merge automático será feito em arquivos textos que não sofreram alterações nas mesmas linhas, já o merge manual será feito em arquivos textos que sofreram alterações nas mesmas linhas.

A mensagem indicando um merge manual será:

```console
Automerging meu_arquivo.txt
CONFLICT (content): Merge conflict in meu_arquivo.txt
Automatic merge failed; fix conflicts and then commit the result.
```

#### Apagando um branch

```console
git branch -d bug-123
```

#### Listar branches

```console
git branch
```

#### Listar branches com informações dos últimos commits

```console
git branch -v
```

#### Listar branches que já foram fundidos (merged) com o master

```console
git branch --merged
```

#### Listar branches que não foram fundidos (merged) com o master

```console
git branch --no-merged
```

#### Criando branches no repositório remoto

#### Criando um branch remoto com o mesmo nome

```console
git push origin bug-123
```

#### Criando um branch remoto com nome diferente

```console
git push origin bug-123:new-branch
```

#### Baixar um branch remoto para edição

```console
git checkout -b bug-123 origin/bug-123
```

#### Apagar branch remoto

```console
git push origin:bug-123
```

### Rebasing

#### Fazendo o rebase entre um o branch bug-123 e o master.

```console
git checkout experiment
```

```console
git rebase master
```

Mais informações e explicações sobre o Rebasing

### Stash

Para alternar entre um branch e outro é necessário fazer o commit das alterações atuais para depois trocar para um outro branch. Se existir a necessidade de realizar a troca sem fazer o commit é possível criar um stash. O Stash como se fosse um branch temporário que contem apenas as alterações ainda não commitadas.

#### Criar um stash

```console
git stash
```

#### Listar stashes

```console
git stash list
```

#### Voltar para o último stash

```console
git stash apply
```

#### Voltar para um stash específico

```console
git stash apply stash@{2}
```

Onde 2 é o indíce do stash desejado.

#### Criar um branch a partir de um stash

```console
git stash branch meu_branch
```

### Reescrevendo o histórico

#### Alterando mensagens de commit

```console
git commit --amend -m "Minha nova mensagem"
```

#### Alterar últimos commits

#### Alterando os três últimos commits

```console
git rebase -i HEAD~3
```

O editor de texto será aberto com as linhas representando os três últimos commits.

```console
pick f7f3f6d changed my name a bit
pick 310154e updated README formatting and added blame
pick a5f4a0d added catfile
```

Altere para edit os commits que deseja realizar alterações.

```console
edit f7f3f6d changed my name a bit
pick 310154e updated README formatting and added blame
pick a5f4a0d added catfile
```

Feche o editor de texto.

Digite o comando para alterar a mensagem do commit que foi marcado como edit.

```console
git commit –amend -m “Nova mensagem”
```

Aplique a alteração

```console
git rebase --continue
```

Atenção: É possível alterar a ordem dos commits ou remover um commit apenas mudando as linhas ou removendo.

#### Juntando vários commits

Seguir os mesmos passos acima, porém marcar os commtis que devem ser juntados com *squash

#### Remover todo histórico de um arquivo

```console
git filter-branch --tree-filter 'rm -f passwords.txt' HEAD
```

### Bisect

O bisect (pesquisa binária) é útil para encontrar um commit que esta gerando um bug ou uma inconsistência entre uma sequência de commits.

#### Iniciar pequinsa binária

```console
git bisect start
```

#### Marcar o commit atual como ruim

```console
git bisect bad
```

#### Marcar o commit de uma tag que esta sem o bug/inconsistência

```console
git bisect good vs-1.1
```

#### Marcar o commit como bom

O GIT irá navegar entre os commits para ajudar a indentificar o commit que esta com o problema. Se o commit atual não estiver quebrado, então é necessário marca-lo como bom.

```console
git bisect good
```

#### Marcar o commit como ruim

Se o commit estiver com o problema, então ele deverá ser marcado como ruim.

```console
git bisect bad
```

#### Finalizar a pesquisa binária

Depois de encontrar o commit com problema, para retornar para o HEAD utilize:

```console
git bisect reset
```
