# Testes de Performance - Banco API do Banco com K6

## Introdução
Este repositório contém testes de performance para a API do Banco, desenvolvidos em **JavaScript** utilizando a ferramenta **K6**. O objetivo é avaliar o desempenho, identificar gargalos e garantir que a API suporte cargas de usuários conforme esperado.

---

## Tecnologias Utilizadas
- **JavaScript** - Linguagem utilizada para escrever os testes.
- **K6** - Ferramenta de teste de carga e performance.
- **JSON** - Para armazenamento de dados de teste (como payloads de login e configuração).
- **Variáveis de Ambiente** - Permitem parametrizar a URL base da API (`BASE_URL`) durante a execução dos testes.

---

## Estrutura do Repositório

```
banco-api-performace/
├─ tests/                  # Contém os scripts de teste (login, transferências, etc.)
├─ helpers/                # Funções auxiliares reutilizáveis (autenticação, geração de tokens)
├─ utils/                  # Variáveis e configurações globais (ex.: pegarBaseURL)
├─ fixtures/               # Dados de teste em JSON (ex.: postLogin.json)
├─ config/                 # Arquivos de configuração local (ex.: config.local.json)
├─ README.md               # Este documento
```

---

## Objetivo de Cada Grupo de Arquivos

- **tests/**: Scripts de teste que simulam requisições à API, verificam respostas e registram métricas de performance.
- **helpers/**: Funções auxiliares como `obterToken`, responsáveis por autenticação e lógica repetitiva.
- **utils/**: Arquivos de configuração ou funções globais, como `pegarBaseURL`, para centralizar parâmetros do projeto.
- **fixtures/**: Arquivos JSON que contêm dados de teste (payloads de login, transferências, etc.).
- **config/**: Configurações locais, incluindo URLs e outras variáveis, usadas como fallback caso variáveis de ambiente não estejam definidas.

---

## Modo de Instalação

1. Clone o repositório:
```bash
git clone https://github.com/katarinaluiza1991/banco-api-performace.git
```

2. Navegue até o diretório do projeto:
```bash
cd banco-api-performace
```

3. Instale o K6, caso não tenha instalado:
- Para Windows, via Chocolatey:
```bash
choco install k6
```
- Para MacOS, via Homebrew:
```bash
brew install k6
```
- Para Linux:
```bash
sudo apt install k6
```

---

## Modo de Execução do Projeto

1. Configure a **variável de ambiente `BASE_URL`** apontando para a URL da API:
```bash
export BASE_URL=http://localhost:3000   # Linux / MacOS
set BASE_URL=http://localhost:3000      # Windows
```

2. Execute um teste de login ou outro teste específico:
```bash
k6 run tests/login.test.js
```

3. Para acompanhar o **relatório em tempo real na web** e exportar em HTML, utilize:
```bash
K6_WEB_DASHBOARD=true K6_WEB_DASHBOARD_EXPORT=html-report.html k6 run tests/login.test.js
```
- `K6_WEB_DASHBOARD=true`: Habilita o dashboard em tempo real.
- `K6_WEB_DASHBOARD_EXPORT=html-report.html`: Exporta o relatório para o arquivo HTML.

---

## Observações

- Todos os testes usam dados do diretório `fixtures` e funções auxiliares do `helpers`.  
- É recomendável revisar o arquivo `config/config.local.json` para ajustar a URL base caso não utilize a variável de ambiente.  

---

Repositório: [https://github.com/katarinaluiza1991/banco-api-performace/tree/iniciando-projeto](https://github.com/katarinaluiza1991/banco-api-performace/tree/iniciando-projeto)
