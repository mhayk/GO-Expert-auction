<p align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/9746/9746923.png" width="100" />
</p>
<p align="center">
    <h1 align="center">GO-EXPERT AUCTION</h1>
</p>
<p align="center">
    <em>Desafio da pós em GO Expert</em>
</p>
<p align="center">
	<img src="https://img.shields.io/github/last-commit/mhayk/GO-Expert-auction?style=flat&logo=git&logoColor=white&color=0080ff" alt="last-commit">
	<img src="https://img.shields.io/github/languages/top/mhayk/GO-Expert-auction?style=flat&color=0080ff" alt="repo-top-language">
	<img src="https://img.shields.io/github/languages/count/mhayk/GO-Expert-rate-limiter?style=flat&color=0080ff" alt="repo-language-count">
<p>
<p align="center">
    <em>Developed with ❤️ by Mhayk Whandson</em>
</p>
<p align="center">
		<em>Developed with the language, software and tools below.</em>
</p>
<p align="center">
	<img src="https://img.shields.io/badge/YAML-CB171E.svg?style=flat&logo=YAML&logoColor=white" alt="YAML">
	<img src="https://img.shields.io/badge/V8-4B8BF5.svg?style=flat&logo=V8&logoColor=white" alt="V8">
	<img src="https://img.shields.io/badge/Docker-2496ED.svg?style=flat&logo=Docker&logoColor=white" alt="Docker">
	<img src="https://img.shields.io/badge/Go-00ADD8.svg?style=flat&logo=Go&logoColor=white" alt="Go">
</p>
<hr>

# Lab GO: Leilão com Fechamento Automático

## Descrição do Desafio
Neste desafio, o objetivo é implementar uma nova funcionalidade em um sistema de leilão existente, permitindo que os leilões sejam encerrados automaticamente com base em um tempo pré-definido. Essa funcionalidade deve garantir que, ao atingir o tempo limite configurado, o sistema finalize o leilão de forma confiável, notificando os participantes e registrando o resultado adequadamente.

## 🚀 Iniciando

1. Clone o repositório:
    ```sh
    git clone git@github.com:mhayk/GO-Expert-auction.git
    ```
2. Execute o comando abaixo na pasta raiz do projeto para iniciar o ambiente de desenvolvimento:
    ```sh
    docker-compose build --no-cache
    docker-compose up -d
    ```

   Para parar os serviços:
    ```sh
    docker-compose down
    ```
## 🧪 Testes

## Cria um leilão
```sh
curl -X POST http://localhost:8080/auction \
-H "Content-Type: application/json" \
-d '{
    "product_name": "Marreta do Thor",
    "category": "Category 1",
    "description": "Description 1",
    "condition": 1
}'
```

## Criar um novo lance para o leilão mais recente
```sh
curl -X POST http://localhost:8080/bid \
-H "Content-Type: application/json" \
-d '{
    "user_id": "00000000-0000-0000-0000-000000000000",
    "auction_id": "AUCTION_ID",
    "amount": 25.0
}'
```

## Obter o lance vencedor do leilão mais recente
```sh
curl -X GET http://localhost:8080/auction/winner/AUCTION_ID
```

## Obter informações do leilão mais recente
```sh
curl -X GET http://localhost:8080/auction/AUCTION_ID
```

## Listar todos os leilões
```sh
curl -X GET "http://localhost:8080/auction?status=0"
```

Substitua `AUCTION_ID` pelo ID do leilão que você deseja consultar.
