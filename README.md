<h2> :dart: Objetivo</h2>
O Desafio Você deverá criar 2 aplicações para cadastro de aeronaves. Back-end: Aplicação JavaEE baseada em Web Services no padrão RESTful. (ou de sua escolha). Front-end: Single Page Application que se comunique com estes serviços (ou de sua escolha).

<h2> :bookmark_tabs: Requisitos </h2>
• Permitir o cadastro de aeronaves
• Permitir a atualização de dados de uma aeronave
• Permitir a exclusão de uma aeronave
• Exibir a informação de quantos aeronaves estão como não vendidos na base.
• Exibir a informação da distribuição de aeronaves por década de fabricação
Exemplo:

- Década 1990 -> 15 aeronaves
- Década 2000 -> 31 aeronaves
• Exibir a informação de cadastros de aeronaves por fabricante.
Exemplo:

- Embraer -> 14 aeronaves
- Boeing -> 8 aeronaves
• Exibir as aeronaves registradas durante a última semana.
• Deverá haver consistência nos nomes dos fabricantes. Não poderá haver nomes escritos
de forma errada (Exemplo: Enbraer, Boing, ErBus etc... não serão aceitos no cadastro)


<br id="topo">

<h1 align="center"> Documentação das rotas</br> Entendendo a lógica da API desenvolvida neste projeto. </h1>
<h2> :dart: Objetivo</h2>

<p align="justify"> Este documento tem por objetivo estabeler a documentação das rotas (requisições) constantes dentro deste projeto. Dessa forma, torna-se possível e mais fácil o entendimento do funcionamento da API criada no Back para consumo no Front, estabelecendo a lógica de funcionamento do aplicativo e os parâmetros necessários para cada método utilizado.</p>
<br>


<h2> 📔 MÉTODO: POST (AERONAVE)</h2>

<p align="justify"> Requisição, via JSON, para a criação de uma aeronave no Banco de Dados.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3001/aeronaves/**

<p align="justify"> Exemplo:</p>

```json
{
  "nome": "E3222",
  "marca": "Embraer",
  "ano": 2017,
  "descricao": "Segundo",
  "vendido": true
}
```

<h2> 📔 MÉTODO: GET (AEROANVE)</h2>

<p align="justify"> Requisição para a listagem de todos as aeronaves cadastrados no banco, retornando os resultados no formato JSON.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3001/aeronaves/**

<p align="justify"> Exemplo:</p>

```json
{
 "id": 9,
 "nome": "E3222",
 "marca": "Embraer",
 "ano": 2017,
 "descricao": "Segundo",
 "vendido": true,
 "created": "2024-04-03T19:15:55.972Z",
 "updated": "2024-04-04T22:21:28.000Z"
},
{
 "id": 12,
 "nome": "2321",
 "marca": "Boeing",
 "ano": 2003,
 "descricao": "dwww",
 "vendido": false,
 "created": "2024-04-04T16:48:10.864Z",
 "updated": "2024-04-04T16:48:10.864Z"
},
{
 "id": 18,
 "nome": "rerewrw",
 "marca": "Boeing",
 "ano": 2012,
 "descricao": "3rewwr",
 "vendido": true,
 "created": "2024-04-04T18:16:58.204Z",
 "updated": "2024-04-04T18:16:58.204Z"
}
```


<h2> 📔 MÉTODO: GET Decada (AERONAVE)</h2>

<p align="justify"> Requisição para busca e exibição de aeronaves por década de fabricação, retornando o resultado no formado JSON.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3001/aeronaves/decada**

<p align="justify"> Exemplo:</p>

```json
{
 "2000": 1,
 "2010": 2
}

```

<h2> 📔 MÉTODO: GET Ultima Semana (AERONAVE)</h2>

<p align="justify"> Requisição para busca e exibição de aeronaves registradas durante a última semana, retornando o resultado no formado JSON.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3001/aeronaves/ultima-semana**

<p align="justify"> Exemplo:</p>

```json
{
 "quantidade": 3
}

```

<h2> 📔 MÉTODO: GET pelo ID (AERONAVE)</h2>

<p align="justify"> Requisição para busca e exibição de uma aeronave identificado pelo seu ID no Banco de Dados, retornando o resultado no formado JSON.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3001/aeronaves/9**

<p align="justify"> Exemplo:</p>

```json
{
 "id": 9,
 "nome": "E3222",
 "marca": "Embraer",
 "ano": 2017,
 "descricao": "Segundo",
 "vendido": true,
 "created": "2024-04-03T19:15:55.972Z",
 "updated": "2024-04-04T22:21:28.000Z"
}
```

<h2> 📔 MÉTODO: PUT pelo ID (AERONAVE)</h2>

<p align="justify"> Requisição para alterar os dados de uma aeronave específica, identificado pelo seu ID no Banco de Dados.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3001/aeronaves/9**

<p align="justify"> Exemplo:</p>

```json
{
 "id": 9,
 "nome": "E3222",
 "marca": "Embraer",
 "ano": 2017,
 "descricao": "Teste",
 "vendido": true,
 "created": "2024-04-03T19:15:55.972Z",
 "updated": "2024-04-04T22:21:28.000Z"
}
```
<h2> 📔 MÉTODO: DELETE pelo ID (AERONAVE)</h2>

<p align="justify"> Requisição para deletar uma aeronaves, retornando o resultado no formado JSON.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3001/aeronaves/18**

<p align="justify"> Exemplo:</p>

```json
{
 "nome": "2321",
 "marca": "Boeing",
 "ano": 2003,
 "descricao": "dwww",
 "vendido": false,
 "created": "2024-04-04T16:48:10.864Z",
 "updated": "2024-04-04T16:48:10.864Z"
}


```

