# 1) Configuração Inicial do Git
$ git config --global user.name "Fulano de Tal"
$ git config --global user.email fulanodetal@exemplo.br

-- setando o editor padrão emacs
$ git config --global core.editor emacs 

-- listando as configurações:
$ git config --list

https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Configura%C3%A7%C3%A3o-Inicial-do-Git


# 2)  Fazer com que o git não solicite senha a cada push (GitHub)
$ sssh-keygen -- vai dando enter
$ cat ~/.ssh/id_rsa.pub

Acesse sua conta no GitHub, clique no canto superior direito na sua foto e depois em Settings (ou configurações).
Clique em SSH and GPG keys e depois em New SSH key.
Agora, você precisa colar a sua chave pública

# 3) Fazer com que o git não solicite senha a cada push (GitLab)
Acessa a conta do gitlab, sobre seu ícone de usuário, settings. Access tokens, dê um nome para o token, marque a opção api e clique em criar.
Com o token gerado, informe no link abaixo 

git remote set-url origin https://<user>:<token>@git.repositorio.git

Se fizer a primeira vez o git clone conforme abaixo, não precisa fazer set-url:
git clone http://<user>:<token>@git.repositorio.git

https://fullcycle.com.br/git-e-github/

# 4) How do you clone a Git repository into a specific folder?
git clone https://github.com/eugenp/tutorials.git  <nome da pasta>

# Adicionando uma pasta a um novo repositorio
echo "# flutter" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/<user>/flutter.git
git push -u origin main

# Exemplo de como trabalhar com GitFlow
https://www.youtube.com/watch?v=wzxBR4pOTTs&list=PLDqnSpzNKDvkfF_ZMfukmOG3MtGKfXlfJ&index=5

# Mergeando uma branch para outra
Entrar na branch que irá receber as alterações e depois:
git merge feature/sua_branch
Mais informações: https://www.atlassian.com/br/git/tutorials/using-branches/git-merge

# Salvar alterações sem commit: git stash
-- listar stash´s salvos: 
git stash list

-- salvar na área de stach: 
Salvar tudo: git stash save "nome para o stash"  
    -> Obs.: somente arquivos que foram dados add (rastreados). Caso queria os não rastreados, passar parâmetro -u
Salvar apenas alguns arquivos: git stash save "nome para o stash"  -- arquivo1 arquivo2 arquivo3 ...



-- tirar da área de stach e aplicar na área de trabalho (branch corrente): 
git stash pop               ---> stach do topo (último inserido). Funciona como uma pilha
git stash pop stash@{2}     ---> stach específico

-- mantém da área de stach e aplicar na área de trabalho (branch corrente): 
git stash apply  
Obs: recurso para aplicar alterações em mais ramificações

-- Criar uma branch a partir de uma stash:
git stash branch nome-da-branch stash@{1}

-- excluir stash´s
Excluir um específico: git stash drop stash@{1}
Excluir todos: git stash clear

-- Revertendo um commit
git log
git revert <numero do commit>
https://www.baeldung.com/git-revert-commit#:~:text=Reverting%20a%20Commit%20with%20git,commit%20with%20the%20inverse%20content.

-- Revert git init
rm -rf .git

-- Renomear a branch master para main
git branch --move master main

-- Criando um repositório novo no github
a) No github crie o novo repositorio
b) Em sua pasta (que será seu repositório) digite:
git init
git branch --move master main
git add .
git commit -m "first commit"
git remote add origin https://github.com/<user>/<repository>.git
git push -u origin main

-- adicionar, commitar e dar push em um único comando
git commit -a -m "commit" && git push
            ou
git add . && git commit -a -m "commit" && git push     
No caso do windows poderia criar um bat que recebe o parâmetro com a descrição do commit. Ex.:
git add . && git commit -a -m %1 && git push     


-- Para criar arquivos .gitignore
http://gitignore.io

-- Api´s rests do GitHub:
https://docs.github.com/en/rest

-- Criando um repositório por linha de comando
Linux:
curl -u "user:token" https://api.github.com/user/repos -d '{"name":"NEW_REPO_NAME","private":false}'

Windows: --> Necessidade de escapar no Windows Prompt
curl -u "user:token" https://api.github.com/user/repos -d "{\"name\":\"NEW_REPO_NAME\",\"private\":false}"



