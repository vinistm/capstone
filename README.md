### API - CAPTSONE

Esse sera o Backend utilizado durante a construcao do nosso Capstone.

O objetivo dessa aplicação vai ser consultar, e publicar questoes voltadas ao campo politico visando que esatamos em ano de eleicoes, para facilitar a consulta e a pesquisa da populacao em dados relacionados a politicos brasileiros.


### Endopoints

A API tem um total de 12 endpoints, que servem para que o usuario possa se registrar na rede social, editar as suas postagens, excluir as suas postagens, onde todos os usuarios tanto logados como deslogados podem visualizar, existem também outros endpoints na parte da cola dos seus candidatos, onde o usuário pode criar uma lista de candidatos, para que, na hora da votacao ele consiga lembrar dos seus candidatos e nao precise levar os "santinhos" dos politicos evitando o desperdicio de papel


### Rotas que nao precisam de autenticacao 

### Listar Postagens

Qualquer usuário mesmo sem fazer o login durante a aplicacao pode ver todas as postagens feitas no site

GET /dashboard - FORMATO DA RESPOSTA - STATUS 200

`
 [
	{
		"post": "Gostaria de saber como o deputado Tiririca esta se saindo",
		"name": "Teste",
		"userId": 1
	}
]
`

### Listar Candidatos

GET /candidatos - FORMATO DA RESPOSTA - STATUS 200

Qualquer usuario pode ver os candidatos listados na aplicacao

`
[
	{
		"name": "Candidato1",
		"numero": "11111",
		"partido": "TT",
		"cidade": "Curitiba",
		"cargo": "vereador",
		"categoria": "educação",
		"userId": 1,
		"id": 1,
		"historia": " vereador desde 2132 esta concorrendo pelo seu mandato pela 4554 vez."
	},
	{
		"name": "Candidato2",
		"numero": "222",
		"partido": "AA",
		"cidade": "Curitiba",
		"cargo": "Senador",
		"categoria": "segurança",
		"userId": 1,
		"id": 2
	},
]
`

### Rotas que precisam de autenticacao 

### Criar/deletar/editar um post

POST,DELETE,PATCH /dashboard - FORMATO DA REQUISICAO

`
	{
		"post": "Gostaria de saber como o deputado Tiririca esta se saindo",
		"name": "Teste",
		"userId": 1
	}
`

### Criar/deletar/editar um candidato

POST,DELETE,PATCH /candidatos - FORMATO DA REQUISICAO

`
	{
		"name": "Candidato1",
		"numero": "11111",
		"partido": "TT",
		"cidade": "Curitiba",
		"cargo": "vereador",
		"categoria": "educação",
		"historia": " vereador desde 2132 esta concorrendo pelo seu mandato pela 4554 vez."
	}
`
