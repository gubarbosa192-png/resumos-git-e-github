# DIO | Resumos Git e GitHub

Repositório para armazenar resumos sobre Git e GitHub do Curso "Versionamento de Código com Git e GitHub" da [Digital Innovation One.](https://www.dio.me/)

## 📚 Documentação
- [Documentação Git](https://git-scm.com/doc)
- [Documentação GitHub](https://docs.github.com/pt?hl=pt)


## 1. Iniciando o git

- git init

Rodando esse comando na sua pasta será criado um novo repositório local.
Caso essa pasta ja seja um repositório, esse será reiniciado.


## 2. Trabalhando com Repositório remoto

Repositório remoto consite em um repositorio com **serviço de nuvem**, o qual o codigo fica armazenado além do repositório local 

Exemplos de serviços de nuvem: Github, Gitlab, Bitbucket

| Relacionando repositório local com remoto |
|-------------------------------------------|

- *git remote add* https://github.com/Username/Nome_do_repositório.git


## 3. Adicionando/Removendo arquivos da área de preparação

| Adicionando: |
|--------------|

- *git add*

Antes de ficar disponível para um commit, os arquivos e/ou pastas do seu repositório precisam ser adicionados ao Git index, ou área de preparação.

O Git index contém as últimas alterações da sua árvore de trabalho antes do próximo commit.

| Uso:|
|-----|
Para todas as alterações:
- *git add .*

Para um arquivo específico:
- *git add* <nome_do_arquivo>

Para uma pasta específica:
- *git add* <nome_da_pasta>

|Removendo: |
|-----------|

- *git reset HEAD* 

O comando reset retorna a zona do buffer para HEAD. Isso limpa a zona do buffer das mudanças que nós acabamos de adicionar ao Git index, ou área de preparação.

| Uso: |
|------|

Para todos os arquivos da área de preparação:
- *git reset HEAD*

Para um arquivo específico:
- *git reset HEAD <nome_do_arquivo>*

Para uma pasta específica:
- *git reset HEAD <nome_da_pasta>*

## 4. Commits

- *git commit -m 'mensagem do commit'*

| Área de stage |
|---------------|

Área onde adicionamos quais modificações serão versionadas pelo git no próximo commit. Para adicionar arquivos na _stage area_ utilizamos o comando *git add*. Podemos adicionar arquivos específicos ou todos os arquivos modificados:
Para arquivos especificos: - *git add <filename>*
Para todos os arquivos: *git add* .

| Commit |
|--------|
"Salva" as modificações nos arquivos (desde que estejam na área de _stage_) e adiciona mais um ponto na linha do tempo do projeto. Para realizar um commit, utiliza-se o seguinte comando.

- *git commit -m '<mensagem do commit>*

| Atalho |
|--------|

Com o comando abaixo, irá adicionar todos os arquivos modificados na área de _stage_ e também realizar o commit com a mensagem escolhida:

- *git commit -am 'mensagem do commit*

| Histórico de commits |
|----------------------|

O comando abaixo irá listar os commits feitos no repositório em ordem cronológica inversa. Além disso, esse comando listará cada commit com o seu checksum SHA-1, o nome e email do autor, data de inserção, e a mensagem do commit.

- *git log*

Caso deseje uma lista de commits agrupados pelo autor, basta utilizar o comando:

- *git shortlog*

## 5. Criando branches

Esse **master** é um **branch** que o git cria automagicamente quando você faz um commit sem estar em nenhum branch (como é o caso de um repositório recém criado).

> OBS: No github, por default, todo novo repo terá a branch nomeada como **main**, substituindo o branch **master**.

Quando usamos Git, quase todas as operações são feitas dentro de um branch. Um branch nada mais é que uma lista de commits. Você pode criar, apagar e renomear branches.

Para listar as branches presentes no repositório você usa *git branch. Para criar você usa o comando *git branch* NOME_DO_BRANCH*. Para apagar *git branch -D NOME_DO_BRANCH*. Para renomear você usa *git branch -m NOME_ANTIGO NOME_NOVO*. E para mudar de branch você usa *git checkout NOME_DO_BRANCH*.

Exemplo:

- *git branch* - lista as branches
- *git branch work* - cria o branch work
- *git branch -D work*- apaga o branch work
- **git branch -m work asdrubal* - renomeia o branch work para asdrubal
- *git checkout work* - muda para a branch work

| Unindo branches |
|-----------------|

Para combinar as mudanças feitas de uma branch para outra branch usamos o comando - *git merge <nome_da_branch>*.

Exemplo: Unindo as mudanças feitas na branch **new_feature** na branch atual:

- *git merge new_feature*
| Verificando diferenças |
|------------------------|

Para verificar as diferenças entre duas branches (ou dois arquivos) basta utilizar o seguinte comando:

- *git diff <branch_1> <branch_2>* ou *git diff <arquivo_1> <arquivo_2>*

## 6. Clonando repositórios

Para criar uma cópia local de um repositório remoto use o comando:
- *git clone <remote_URL>*

## 7. Atualizando repositórios

 Repositório local (`git pull`)

Para atualizar seu **repositório local** com as últimas alterações feitas no repositório remoto use o comando:
- *git pull <remote_URL ou remote_name> <nome_da_branch>*

**Exemplo**:
Atualizando branch atual com a branch remota feature:
- *git pull origin feature*

| **Repositório remoto** (`git push`) |
|-------------------------------------|

Para atualizar seu *repositório remoto* com as últimas alterações feitas no repositório local use o comando:

- *git push <remote_URL ou remote_name> <nome_da_branch>*


## 8. Contribuindo com repositórios de terceiros

Um grande diferencial de plataformas **open-source** é a possibilidade de **contribuir com repositórios de terceiros**, para isso é preciso seguir os seguintes passos:

**1 -** Vá até o repositório que deseja contribuir:

- *https://github.com/Username/Nome_do_repositório*

**2 -** Fork o repositório, com isso você criará uma **ramificação** do repositório principal, a qual poderá fazer mudanças, pois essa será a **SUA** versão do projeto principal

**3 -** Clone seu repositório "forkado" do projeto principal com:
 - *git clone https://github.com/Seu_Username/Nome_do_repositório.git*

**4 -** Crie uma nova Branch:
- *cd repositório git branch nome_da_nova_branch*


**5 -** Mude para a nova branch: 
- *git checkout nome_da_nova_branch*

**6 -** Faça alterações no seu repositório "forkado" e use o comando push
já que esta ultilizando uma nova branch, use o comando:
 - *git push --set-upstream origin nome_da_nova_branch*


**7 -** No github clique em **"Compare e Pull Request"** para enviar para o usuário do repositório as mudanças feitas comparadas com o repositório principal, com isso ele irá analisar as alterações e decidir aceitar ou não suas mudanças, com um Merge(adicionar suas mudanças ao codigo principal)
**obs: importante deixar um comentário no pull request, explicando oque foi alterado no código**

## 9. Otimização e Integridade

 |  Otimização  |
 |--------------|

Para otimizar o seu repositório em questões de performance, utilize o comando:

- *git gc*

Ele identifica e apaga arquivos desnecessários. *gc* é uma abreviação para _garbage collector_.

| Integridade |
|-------------|

Para verificar a integridade dos arquivos do seu repositório e checar se há alguma corrupção em arquivos, utilize o comando:

- *git fsck*

*fsck* é uma abreviação para File System Check.

## 🔎 Referencias
[Digital Innovation One](https://www.dio.me/)

[Atlassian](https://www.atlassian.com/br/git)

[Git](https://git-scm.com/)