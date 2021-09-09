# Configurações

 *Git Config* <br />

git config --local user.name "Seu nome aqui"
<br />
git config --local user.email "seu@email.aqui"

    HEAD: Estado atual do nosso código, ou seja, onde o Git nos colocou.
    Working tree: Local onde os arquivos realmente estão sendo armazenados e editados.
    index: Local onde o Git armazena o que será commitado, ou seja, o local entre a working tree e o repositório Git em si.
    
[Saiba Mais](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Gravando-Altera%C3%A7%C3%B5es-em-Seu-Reposit%C3%B3rio)

<br />

    git log --oneline => exibe as alterações em uma linha.
    git log -p => exibe o que foi alterado no código.
    git log --help => exibe opções possíveis.
    git log --graph => exbibe os logs num gráfico as linhas específicas do desenvolvimento.

[Saiba Mais sobre Git Log](https://devhints.io/git-log)

<br />

    git commit --amend => ao clicar enter abrirá o arquivo para editar o commit.
    git init --bare => repositório puro, que só contém as alterações dos arquivos e não contém uma cópia física dos arquivos, ou seja, não terá a working tree. Dessa forma, poupa espaço de armazenamento.

<br /> *Git Branch* <br />

    git branch -b {nova-branch} master => cria uma nova branch a partir da master.
    git branch -m {novo-nome} => renomeia a branch atual.
    git branch -d {branch} => remove a branch.
    git branch -D {branch} => remove a branch mesmo que ela tenha commits à frente da master.

<br /> *Git Remote* <br />

    git remote => lista repositório remotos que o repositório local conhece.
    git remote add [repositorio] => cria um novo repositório que pode ser tanto remoto quanto local.
    git remote -v => lista repositório remotos que o repositório local conhece com os endereços do repositório.
    
<br /> *Git Push* <br />

    git push [repositório] master => envia os dados de um repositório X para a master.
    git push -u origin master => seta que toda vez que for dado o git push será enviado para a master.
    git branch --set-upstream-to <remote-branch> => comando equivalente ao git push -u origin
    
<br /> *Git Rebase/Merge* <br />

    git merge [repositório] => gera um novo commit, informando que houve uma mescla entre duas branches.
    git rebase [repositório] => Junta todos os commits e aplica os commits de outra branch na branch atual.
    git rebase -i => unir vários commits em um

[Git Rebase vs Git Merge](https://medium.com/datadriveninvestor/git-rebase-vs-merge-cc5199edd77c)


<br /> *Reseat Files* <br />

    git chechout --<file> => remove o arquivo que ainda não foi adicionado.
    git reset HEAD <file> => desfazer o add no arquivo que já foi adicionado, mas alterações no arquivo permanecem.
    git revert {hash do commit} => desfaz as alterações que foram feitas, adicionadas e commitadas.
    
<br /> *Git Stash* <br />

    git stash => salva os arquivos temporariamente para serem adicionados depois.
    git stash apply [#] => aplica as modificações salvas no número da stash que foi específicada. 
    git stash drop => remove o que foi alterado e salvo no stash.
    git stash pop => pega a ultima alteração da stash, faz o merge e aplica as modificações que estavam lá.
    
<br /> *Git Diff* <br />

    git diff => mostra a diferença no arquivo que está sendo editado, porém, caso seja adicionado não retorna nada.
    git diff [hash do commit]..[outra hash do commit]=> mostra a diferença entre dois commits.
        
<br /> *Git Tag* <br />

    git tag -a [v0.1.0] - m "..." => marca o ponto em que não haverá mais alteração naquele estado.

<br /> *Git Cherry-pick* <br />
Pode trazer um commit específico para a branch atual.

<br /> *Git Bisec* <br />
Encontrar o commit em que determinada alteração foi aplicada.

<br /> *Git Blame* <br />
Encontrar o responsável por determinada linha ou bloco de código.

<br /> *Git Show* <br />

    git --graph => exibe o log de commits de uma forma um pouco mais visual, onde as diferentes branches são representadas por linhas separadas.
    
<br /> *Git Graph* <br />

    git show {hash} => mostra todas as alterações aplicadas pelo commit com o hash informado.
    
<br /> *Git Flow* <br />

    git flow => estratégia de organização de branches: Master, Develop, Branches de feature, Branches de Hotfix e Branches de release.


### SSH Public Key

    ssh-keygen -t rsa -C "your@email.com" -b 4096

Para copiar a chave sem precisar abrir o arquivo:

Instalar o XClip: `sudo apt-get install xclip`<br />
OSX: `pbcopy < ~/.ssh/id_rsa.pub`<br />
Linux: `xclip -sel clip < ~/.ssh/id_rsa.pub`<br />
Windows PowerShell: `cat ~/.ssh/id_rsa.pub | clip`
