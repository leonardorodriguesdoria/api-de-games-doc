# API DE GAMES
ESTA API SERVE PARA TESTAR CONHECIMENTOS
##Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça, você vai receber a listagem de todos os games
Exemplo de Resposta: 
```
[
  {
    "id": 23,
    "title": "Fallout 3",
    "year": 2006,
    "price": 60
  },
  {
    "id": 65,
    "title": "Call of Duty Black Ops 2",
    "year": 2012,
    "price": 80
  },
  {
    "id": 2,
    "title": "The Elder Scrolls V: Skyrim",
    "year": 2011,
    "price": 75
  }
]

```
##### Falha na autenticação 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha no processo de autenticação da requisição. Motivos: Token inválido, Token expirado
Exemplo de Resposta:
```
{
  "error": "Token Inválido"
}
```


##Endpoints
### POST /auth
Esse endpoint é responsável por fazer o processo de login
#### Parametros
email: E-mail do usuário cadastrado no sistema

password: Senha do usuário cadastrada no sistema, com aquele determinado e-mail

Exmplo:
```
{
  "email": "leordoria2016@gmail.com",
  "password": "nodejs<3"
}

```
#### Respostas
##### OK! 200
Caso essa resposta aconteça, você vai receber o token jwt para conseguir acessar endpoints protegidos na API
Exemplo de Resposta: 
```
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJsZW9yZG9yaWEyMDE2QGdtYWlsLmNvbSIsImlhdCI6MTY3MjE3MTkwNCwiZXhwIjoxNjcyMzQ0NzA0fQ.XXc2DMZ8LS0WITwBiu4BsFSe7Gp8Ep6BBMbmziM9B-U"
}

```
##### Falha na autenticação 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha no processo de autenticação da requisição. Motivos: Senha ou e-mail incorretos
Exemplo de Resposta:
```
{err: "CREDENCIAIS INVÁLIDAS"}
```
