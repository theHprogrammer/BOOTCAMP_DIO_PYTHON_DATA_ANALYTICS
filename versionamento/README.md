# Versionamento de Código com Git e GitHub

## Índice
1. [Visão Geral do Curso e Ferramentas](#visão-geral-do-curso-e-ferramentas)
2. [Instalação e Configuração do Git e GitHub](#instalação-e-configuração-do-git-e-github)
3. [Primeiros Passos com Git e GitHub Parte 1](#primeiros-passos-com-git-e-github-parte-1)
3. [Primeiros Passos com Git e GitHub Parte 2](#primeiros-passos-com-git-e-github-parte-2)

---

## Visão Geral do Curso e Ferramentas
### O que é Versionamento de Código?
O versionamento de código é um processo de gerenciamento de diversas versões de um conjunto de arquivos de código. Ele permite que os desenvolvedores acompanhem e controlem as alterações realizadas ao longo do tempo, facilitando a identificação de quando e por quem uma alteração específica foi feita. O versionamento é essencial para coordenar o trabalho em equipe, permitindo que múltiplas pessoas trabalhem em diferentes partes do mesmo projeto sem conflitos.

### Sistemas de Controle de Versão
Sistemas de Controle de Versão (VCS) são ferramentas que ajudam no gerenciamento de diferentes versões de arquivos de código. Eles registram alterações feitas ao longo do tempo, mantendo um histórico de quem fez o quê e quando. Os VCS oferecem organização, controle e segurança para os projetos de software.

### Tipos de Sistemas de Controle de Versão
- **VCS Centralizado (CVCS)**: No modelo centralizado, todos os arquivos e históricos são armazenados em um servidor central. Os desenvolvedores trabalham com cópias desses arquivos e devem se comunicar com o servidor central para obter as versões mais recentes ou para submeter suas alterações.
- **VCS Distribuído (DVCS)**: No DVCS, cada desenvolvedor tem uma cópia completa do repositório, incluindo o histórico de alterações. Isso possibilita um fluxo de trabalho mais flexível e a capacidade de trabalhar offline. As alterações são compartilhadas entre repositórios, permitindo uma colaboração eficaz mesmo com equipes distribuídas geograficamente.

### O que é Git?
Git é um sistema de controle de versão distribuído, gratuito e open source. É conhecido por sua eficiência em lidar com projetos de todos os tamanhos, com destaque para suas capacidades de ramificação (branching) e fusões (merging). Git é leve, rápido e foi desenvolvido para oferecer integridade e suporte para fluxos de trabalho não-lineares.

- **Breve Histórico do Git**: O Git foi criado em 2005 por Linus Torvalds e sua equipe como uma resposta à necessidade de um VCS eficiente para o desenvolvimento do kernel do Linux, após conflitos com o uso de um sistema proprietário. Desde então, tornou-se um dos sistemas de controle de versão mais utilizados mundialmente.
- **Fluxo Básico no Git**: O fluxo básico de trabalho no Git envolve clonar um repositório existente, realizar mudanças locais, fazer commits dessas mudanças, e finalmente enviar (push) as alterações para um repositório remoto. Também inclui o ato de atualizar o repositório local com mudanças vindas do repositório remoto (pull).

### O que é GitHub?
GitHub é uma plataforma de hospedagem de código-fonte e controle de versão que utiliza o Git. Ela permite a colaboração entre desenvolvedores e oferece diversas funcionalidades para o gerenciamento de projetos de software, como controle de acesso, gerenciamento de tarefas e solicitações de pull.

- **Breve Histórico do GitHub**: O GitHub foi lançado em 2008 e rapidamente se tornou uma das principais plataformas para hospedagem de projetos de código aberto. Em 2018, foi adquirido pela Microsoft Corporation.

### Git ≠ GitHub
É importante diferenciar Git de GitHub. O Git é o sistema de controle de versão, enquanto o GitHub é um serviço baseado em nuvem que hospeda repositórios Git e adiciona muitas funcionalidades voltadas para a colaboração em projetos de software.

---

## Instalação e Configuração do Git e GitHub

### Instalando o Git

#### Windows
1. **Baixar o Git**: Acesse [Git for Windows](https://gitforwindows.org/) e baixe o instalador.
2. **Executar o Instalador**: Siga as instruções de instalação, escolhendo as configurações que se adequem às suas necessidades.
3. **Verificar a Instalação**: Abra o Prompt de Comando ou Git Bash e digite `git --version`.

#### Linux (Ubuntu)
1. **Instalar via Terminal**: Abra o Terminal e digite `sudo apt-get install git`.
2. **Verificar a Instalação**: No Terminal, digite `git --version`.

#### macOS
1. **Instalar via Homebrew**: Se você tem o Homebrew, pode instalar o Git com o comando `brew install git`.
2. **Instalar manualmente**: Baixe o instalador do Git no site [Git SCM for Mac](https://sourceforge.net/projects/git-osx-installer/).
3. **Verificar a Instalação**: Abra o Terminal e digite `git --version`.

### Configurando o Git
Após a instalação, configure suas informações de usuário no Git.

1. **Definir Nome e E-mail**: 
   - No Terminal ou Prompt de Comando, digite:
     - `git config --global user.name "Seu Nome"`
     - `git config --global user.email "seuemail@example.com"`
2. **Verificar Configurações**: Utilize `git config --list` para conferir as configurações.

### Autenticação via Token
Para autenticar no GitHub via token:

1. **Gerar Token**: Acesse as configurações de sua conta no GitHub, vá para 'Developer settings' > 'Tokens' > 'Generate new token'.
2. **Configurar Git**: Utilize o token gerado como senha ao fazer operações no GitHub que requeiram autenticação.

### Armazenando Credenciais
Para armazenar suas credenciais do Git:

- **Via Cache**: Utilize `git config --global credential.helper cache` para armazenar temporariamente.
- **Permanentemente**: Utilize `git config --global credential.helper store` para salvar as credenciais.

### Autenticando via Chave SSH
Para autenticar via chave SSH:

1. **Gerar Chave SSH**: No Terminal ou Git Bash, digite `ssh-keygen -t rsa -b 4096 -C "seuemail@example.com"`.
2. **Adicionar ao ssh-agent**: Após a geração, adicione a chave ao ssh-agent.
3. **Adicionar ao GitHub**: No GitHub, vá para 'Settings' > 'SSH and GPG keys' > 'New SSH key' e adicione sua chave SSH.

---

## Primeiros Passos com Git e GitHub Parte 1

### Criando e Clonando Repositórios
Aprenda as duas formas fundamentais de iniciar trabalhos com Git: transformando um diretório local em um repositório Git e clonando um repositório Git existente.

### Criando um Repositório Local
1. **Inicialização**: Navegue até a pasta desejada e inicie um repositório Git com `git init`.
2. **Conectar com Repositório Remoto**: Use `git remote add origin [URL]` para conectar seu repositório local com um remoto.

### Clonando um Repositório
Para clonar um repositório Git existente:
1. **Obter URL**: No GitHub, copie a URL do repositório (HTTPS ou SSH).
2. **Clonar Repositório**: No terminal, digite `git clone [URL]`.

### Criando um Repositório Remoto
No GitHub:
1. **Criar Novo Repositório**: Clique em "New repository".
2. **Configurar Repositório**: Defina nome, descrição e visibilidade.
3. **Inicialização Opcional**: Escolha inicializar com README, .gitignore ou licença.
4. **Criar Repositório**: Clique em “Create repository”.

### Salvando Alterações no Repositório Local
1. **Adicionar Mudanças**: Use `git add [arquivo]` ou `git add .` para adicionar todas as mudanças.
2. **Commitar Mudanças**: Com `git commit -m "mensagem"`, crie um commit com sua mensagem.

Claro, vou expandir a seção sobre desfazendo alterações com mais detalhes sobre os diferentes tipos de `git reset`:

### Desfazendo Alterações no Repositório Local

1. **Alterar Mensagem do Último Commit**: Use `git commit --amend -m "nova mensagem"` para alterar a mensagem do último commit.

2. **Desfazendo Commits com `git reset`**: O comando `git reset` pode ser usado de três maneiras principais:
   - **`git reset --soft [commit]`**: Desfaz o último commit, mas mantém as alterações nos arquivos (staged).
   - **`git reset [commit]`** ou **`git reset --mixed [commit]`**: Remove o último commit e desfaz as alterações dos arquivos (unstaged), mas mantém as alterações no diretório de trabalho.
   - **`git reset --hard [commit]`**: Remove todos os commits e alterações desde o commit especificado. Cuidado: esta ação é destrutiva e não pode ser desfeita.

Em cada caso, `[commit]` refere-se ao identificador do commit até o qual você deseja resetar. Por exemplo, `HEAD~1` para o commit anterior.

### Enviando Alterações para o Repositório Remoto
1. **Enviar Mudanças**: Com `git push`, envie os commits para o repositório remoto.
2. **Atualizar Repositório Local**: Com `git pull`, atualize seu repositório local com mudanças do remoto.

---

## Primeiros Passos com Git e GitHub Parte 2

### Trabalhando com Branches

Branches no Git permitem aos desenvolvedores trabalhar em diferentes funcionalidades ou versões de um projeto simultaneamente, sem interferir no trabalho principal ou em outras branches. Isso facilita a experimentação, o desenvolvimento de novas funcionalidades e a correção de bugs, mantendo o código principal estável.

1. **Criando uma Nova Branch**:
   - Para criar uma nova branch, use `git branch nome-da-branch`.
   - Mude para a nova branch com `git checkout nome-da-branch`.
   - Use `git checkout -b nome-da-branch`, para criar uma nova branch e imediatamente mudar para ela.

2. **Fluxo de Trabalho com Branches**:
   - Faça alterações no código e comite essas mudanças na sua branch.
   - Use `git push origin nome-da-branch` para enviar as alterações para o repositório remoto.

3. **Integrando Branches**:
   - Para integrar as mudanças de uma branch de volta ao main, use `git merge nome-da-branch` enquanto estiver na branch `main`.
   - Alternativamente, você pode abrir um Pull Request no GitHub se estiver trabalhando colaborativamente.

4. **Deletando Branches**:
   - Após a integração, a branch pode ser deletada com `git branch -d nome-da-branch` para remoção local e `git push origin --delete nome-da-branch` para remoção remota.

5. **Visualizando Branches**:
   - Use `git branch` para ver todas as branches locais.
   - Para ver branches remotas, use `git branch -r`.
   - Para verificar o último commit de cada bbrach, use `git branch -v`.

## 👨‍💻 Author

<table align="center">
    <tr>
        <td align="center">
            <a href="https://github.com/theHprogrammer">
                <img src="https://avatars.githubusercontent.com/u/79870881?v=4" width="150px;" alt="Helder's Image" />
                <br />
                <sub><b>Helder Henrique</b></sub>
            </a>
        </td>    
    </tr>
</table>
<h4 align="center">
   By: <a href="https://www.linkedin.com/in/theHprogrammer/" target="_blank"> Helder Henrique </a>
</h4>