<p align="center">
    <img alt="Logo Febrafar" src="https://raw.githubusercontent.com/FebrafarDev/desafio/main/static/logo-febrafar.png?raw=true" width="360">
</p>

# Desafio Backend Inovação Febrafar

Ficamos felizes em ter você por aqui e queremos te desejar boa sorte!

Siga as instruções com calma e não deixe de evidenciar o seu progresso, mesmo que não consiga concluir totalmente o desafio.

# Regras

- Crie um repositório privado na sua conta do Github
- Ao final do desafio, compartilhe o acesso ao repositório com [@Rodrigo](https://github.com/Leonavas) e [@Mikail](https://github.com/ajukas)

## Criar uma aplicação para cálculo de pontos e números da sorte

### Descrição:

A Febrafar é responsável por realizar campanhas sazonais de vendas de produtos nas farmácias. Para incentivar as vendas, os balconistas das lojas recebem pontos para cada venda realizada e esses pontos acumulam durante a campanha, e a cada 100 pontos, o balconista ganha um número da sorte para concorrer a um sorteio ao final da campanha. O objetivo da aplicação é calcular a quantidade de pontos que o balconista vai ganhar ao realizar uma venda (que será fornecida como exemplo) e também a quantidade de números da sorte.

### Como calcular a quantidade de pontos:
- 10 pontos por venda
- 50 pontos para cada produto promocional
- aplicar um multiplicador externo

### Como obter o multiplicador:

O multiplicador será obtido através da API do open weather (API de clima):

`GET http://api.openweathermap.org/data/2.5/weather?q={cidade}&appid={key}`

multiplicador = temperatura °C / 5 (valor inteiro)

### Resultado Esperado:

Criar uma aplicação que seja capaz de receber os dados de uma venda hipotética e retornar a quantidade de pontos e números da sorte que o balconista recebeu.

### Requisitos:
- A aplicação deve rodar de maneira local em Linux ou Windows
- A linguagem de programação utilizada é de livre escolha, porém recomendamos Javascript/Typescript (Node), Python ou Golang
- A criação de testes não é obrigatória, mas é um diferencial
- O código deve ser bem organizado, simples e fácil de entender
- Deve ser criado um README com instruções para rodar a aplicação

### Lista de EANs de produtos promocionais:
- 7896094903272
- 7896331703443
- 7896641808630
- 7891058001155
- 7891058168049

### Exemplo de JSON de venda:
```json
{
   "id_venda": "000001",
   "data_venda": "2024-05-31 12:00:00",
   "id_balconista": "123",
   "valor_total": 150.10,
   "itens_venda": [
       {
           "ean": "7896094903272",
           "quantidade": 10,
           "valor_unitario": 1.99
       },
       {
           "ean": "7896004803456",
           "quantidade": 5,
           "valor_unitario": 9.50
       },
       {
           "ean": "7896331703443",
           "quantidade": 2,
           "valor_unitario": 14.90
       },
       {
           "ean": "7891058168049",
           "quantidade": 1,
           "valor_unitario": 52.90
       }
   ]
}
```