# Fake-api-covid

## Endpoint

 (https://fake-api-covid.onrender.com)

# Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

## exemplo de resposta: 
{<br>
	"accessToken":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImtlbnppbmhvQG1haWwuY29tIiwiaWF0IjoxNjczNDUxMDE3LCJleHAiOjE2NzM0NTQ2MTcsInN1YiI6IjEifQ.J6zeOpTimkvYq9P_4B4j2FVqEljn-ONUf_g-ResgNUs",<br>
	"user": {<br>
		"email": "kenzinho@mail.com",<br>
		"name": "Kenzinho",<br>
		"age": 38,<br>
		"id": 1<br>
	}<br>
}<br>


# Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

## exemplo de resposta: 
{<br>
	"accessToken":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImtlbnppbmhvQG1haWwuY29tIiwiaWF0IjoxNjczNDUxMDE3LCJleHAiOjE2NzM0NTQ2MTcsInN1YiI6IjEifQ.J6zeOpTimkvYq9P_4B4j2FVqEljn-ONUf_g-ResgNUs",<br>
	"user": {<br>
		"email": "kenzinho@mail.com",<br>
		"name": "Kenzinho",<br>
		"age": 38,<br>
		"id": 1<br>
	}<br>
}<br>


# pegar usuario

Get/users/1  <- O numero 1 representa o id do usuario.<br/>

Voce tambem precisa fornecer o tokem do usuario

## exemplo de resposta: 
{<br>
	"email": "kenzinho@mail.com",<br>
	"password": "$2a$10$YQiiz0ANVwIgpOjYXPxc0O9H2XeX3m8OoY1xk7OGgxTnOJnsZU7FO",<br>
	"name": "Kenzinho",<br>
	"age": 38,<br>
	"id": 1<br>
}<br>


# Adicionar aos favoritos

POST /favoriteIds <br/>

Voce precisa fornecer o tokem do usuario e o corpo da requisição com o seguinte padrão : 


{<br>
	"favoriteObject": {<br>
		"country": "Bolivia",<br>
		"cases": 19,<br>
		"confirmed": 19,<br>
		"deaths": 0,<br>
		"recovered": 0,<br>
		"updated_at": "2020-03-21T12:43:08.000Z"<br>
	},<br>
	"userId": 1  <- Presisamos pasar o id do usuario 
}<br>


## exemplo de resposta: 

{<br>
	"favoriteObject":{<br>
      "country": "Bolivia",<br>
      "cases": 19,<br>
      "confirmed": 19,<br>
      "deaths": 0,<br>
      "recovered": 0,<br>
      "updated_at": "2020-03-21T12:43:08.000Z"<br>
    },<br>
	"userId":1,<br>
	"id":12<br>
}<br>

# Pegar os favoritos do usuario 

GET /favoriteIds?userId=1  <-colocamos o id do usuario aqui  <br/>

Voce precisa fornecer o tokem do usuario e nao precisa de corpo 

## exemplo de resposta: <br>

[<br>
	{<br>
		"favoriteObject": {<br>
			"country": "Bolivia",<br>
			"cases": 19,<br>
			"confirmed": 19,<br>
			"deaths": 0,<br>
			"recovered": 0,<br>
			"updated_at": "2020-03-21T12:43:08.000Z"<br>
		},<br>
		"userId": 1,<br>
		"id": 6<br>
	}<br>
]


# Deletar dos favoritos do usuario

DELETE/ favoriteIds/4  <- O numero 4 representa o id do objeto a ser deletado<br/>

Voce tambem precisa fornecer o tokem do usuario 


# Pegar Mapas dos estados 

GET/listMapsUfs 

E nao pecisa passar mais nada 


# pagar  os dados da populaçao de cada estado 

GET/listBrazilDataPopulation

E nao pecisa passar mais nada 

# pegar todo o histocico de casos 

GET/listBrazilHistoryCases

E nao pecisa passar mais nada 
