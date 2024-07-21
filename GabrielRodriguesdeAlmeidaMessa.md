# Exemplo: GitHub

## Diagrama de sequência: jornada completa do usuário

Abaixo está o diagrama de sequência que mostra todo o processo que um usuário passa ao usar o GitHub, desde o login até visualizar pull requests.

```mermaid
sequenceDiagram
    autonumber

    participant User as Usuário
    participant Browser as Navegador
    participant GitHubServer as Servidor GitHub
    participant GitClient as Cliente Git
    participant LocalRepo as Repositório Local

    User->>Browser: Acessa o GitHub
    Browser->>GitHubServer: Solicita página de login
    GitHubServer->>Browser: Retorna página de login
    User->>Browser: Insere credenciais e faz login
    Browser->>GitHubServer: Envia credenciais para autenticação
    GitHubServer->>GitHubServer: Valida credenciais
    GitHubServer->>Browser: Retorna sessão autenticada
    Browser-->>User: Exibe página inicial do GitHub autenticada

    User->>GitClient: Clona repositório
    GitClient->>GitHubServer: Solicita clonagem do repositório
    GitHubServer->>GitClient: Envia dados do repositório
    GitClient->>LocalRepo: Salva repositório localmente

    User->>GitClient: Realiza alterações no arquivo
    GitClient->>LocalRepo: Salva alterações no repositório local
    User->>GitClient: Executa comando de commit
    GitClient->>LocalRepo: Cria commit no repositório local
    User->>GitClient: Executa comando de push
    GitClient->>GitHubServer: Envia commit para o repositório remoto
    GitHubServer->>GitHubServer: Valida e processa commit
    GitHubServer->>GitHubServer: Atualiza repositório com novo commit
    GitHubServer-->>GitClient: Confirmação de commit bem-sucedido
    GitClient-->>User: Exibe mensagem de sucesso

    User->>Browser: Verifica histórico de commits no repositório remoto
    Browser->>GitHubServer: Solicita histórico de commits
    GitHubServer->>Browser: Retorna histórico de commits
    Browser-->>User: Exibe histórico de commits

    User->>Browser: Acessa página de pull requests
    Browser->>GitHubServer: Solicita lista de pull requests
    GitHubServer->>Browser: Retorna lista de pull requests
    Browser-->>User: Exibe pull requests

    User->>Browser: Visualiza detalhes de um pull request
    Browser->>GitHubServer: Solicita detalhes do pull request
    GitHubServer->>Browser: Retorna detalhes do pull request
    Browser-->>User: Exibe detalhes do pull request

Explicação do Diagrama

Login:

O usuário acessa o GitHub e faz login.
O navegador solicita e recebe a página de login do GitHub.
O usuário insere as credenciais, que são enviadas e autenticadas pelo GitHub.
O GitHub retorna uma sessão autenticada e exibe a página inicial.
Clonagem de Repositório:

O usuário clona um repositório usando o Git.
O cliente Git solicita a clonagem ao GitHub.
O GitHub envia os dados do repositório.
O cliente Git salva o repositório no computador do usuário.
Commit e Push:

O usuário faz alterações e salva no repositório local.
O usuário faz commit das alterações.
O usuário faz push do commit para o GitHub.
O GitHub valida e processa o commit.
O GitHub atualiza o repositório e confirma o commit.
Verificação de Commits:

O usuário verifica o histórico de commits no navegador.
O navegador solicita e recebe o histórico de commits do GitHub.
Pull Requests:

O usuário acessa a página de pull requests.
O navegador solicita e recebe a lista de pull requests do GitHub.
O usuário visualiza detalhes de um pull request específico.
Perguntas para o Time do GitHub
Arquitetura e Escalabilidade: Como o GitHub suporta muitos repositórios e usuários ao mesmo tempo?
Consistência de Dados: Como o GitHub garante que os dados estejam corretos e lida com conflitos?
Desafios de Desempenho: Quais foram os maiores desafios de desempenho e como foram resolvidos?
Gerenciamento de Erros: O que acontece se algo der errado durante um commit?
Segurança: Quais medidas de segurança o GitHub usa para proteger os dados?
Integração com Outros Serviços: Como o GitHub se conecta com outras ferramentas, como pipelines de CI/CD?
Manutenção e Atualizações: Como o GitHub gerencia manutenção e atualizações para garantir disponibilidade?

Perguntas para o Time do GitHub

1 - Arquitetura e Escalabilidade: Como o GitHub suporta muitos repositórios e usuários ao mesmo tempo?

2 - Consistência de Dados: Como o GitHub garante que os dados estejam corretos e lida com conflitos?

3 - Desafios de Desempenho: Quais foram os maiores desafios de desempenho e como foram resolvidos?

4 - Gerenciamento de Erros: O que acontece se algo der errado durante um commit?

5 - Segurança: Quais medidas de segurança o GitHub usa para proteger os dados?

6 - Integração com Outros Serviços: Como o GitHub se conecta com outras ferramentas, como pipelines de CI/CD?

7 - Manutenção e Atualizações: Como o GitHub gerencia manutenção e atualizações para garantir disponibilidade?
