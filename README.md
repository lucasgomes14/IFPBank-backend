# 🏦 IFPBank | O Banco Digital do IFPB

Este projeto é um protótipo de **Banco Digital** desenvolvido como base para a aplicação dos conceitos de **Gerenciamento de Configuração e Mudanças (GCM)**, da disciplina do curso de Análise e Desenvolvimento de Sistemas do IFPB - Campus Esperança.

O foco é demonstrar o controle sobre a evolução do sistema, desde a identificação dos itens de configuração até a documentação e aprovação de mudanças críticas.

## 🧭 Menu de Navegação

1.  [Sobre a Disciplina](#1-sobre-a-disciplina-gerência-e-configuração-e-mudanças)
2.  [Arquitetura e Tecnologias](#2-arquitetura-e-tecnologias)
3.  [Itens de Configuração (ICs)](#3-itens-de-configuração-ics)
4.  [Controle de Mudanças (DSM)](#4-controle-de-mudanças-documento-de-solicitação-de-mudança---dsm)
5.  [Equipe de Desenvolvimento](#5-equipe-de-desenvolvimento)
6.  [Como Rodar o Projeto](#6-como-rodar-o-projeto)
7.  [Licença](#7-licença)

-----

## 1\. Sobre a Disciplina: Gerência e Configuração e Mudanças

A Gerência de Configuração é uma disciplina que visa controlar a evolução de sistemas complexos para evitar perda de controle e inconsistências, garantindo a integridade e rastreabilidade dos itens de configuração ao longo do ciclo de vida do software.

**Conceitos Fundamentais Aplicados:**

* **Identificação da Configuração:** Definição dos itens críticos (código, documentos, configurações).
* **Controle de Mudanças:** Processo formal para solicitação, avaliação, aprovação e rastreamento de todas as alterações no sistema.
* **Auditoria de Configuração:** Verificação de que o sistema implementado corresponde à versão documentada e aprovada.
* **Linha de Base:** Estado formalmente aprovado e documentado dos itens de configuração em um dado momento.

## 2\. Tecnologia

Este projeto utiliza o ecossistema Spring Boot para construir a API REST que serve de base para o banco digital.
## 3\. Itens de Configuração (ICs)

A tabela abaixo lista os principais Itens de Configuração (ICs) identificados e documentados para o projeto IFPBank na **Linha de Base inicial (v1.0.0)**. Estes itens são o foco do controle de versão e do processo de Gerenciamento de Mudanças.

| Item de Configuração | Tipo | Plataforma | Localização (Simulada) | Versão | Responsável | Dependências |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `Login.java` | Script | Web | `/web/auth/` | `v1.0.0` | Lucas | `Seguranca.java` |
| `Seguranca.java` | Script | Web | `/web/auth/` | `v1.0.0` | Patrícia | - |
| `Login.js` | Código-fonte | Web | `/web/auth/` | `v1.0.0` | Richard | `Login.css` |
| `config.yml` | Configuração | Web | `/config/` | `v1.0.0` | Todos | - |

## 4\. Controle de Mudanças (Documento de Solicitação de Mudança - DSM)

O **Documento de Solicitação de Mudança (DSM)** formaliza a necessidade de alteração de um ou mais Itens de Configuração, sendo a peça central da disciplina.

Abaixo está o registro da primeira Solicitação de Mudança formalizada para este projeto:

| Campo | Detalhe |
| :--- | :--- |
| **Código da Mudança** | DSM-2025-001 |
| **Data da Solicitação** | 17/10/2025 |
| **Solicitante** | Prof. Álvaro Magum |
| **Projeto** | Banco Digital (IFPBank) |
| **Versão Atual** | v1.0.0 |
| **Tipo de Mudança** | Evolutiva |

**Descrição da Mudança:**
Solicita-se a implementação de um novo módulo de autenticação para a Tela Inicial do Sistema, incorporando um mecanismo de segurança baseado em criptografia robusta. A mudança visa garantir que as credenciais do usuário e o tráfego de dados sensíveis atendam aos requisitos mínimos de proteção, substituindo a validação atual por um fluxo de autenticação completo e seguro.

**Justificativa:**
Sendo um Banco Digital, a segurança e a integridade dos dados são requisitos CRÍTICOS. Esta solicitação visa garantir que a funcionalidade básica de *login* esteja estruturada com *hashing* de senhas (ex: bcrypt) e que o canal de comunicação seja criptografado (TLS).

**Impacto Esperado:**
**ALTO.** A mudança é crítica, pois afeta o núcleo da autenticação. Requer modificação e validação de segurança nos Itens de Configuração de Login (Front-end e Back-end) e no módulo de Segurança para a correta aplicação dos algoritmos de criptografia.

**Aprovação:**

| Aprovador Responsável | Cargo | Data |
| :--- | :--- | :--- |
| Lucas Lima | Desenvolvedor Back-End | 18/10/2025 |
| Patrícia Santos | Desenvolvedora Back-End | 18/10/2025 |
| Richard Salviano | Desenvolvedor Front-End | 18/10/2025 |

## 5\. Equipe de Desenvolvimento

Esta equipe é responsável pela manutenção e evolução dos Itens de Configuração do projeto IFPBank.

<table width="100%"> 
    <thead> 
        <tr> 
            <th>Avatar</th> 
            <th>Nome</th> 
            <th>Função</th> 
        </tr> 
    </thead> 
    <tbody> 
        <tr> 
            <td> <img src="https://avatars.githubusercontent.com/u/40415279?v=4" width="100px;" alt="Avatar Richard"/> </td> 
            <td><strong>Richard Salviano</strong></td> 
            <td>Desenvolvedor Front-End</td> 
        </tr> 
        <tr> 
            <td> <img src="https://avatars.githubusercontent.com/u/62152683?v=4" width="100px;" alt="Avatar Lucas"/> </td> 
            <td><strong>Lucas Lima</strong></td> 
            <td>Desenvolvedor Back-End</td> 
        </tr> 
        <tr> 
            <td> <img src="https://avatars.githubusercontent.com/u/54537516?v=4" width="100px;" alt="Avatar Patrícia"/> </td> 
            <td><strong>Patrícia Santos</strong></td> 
            <td>Desenvolvedora Back-End</td> </tr> </tbody> 
</table>

## 6\. Como Rodar o Projeto

Este projeto utiliza Maven para gerenciar as dependências e o ciclo de vida da aplicação.
### Pré-requisitos

 
* **Java JDK:** Versão recomendada: `v21` ou superior.
* **Apache Maven:** Versão `3.8.x` ou superior.

### Instalação e Execução

Siga os passos abaixo no seu terminal (PowerShell, CMD, Bash, etc.):

1.  **Clone o Repositório ou Baixe o ZIP:**
    ```bash
    git https://github.com/lucasgomes14/IFPBank-backend.git
    cd IFPBank-backend
    ```
2.  **Instale as Dependências:**
    Este comando baixa todos os pacotes necessários (React, MUI, Vite, etc.).
    ```bash
    npm install
    ```
3.  **Inicie o Servidor de Desenvolvimento:**
    Este comando inicia o servidor Vite.
    ```bash
    mvn spring-boot:run
    ```

Após a execução, a API estará rodando e pronta para receber requisições em:
**`http://localhost:8080/api/auth/login`**
**`http://localhost:8080/api/auth/logout`**

Você pode testar os endpoints com ferramentas como Postman, Insomnia ou curl.

## 7\. Licença

Este projeto foi desenvolvido exclusivamente para fins didáticos e acadêmicos (Disciplina de Gerência e Configuração de Mudanças do IFPB).

A cópia, reprodução ou uso do código-fonte, dados e documentação fora do contexto do curso deve ser solicitada e autorizada pelo autor principal antes da utilização.