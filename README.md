# Consulta do Clima | Previsão Meteorológica

Aplicação web desenvolvida para pesquisar cidades brasileiras e consultar informações meteorológicas utilizando requisições HTTP à API pública da BrasilAPI (CPTEC).

## 📌 Sobre o Projeto

O projeto permite pesquisar uma cidade pelo nome, visualizar as correspondências encontradas e selecionar uma delas para consultar sua previsão do tempo.

A aplicação utiliza JavaScript assíncrono (`async/await`) e a função `fetch()` para consumir os endpoints da BrasilAPI, processando as respostas em JSON e apresentando os dados meteorológicos na interface.

## ✨ Funcionalidades

- **Pesquisa de cidades:** busca cidades brasileiras pelo nome informado.
- **Lista de resultados:** apresenta as cidades encontradas e seus respectivos estados.
- **Seleção de cidade:** permite selecionar um resultado para consultar sua previsão.
- **Consulta meteorológica:** obtém os dados de previsão associados à cidade selecionada.
- **Informações climáticas:** apresenta temperatura mínima, máxima, condição do tempo e índice UV.
- **Formatação de datas:** converte as datas retornadas pela API para o formato brasileiro (`DD/MM/AAAA`).
- **Feedback visual:** apresenta mensagens durante as consultas e informa erros retornados pela API.
- **Pesquisa por teclado:** permite iniciar a busca pressionando Enter.

## 🌤️ Informações Exibidas

| Informação | Descrição |
|---|---|
| Cidade | Nome da cidade selecionada |
| Estado | Estado correspondente |
| Data | Data da previsão |
| Condição | Descrição das condições meteorológicas |
| Temperatura mínima | Menor temperatura prevista (°C) |
| Temperatura máxima | Maior temperatura prevista (°C) |
| Índice UV | Índice de radiação ultravioleta |

## 🔄 Funcionamento

A aplicação realiza duas requisições HTTP principais:

### 1. Pesquisa de cidades

O usuário informa o nome de uma cidade. O JavaScript envia uma requisição para a BrasilAPI:

```javascript
const resposta = await fetch(
    `https://brasilapi.com.br/api/cptec/v1/cidade/${nome}`
);

const dados = await resposta.json();
```

A API retorna uma lista de cidades correspondentes à pesquisa.

Cada resultado é apresentado na interface e recebe um evento de clique que permite consultar sua previsão utilizando o identificador da cidade.

### 2. Consulta da previsão

Após selecionar uma cidade, a aplicação utiliza seu identificador para realizar uma nova requisição:

```javascript
const resposta = await fetch(
    `https://brasilapi.com.br/api/cptec/v1/clima/previsao/${id}`
);

const dados = await resposta.json();
```

Os dados retornados são utilizados para apresentar as informações meteorológicas da cidade selecionada.

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Finalidade |
|---|---|
| HTML5 | Estruturação da página |
| CSS3 | Estilização e organização visual |
| JavaScript | Lógica e manipulação da interface |
| Fetch API | Realização de requisições HTTP |
| Async/Await | Controle de operações assíncronas |
| JSON | Formato de comunicação e transferência de dados |
| BrasilAPI (CPTEC) | Fornecimento dos dados meteorológicos |

## 📂 Estrutura do Projeto

```text
atv-requisi-oweb/
│
├── css/
│   └── index.css
│
├── js/
│   └── index.js
│
├── index.html
├── package.json
└── package-lock.json
```

## ⚙️ Como Executar

### 1. Pré-requisitos

- Navegador atualizado.
- Conexão com a internet.

### 2. Clonar o repositório

```bash
git clone https://github.com/EnzoSuzukiProkopas/atv-requisi-oweb.git
```

### 3. Acessar a pasta

```bash
cd atv-requisi-oweb
```

### 4. Executar a aplicação

Abra o arquivo `index.html` diretamente no navegador.

Também é possível utilizar a extensão **Live Server** do Visual Studio Code para executar a página em um servidor local.

> Não é necessário executar `npm install` ou iniciar um servidor Node.js para utilizar a aplicação, pois ela funciona diretamente no navegador.

## 🌐 API Utilizada

**BrasilAPI — CPTEC**

A aplicação utiliza os serviços meteorológicos disponibilizados pela BrasilAPI.

**Endpoint de pesquisa de cidades:**

```http
GET https://brasilapi.com.br/api/cptec/v1/cidade/{nome}
```

**Endpoint de previsão meteorológica:**

```http
GET https://brasilapi.com.br/api/cptec/v1/clima/previsao/{id}
```

- Documentação: https://brasilapi.com.br/
- Método HTTP: `GET`
- Formato de resposta: JSON

## 🎓 Contexto Acadêmico

Projeto desenvolvido como atividade acadêmica, com foco na prática de requisições HTTP, consumo de APIs externas, manipulação de dados JSON e utilização de JavaScript assíncrono.

## 👨‍💻 Autor

**Enzo Suzuki Prokopas**

- GitHub: [@EnzoSuzukiProkopas](https://github.com/EnzoSuzukiProkopas)
- Repositório: [atv-requisi-oweb](https://github.com/EnzoSuzukiProkopas/atv-requisi-oweb)

---

<p align="center">
  Desenvolvido para fins acadêmicos.
</p>
