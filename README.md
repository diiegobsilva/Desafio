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
}
```


<h2> 📔 MÉTODO: GET pelo parâmetro (AERONAVE)</h2>

<p align="justify"> Requisição para busca e exibição de Aeronave identificado pelo pelo parâmetro passado, retornando o resultado no formado JSON.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3001/equipment/listOne/650daa56a3c4ce65afb9b862**

<p align="justify"> Exemplo:</p>

```json
{
        "_id": "650daa56a3c4ce65afb9b862",
        "type": "Poste",
        "numero": "628",
        "serial": "D-KYEUGG2877",
        "latitude": "12.4569",
        "longitude": "10.4578",
        "observations": "Necessita de manutenção",
        "url": [
            "https://cbrqdjaeurmeftioqfaz.supabase.co/storage/v1/object/public/imagens/D-KYEUGG28770.19592657284536147.jpeg"
        ],
        "status": true
    }
```

<h2> 📔 MÉTODO: GET (USER)</h2>

<p align="justify"> Requisição para a listagem de todos os Usuários cadastrados no aplicativo, retornando os resultados no formado JSON.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3000/user/historicUser**

<p align="justify"> Exemplo:</p>

```json
{
        "id": 32,
        "userCpf": "01234567890",
        "userMatricula": "012345",
        "userTelefone": "99999999999",
        "userName": "Larissa Silva",
        "userEmail": "larissa.silva179@fatec.sp.gov.br",
        "userType": 2,
        "icone": "https://cbrqdjaeurmeftioqfaz.supabase.co/storage/v1/object/public/icone/012345678900.18060346807565758.jpeg"
    },
    {
        "id": 28,
        "userCpf": "12345678900",
        "userMatricula": "a1b2c3",
        "userTelefone": "12999999",
        "userName": "Ana",
        "userEmail": "ana@gmail.com",
        "userType": 2,
        "icone": "https://cbrqdjaeurmeftioqfaz.supabase.co/storage/v1/object/public/icone/8648364840.3938095478661176.jpeg6d827d6d-651b-4eb8-9427-0216ecca4f7b.jpeg0.4829035627709067.jpeg"
    },
    {
        "id": 4,
        "userCpf": "123786789123",
        "userMatricula": "TDX-3213S8",
        "userTelefone": "125673649736452",
        "userName": "Renan",
        "userEmail": "renan@gmail.com",
        "userType": 1,
        "icone": "https://cbrqdjaeurmeftioqfaz.supabase.co/storage/v1/object/public/icone/avatar.png"
    }
```


<h2> 📔 MÉTODO: GET pelo ID (USER)</h2>

<p align="justify"> Requisição para busca e exibição de um Usuário identificado pelo seu ID no Banco de Dados, retornando o resultado no formado JSON.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3000/user/especificoUser/32**

<p align="justify"> Exemplo:</p>

```json
{
    "id": 32,
    "userCpf": "01234567890",
    "userMatricula": "012345",
    "userTelefone": "99999999999",
    "userName": "Larissa Silva",
    "userEmail": "larissa.silva179@fatec.sp.gov.br",
    "userType": 2,
    "icone": "https://cbrqdjaeurmeftioqfaz.supabase.co/storage/v1/object/public/icone/012345678900.18060346807565758.jpeg"
}
```


<h2> 📔 MÉTODO: GET (E-MAIL E STATUS)</h2>

<p align="justify"> Requisição que verifica o e-mail e o status do cadastro que está na parte de análise a ser feita pelo administrador. Quando criado, e-mail é disparado para que o usuário aguarde a análise. Quando aprovado, e-mail é disparado informando que cadastro foi ativado para acesso.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3000/status/renan.mendonca@fatec.sp.gov.br/1**


<h2> 📔 MÉTODO: PUT pelo ID (EQUIPMENT)</h2>

<p align="justify"> Requisição para alterar os dados de um Equipamento específico, identificado pelo seu ID no Banco de Dados.</p>

<p align="justify"> Endereço da rota:</p>

**http://localhost:3001/equipment/updateEquipment/650daa56a3c4ce65afb9b862**

<p align="justify"> Exemplo:</p>

```json
{
    "_id": "650daa56a3c4ce65afb9b862",
    "type": "Poste",
    "numero": "777",
    "serial": "145AE63", <-----
    "latitude": "12.4569",
    "longitude": "10.4578",
    "observations": "Necessita de manutenção",
    "url": [
        "null"
    ],
    "status": false
}
```

