# 🚀 NestJS Hello World — Fundamentos & Arquitetura Modular

![NestJS](https://img.shields.io/badge/NestJS-11.0-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.7-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Jest](https://img.shields.io/badge/Jest-30.0-C21325?style=for-the-badge&logo=jest&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge)
![Licença](https://img.shields.io/badge/Licença-MIT-yellow?style=for-the-badge)

---

## 🔗 Acesso e Rotas da Aplicação

* **Ambiente de Execução Local:** `http://localhost:3000` (ou porta definida na variável de ambiente `PORT`)
* **Endpoint Raiz:** `http://localhost:3000/`
* **Endpoint da Turma:** `http://localhost:3000/turma`

---

## 📖 Visão Geral

O **generation_JS13_nest_hello-world** é um projeto prático desenvolvido durante o início da trilha de back-end do bootcamp **Generation Brasil (Turma JS13)**, estruturado para introduzir e fixar os conceitos fundamentais do framework **NestJS 11** sob o ecossistema do **TypeScript** e **Node.js**.

A aplicação atua como a fundação arquitetural para o desenvolvimento de microsserviços e APIs corporativas, demonstrando a aplicação do padrão **Inversão de Controle (IoC)**, **Injeção de Dependências**, configuração dinâmica de ambiente com `@nestjs/config` e testes automatizados de integração end-to-end (e2e).

---

## ✨ Funcionalidades

* 🌐 **Endpoints de Saudação e Identificação:**
  * `GET /`: Retorna a mensagem padrão de integridade do servidor (`Hello World!`).
  * `GET /turma`: Retorna a mensagem temática de integração da turma de formação (`A turma js13 é TOP!`).
* ⚙️ **Configuração Dinâmica de Portas:** Leitura dinâmica da porta do servidor através do `ConfigService` integrado ao `AppModule`, permitindo flexibilidade para deploy em plataformas de nuvem (Render, Railway, Heroku).
* 🧪 **Garantia de Qualidade Automatizada:** Suíte de testes de ponta a ponta validando o comportamento do servidor HTTP, códigos de status e respostas textuais.

---

## 🎯 Diferenciais e Destaques Técnicos

1. **Injeção de Dependências Nativa:** Separação estrita entre o Controlador (`AppController`), responsável exclusivamente por receber as requisições HTTP e roteá-las, e o Provedor de Serviço (`AppService`), encarregado da lógica de negócio.
2. **Uso Global do `ConfigModule`:** Integração do pacote `@nestjs/config` com `isGlobal: true`, centralizando o carregamento de variáveis de ambiente sem acoplamento.
3. **Padrão de Inicialização Assíncrona:** Bootstrap limpo no `main.ts` utilizando a fábrica assíncrona `NestFactory.create` e resolução de serviços via `app.get(ConfigService)`.
4. **Testes Automatizados com Supertest:** Teste e2e em `test/app.e2e-spec.ts` simulando requisições HTTP reais em memória sobre o servidor Express encapsulado pelo NestJS.

---

## 🏗️ Arquitetura e Estrutura de Pastas

```text
generation_JS13_nest_hello-world/
├── src/
│   ├── app.controller.ts       # Rotas HTTP GET / e GET /turma
│   ├── app.module.ts           # Módulo raiz importando ConfigModule e declarando controllers/providers
│   ├── app.service.ts          # Provedor com regras de negócio e retorno de mensagens
│   └── main.ts                 # Ponto de entrada da aplicação com leitura de porta dinâmica
├── test/
│   ├── app.e2e-spec.ts         # Teste automatizado de ponta a ponta (e2e)
│   └── jest-e2e.json           # Configurações do Jest para testes e2e
├── nest-cli.json               # Configurações da CLI do NestJS
├── package.json                # Metadados, scripts e dependências do projeto
├── tsconfig.json               # Configurações do compilador TypeScript
└── README.md                   # Documentação técnica consolidada do projeto
```

---

## 📋 Tabela de Endpoints

| Método | Rota | Descrição | Status HTTP | Resposta |
| :--- | :--- | :--- | :--- | :--- |
| `GET` | `/` | Retorna saudação inicial de integridade | `200 OK` | `Hello World!` |
| `GET` | `/turma` | Mensagem temática da Turma JS13 | `200 OK` | `A turma js13 é TOP!` |

---

## ⚙️ Requisitos e Instalação

### Pré-requisitos
* **Node.js:** Versão 18 ou superior.
* **Gerenciador de Pacotes:** `npm` (incluso no Node.js).
* **Git:** Para clonagem e controle de versão.

### 1. Clonar o Repositório
```bash
git clone https://github.com/erickystn/generation_JS13_nest_hello-world.git
cd generation_JS13_nest_hello-world
```

### 2. Instalar as Dependências
```bash
npm install
```

### 3. Configurar Variáveis de Ambiente (Opcional)
Caso queira alterar a porta de execução padrão (`3000`), crie um arquivo `.env` na raiz do projeto:
```env
PORT=8080
```

---

## 🚀 Como Executar

```bash
# Executar em modo de desenvolvimento (com recarga automática via watch mode):
npm run start:dev

# Compilar o código TypeScript para JavaScript (dist/):
npm run build

# Executar a versão compilada em modo de produção:
npm run start:prod
```

---

## 💻 Exemplos de Requisições via cURL

### 1. Consultar Endpoint Raiz
```bash
curl -X GET http://localhost:3000/
```
**Resposta esperada:**
```text
Hello World!
```

### 2. Consultar Endpoint `/turma`
```bash
curl -X GET http://localhost:3000/turma
```
**Resposta esperada:**
```text
A turma js13 é TOP!
```

---

## 🧪 Suíte de Testes

```bash
# Executar testes unitários
npm run test

# Executar testes end-to-end (e2e) com Supertest
npm run test:e2e

# Gerar relatório de cobertura de código
npm run test:cov
```

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Versão | Finalidade |
| :--- | :--- | :--- |
| **NestJS** | 11.0 | Framework progressivo para back-end corporativo |
| **TypeScript** | 5.7 | Superset com tipagem estática e decorators |
| **@nestjs/config** | 4.0 | Gerenciamento de variáveis de ambiente com dotenv |
| **RxJS** | 7.8 | Biblioteca reativa para programação funcional assíncrona |
| **Jest** | 30.0 | Framework de testes unitários e asserções |
| **Supertest** | 7.0 | Módulo para testes de integração sobre requisições HTTP |
| **Prettier & ESLint**| 3.4 / 9.18 | Padronização e qualidade estilística de código |

---

## 📈 Próximos Passos de Evolução Arquitetural

Este projeto serviu como base para a evolução gradual das demais APIs do bootcamp:
- [x] Criação de endpoints simples e injeção de dependências.
- [x] Configuração dinâmica de portas de ambiente.
- [ ] Integração com TypeORM e persistência relacional MySQL/PostgreSQL (implementado em `generation_JS13_Projeto_Loja_Games` e `generation_JS13_blogpessoal`).
- [ ] Autenticação com Passport e JWT.
- [ ] Validações de entrada com DTOs e `class-validator`.

---

## 👤 Autor & 📄 Licença

Desenvolvido por **[Ericky Sant'ana](https://github.com/erickystn)** durante o bootcamp da **Generation Brasil**.

Distribuído sob a licença **MIT**.
