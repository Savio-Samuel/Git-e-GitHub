# 📚 Anotações de Git e GitHub

> [!NOTE]
> Este repositório reúne minhas anotações de estudo **Git** e **GitHub**. O conteúdo será atualizado conforme avanço nos estudos.

---
# 📝 Índice

| Comando | Função | Seção |
|---------|--------|--------|
| `mkdir` | Cria uma pasta. | [📁 Manipulação de Diretórios](#-manipulação-de-diretórios) |
| `cd` | Entra em uma pasta. | [📁 Manipulação de Diretórios](#-manipulação-de-diretórios) |
| `mv` | Move ou renomeia arquivos e pastas. | [📁 Manipulação de Diretórios](#-manipulação-de-diretórios) |
| `touch` | Cria um arquivo. | [📄 Manipulação de Arquivos](#-manipulação-de-arquivos) |
| `ls` | Lista arquivos. | [📄 Manipulação de Arquivos](#-manipulação-de-arquivos) |
| `ls -a` | Lista arquivos ocultos. | [📄 Manipulação de Arquivos](#-manipulação-de-arquivos) |
| `git init` | Inicializa um repositório Git. | [🌱 Inicializando um Repositório](#-inicializando-um-repositório) |
| `git status` | Exibe o estado dos arquivos. | [📌 Status dos Arquivos](#-status-dos-arquivos) |
| `git add` | Adiciona arquivos à Stage Area. | [📥 Stage Area](#-stage-area) |
| `git rm --cached` | Remove arquivos da Stage Area. | [📥 Stage Area](#-stage-area) |
| `git commit` | Cria um commit. | [💾 Commits](#-commits) |
| `git log` | Exibe o histórico de commits. | [📜 Histórico de Commits](#-histórico-de-commits) |
| `git checkout` | Alterna de branch ou navega entre commits. | [↩️ Desfazendo Alterações](#️-desfazendo-alterações) |
| `git checkout -b` | Cria e acessa uma branch. | [🌿 Branches](#-branches) |
| `git revert` | Desfaz um commit criando outro. | [↩️ Desfazendo Alterações](#️-desfazendo-alterações) |
| `git reset --hard` | Volta para um commit anterior removendo os posteriores. | [↩️ Desfazendo Alterações](#️-desfazendo-alterações) |
| `git branch` | Lista branches. | [🌿 Branches](#-branches) |
| `git branch` | Cria uma branch. | [🌿 Branches](#-branches) |
| `git branch -d` | Exclui uma branch mesclada. | [🌿 Branches](#-branches) |
| `git branch -D` | Força a exclusão de uma branch. | [🌿 Branches](#-branches) |
| `git merge` | Mescla branches. | [🔀 Merge](#-merge) |
| `.gitignore` | Ignora arquivos e diretórios. | [🚫 Arquivo .gitignore](#-arquivo-gitignore) |
| `git remote -v` | Exibe os repositórios remotos. | [☁️ GitHub](#️-github) |
| `git push` | Envia alterações para o GitHub. | [☁️ GitHub](#️-github) |
| `git pull` | Atualiza o repositório local. | [☁️ GitHub](#️-github) |
| `git clone` | Clona um repositório. | [☁️ GitHub](#️-github) |
| `&&` | Executa comandos em sequência. | [⚡ Atalhos](#-atalhos) |

---

# 📁 Manipulação de Diretórios

| Comando | Descrição |
|---------|-----------|
| `mkdir nomeDaPasta` | Cria uma nova pasta. |
| `cd nomeDaPasta` | Entra em uma pasta. |
| `mv origem destino` | Move ou renomeia arquivos e pastas. |

## Exemplo

```bash
mkdir projeto

cd projeto

mv projeto projeto-antigo
```

> [!TIP]
> O comando `mv` pode ser utilizado tanto para mover quanto para renomear arquivos e diretórios.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 📄 Manipulação de Arquivos

| Comando | Descrição |
|---------|-----------|
| `touch nomeDoArquivo` | Cria um novo arquivo. |
| `ls` | Lista os arquivos da pasta atual. |
| `ls -a` | Lista todos os arquivos, inclusive os ocultos. |

## Exemplo

```bash
touch index.html
touch estilos.css
touch script.js

ls
ls -a
```

> [!TIP]
> O comando `ls -a` também exibe arquivos ocultos, como `.git`, `.gitignore` e `.env`.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 🌱 Inicializando um Repositório

| Comando | Descrição |
|---------|-----------|
| `git init` | Inicializa um novo repositório Git. |

## Exemplo

```bash
git init
```

### O que acontece?

Após executar o comando, o Git cria uma pasta oculta chamada:

```text
.git
```

Essa pasta contém todo o histórico e as configurações do repositório.

> [!IMPORTANT]
> Nunca apague a pasta `.git`, pois ela contém todas as informações do repositório.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 📌 Status dos Arquivos

| Comando | Descrição |
|---------|-----------|
| `git status` | Exibe o estado atual dos arquivos do projeto. |

## Exemplo

```bash
git status
```

### Estados possíveis

| Estado | Significado |
|---------|-------------|
| 🔴 **Untracked** | Arquivo novo que o Git ainda não monitora. |
| 🟡 **Modified** | Arquivo alterado após o último commit. |
| 🟢 **Staged** | Arquivo preparado para o próximo commit. |
| ⚪ **Unmodified** | Arquivo sem alterações. |

### Fluxo dos estados

```text
Criar arquivo
      │
      ▼
 Untracked
      │ git add
      ▼
   Staged
      │ git commit
      ▼
 Unmodified
      │ editar
      ▼
  Modified
      │ git add
      ▼
   Staged
```

> [!NOTE]
> O comando `git status` é um dos mais utilizados no Git, pois mostra exatamente a situação atual do projeto.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 📥 Stage Area

A **Stage Area** é uma área temporária onde ficam os arquivos preparados para o próximo commit.

| Comando | Descrição |
|---------|-----------|
| `git add arquivo` | Adiciona um arquivo específico à Stage Area. |
| `git add .` | Adiciona todos os arquivos modificados. |
| `git rm --cached arquivo` | Remove um arquivo da Stage Area sem apagá-lo do computador. |

## Exemplos

Adicionar um arquivo:

```bash
git add index.html
```

Adicionar todos os arquivos:

```bash
git add .
```

Remover da Stage Area:

```bash
git rm --cached index.html
```

### Fluxo

```text
Working Directory
        │
        │ git add
        ▼
    Stage Area
        │
        │ git commit
        ▼
 Repository
```

> [!TIP]
> `git add .` adiciona todos os arquivos modificados de uma única vez.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 💾 Commits

| Comando | Descrição |
|---------|-----------|
| `git commit -m "Mensagem"` | Cria um novo commit com uma mensagem descritiva. |

## Exemplo

```bash
git commit -m "Adiciona página inicial"
```

### Boas práticas

- Utilize mensagens curtas.
- Seja objetivo.
- Explique a alteração realizada.

✅ Exemplos:

```text
Adiciona tela de login

Corrige bug no formulário

Atualiza documentação
```

❌ Evite:

```text
teste

alteração

aaaa
```

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 📜 Histórico de Commits

| Comando | Descrição |
|---------|-----------|
| `git log` | Exibe o histórico completo dos commits. |
| `git log --oneline` | Exibe o histórico resumido. |

## Exemplo

```bash
git log
```

Saída:

```text
commit 46d8ac684f201c9fa129ee4323bfd9fe1a3b8180

Author: Sávio Samuel

Date: Sat Aug 15 19:41:09 2026 -0300

Adicionado código base HTML
```

### O `git log` exibe

- 🆔 Hash do commit
- 👤 Autor
- 📅 Data
- 📝 Mensagem

Para sair da tela, clique na letra:

```text
Q
```

### Histórico resumido

```bash
git log --oneline
```

```text
46d8ac6 Adiciona HTML

1d0ec4b Adiciona CSS

07dda7d Primeiro commit
```

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

# ↩️ Desfazendo Alterações

Existem três maneiras principais de desfazer alterações no Git.

| Comando | Segurança | Altera o histórico? |
|---------|:---------:|:-------------------:|
| `git checkout` | 🟢 Seguro | ❌ Não |
| `git revert` | 🟡 Moderado | ✅ Sim |
| `git reset --hard` | 🔴 Perigoso | ✅ Sim |

---

## 🔄 Git Checkout

Permite visualizar um commit específico **sem alterar o histórico**.

### Exemplo

```bash
git checkout 86b0cdb
```

Para voltar para a branch principal:

```bash
git checkout master
```

ou

```bash
git checkout main
```

> [!TIP]
> Ideal para navegar entre versões do projeto sem apagar commits.

---

## ↩️ Git Revert

Cria um novo commit que desfaz outro commit.

### Exemplo

```bash
git revert 86b0cdb
```

### Resultado

```text
Revert "Mensagem do commit"
```

> [!IMPORTANT]
> O commit original continua existindo. Um novo commit é criado desfazendo as alterações.

---

## 💣 Git Reset

Move a branch para um commit anterior.

### Exemplo

```bash
git reset 86b0cdb --hard
```

> [!WARNING]
> Remove definitivamente todos os commits posteriores e também descarta alterações locais.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 🌿 Branches

As **branches** permitem desenvolver funcionalidades sem alterar diretamente a branch principal.

## Comandos

| Comando | Descrição |
|---------|-----------|
| `git branch` | Lista as branches existentes. |
| `git branch nome` | Cria uma nova branch. |
| `git checkout nome` | Alterna para outra branch. |
| `git checkout -b nome` | Cria e acessa a branch. |
| `git branch -d nome` | Exclui uma branch já mesclada. |
| `git branch -D nome` | Força a exclusão da branch. |

---

## 📋 Listando branches

```bash
git branch
```

Saída:

```text
* master
  login
  cadastro
```

O `*` indica a branch atual.

---

## 🌱 Criando uma branch

```bash
git branch whatsapp
```

A branch será criada, mas você continuará na branch atual.

---

## 🔄 Alterando de branch

```bash
git checkout whatsapp
```

Todos os commits seguintes serão feitos nessa branch.

---

## ⚡ Criando e acessando em um único comando

```bash
git checkout -b svg
```

Equivale a:

```bash
git branch svg
git checkout svg
```

---

## 🗑️ Excluindo uma branch

### Exclusão segura

```bash
git branch -d whatsapp
```

### Exclusão forçada

```bash
git branch -D whatsapp
```

> [!WARNING]
> Não é possível excluir a branch em que você está trabalhando.

Antes faça:

```bash
git checkout master
```

ou

```bash
git checkout main
```

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 🔀 Merge

O comando `git merge` une duas branches.

## Exemplo

Estando na branch principal:

```bash
git checkout master
```

Depois:

```bash
git merge whatsapp
```

### Fluxo

```text
master
   │
   ├─────────────┐
   │             │
   ▼             ▼
whatsapp      alterações
   │             │
   └──────┬──────┘
          ▼
      git merge
          ▼
       master
```

> [!IMPORTANT]
> O merge deve ser executado na branch que receberá as alterações.

> [!TIP]
> Caso existam conflitos, será necessário resolvê-los antes da conclusão do merge.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 🚫 Arquivo `.gitignore`

O arquivo `.gitignore` informa ao Git quais arquivos ou diretórios não devem ser monitorados.

## Exemplo

```gitignore
.env
node_modules/
dist/
```

### Observações

- Muito utilizado para ocultar arquivos sensíveis.
- Também é utilizado para ignorar pastas geradas automaticamente.
- Arquivos que já estavam sendo monitorados antes de entrar no `.gitignore` continuarão sendo monitorados.

Para parar de monitorá-los:

```bash
git rm --cached nomeDoArquivo
```

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# ☁️ GitHub

## Comandos

| Comando | Descrição |
|---------|-----------|
| `git remote -v` | Exibe os repositórios remotos configurados. |
| `git push` | Envia commits para o GitHub. |
| `git pull` | Baixa e integra alterações do GitHub. |
| `git clone` | Clona um repositório remoto. |

---

## 🔗 Verificando o repositório remoto

```bash
git remote -v
```

Saída esperada:

```text
origin git@github.com:usuario/repositorio.git (fetch)
origin git@github.com:usuario/repositorio.git (push)
```

---

## ⬆️ Enviando alterações

```bash
git push
```

ou

```bash
git push origin main
```

```bash
git push origin master
```

---

## ⬇️ Atualizando o projeto

```bash
git pull origin main
```

ou

```bash
git pull origin master
```

---

## 📥 Clonando um projeto

HTTPS

```bash
git clone https://github.com/usuario/repositorio.git
```

SSH

```bash
git clone git@github.com:usuario/repositorio.git
```

> [!NOTE]
> Após o clone, não é necessário executar `git init`.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 📬 Pull Request (PR)

O Pull Request é uma solicitação para que as alterações de uma branch sejam revisadas antes do merge.

### Fluxo

```text
Criar Branch
      │
      ▼
Realizar alterações
      │
      ▼
git add .
      │
      ▼
git commit
      │
      ▼
git push
      │
      ▼
Abrir Pull Request
      │
      ▼
Revisão
      │
      ▼
Merge
```

> [!TIP]
> Após a aprovação, a branch pode ser excluída caso não seja mais necessária.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# 🍴 Fork

O **Fork** cria uma cópia de um projeto na sua conta do GitHub.

## Fluxo

```text
Fork
  │
  ▼
Clone
  │
  ▼
Alterações
  │
  ▼
git add .
  │
  ▼
git commit
  │
  ▼
git push
  │
  ▼
Pull Request
```

## Exemplo

```bash
git clone https://github.com/usuario/repositorio.git

git add .

git commit -m "Corrige erro"

git push
```

> [!NOTE]
> As alterações só chegam ao projeto original após a aprovação do Pull Request.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

# ⚡ Atalhos

## Executando comandos em sequência

```bash
git add . && git commit -m "Mensagem do commit"
```

O segundo comando só será executado se o primeiro for concluído com sucesso.

<p align="right">
<sub><a href="#-índice">⬆️ Voltar ao índice</a></sub>
</p>

---

<p align="center">
Anotações de <strong>Git</strong> e <strong>GitHub</strong> - Sávio Samuel.
</p>
