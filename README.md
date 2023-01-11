# Fake-api-covid

## Endpoint

 (https://fake-api-covid.onrender.com)

 [![Run in Insomnia}](https://insomnia.rest/images/run.svg)](https://insomnia.rest/run/?label=Fake-api-covid&uri=https%3A%2F%2Fraw.githubusercontent.com%2Flucasraujo%2FFake-api-covid%2Fmain%2FInsomnia_2023-01-11.json)

# Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

## exemplo de resposta: 
~~~json
}
	"accessToken":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImtlbnppbmhvQG1haWwuY29tIiwiaWF0IjoxNjczNDUxMDE3LCJleHAiOjE2NzM0NTQ2MTcsInN1YiI6IjEifQ.J6zeOpTimkvYq9P_4B4j2FVqEljn-ONUf_g-ResgNUs",
	"user": {
		"email": "kenzinho@mail.com",
		"name": "Kenzinho",
		"age": 38,
		"id": 1
	}
}
~~~
<br>


# Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

## exemplo de resposta: 

~~~json
{
	"accessToken":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImtlbnppbmhvQG1haWwuY29tIiwiaWF0IjoxNjczNDUxMDE3LCJleHAiOjE2NzM0NTQ2MTcsInN1YiI6IjEifQ.J6zeOpTimkvYq9P_4B4j2FVqEljn-ONUf_g-ResgNUs",
	"user": {
		"email": "kenzinho@mail.com",
		"name": "Kenzinho",
		"age": 38,
		"id": 1
	}
}
~~~

# pegar usuario

Get/users/1  <- O numero 1 representa o id do usuario.<br/>

Voce tambem precisa fornecer o tokem do usuario

## exemplo de resposta: 
~~~json
{
	"email": "kenzinho@mail.com",
	"password": "$2a$10$YQiiz0ANVwIgpOjYXPxc0O9H2XeX3m8OoY1xk7OGgxTnOJnsZU7FO",
	"name": "Kenzinho",
	"age": 38,
	"id": 1
}
~~~

# Adicionar aos favoritos

POST /favoriteIds <br/>

Voce precisa fornecer o tokem do usuario e o corpo da requisição com o seguinte padrão : 

~~~json
{
	"favoriteObject": {
		"country": "Bolivia",
		"cases": 19,
		"confirmed": 19,
		"deaths": 0,
		"recovered": 0,
		"updated_at": "2020-03-21T12:43:08.000Z"
	},
	"userId": 1  <- Presisamos pasar o id do usuario 
}
~~~

## exemplo de resposta: 
~~~json
{
	"favoriteObject":{
      "country": "Bolivia",
      "cases": 19,
      "confirmed": 19,
      "deaths": 0,
      "recovered": 0,
      "updated_at": "2020-03-21T12:43:08.000Z"
    },
	"userId":1,
	"id":12
}
~~~
# Pegar os favoritos do usuario 

GET /favoriteIds?userId=1  <-colocamos o id do usuario aqui  <br/>

Voce precisa fornecer o tokem do usuario e nao precisa de corpo 

## exemplo de resposta: <br>
~~~json
[
	{
		"favoriteObject": {
			"country": "Bolivia",
			"cases": 19,
			"confirmed": 19,
			"deaths": 0,
			"recovered": 0,
			"updated_at": "2020-03-21T12:43:08.000Z"
		},
		"userId": 1,
		"id": 6
	}
]

~~~

# Deletar dos favoritos do usuario

DELETE/ favoriteIds/4  <- O numero 4 representa o id do objeto a ser deletado<br/>

Voce tambem precisa fornecer o tokem do usuario 


# Pegar Mapas dos estados 

GET/listMapsUfs 

E nao pecisa passar mais nada 

## exemplo de resposta: <br>
~~~json
[
	{
		"state": "AC",
		"map": "https://kenzie-academy-brasil-developers.github.io/mapsstates/ac.svg"
	},
	{
		"state": "AL",
		"map": "https://kenzie-academy-brasil-developers.github.io/mapsstates/al.svg"
	},
	{
		"state": "AP",
		"map": "https://kenzie-academy-brasil-developers.github.io/mapsstates/ap.svg"
	}
 ... etc
]

~~~


# pagar  os dados da populaçao de cada estado 

GET/listBrazilDataPopulation

E nao pecisa passar mais nada 

## exemplo de resposta:

~~~json
[
	{
		"state": "AC",
		"population": 829780,
		"percentagePopulation": 0.4
	},
	{
		"state": "AL",
		"population": 3125254,
		"percentagePopulation": 1.5
	},
	{
		"state": "AP",
		"population": 774268,
		"percentagePopulation": 0.4
	},
	...etc

]
~~~

# pegar todo o histocico de casos 

GET/listBrazilHistoryCases

E nao pecisa passar mais nada 

## exemplo de resposta:
~~~json
[
	{
		"totalTested": 1496,
		"testedNotInfected": 1413,
		"infected": 121,
		"deceased": 0,
		"infectedByRegion": [
			{
				"state": "RO",
				"count": 0
			},
			{
				"state": "AC",
				"count": 0
			},
			{

				},
requisiçao com mais de 200.000 linhas
~~~





