# Erros

## Tratamento de erros

A API retorna códigos de status HTTP para indicar sucesso ou falhas das requisições.

Códigos 2xx indicam sucesso. Códigos 4xx indicam falhas causadas pelas informações enviadas pelo cliente ou pelo estado atual das entidades. Códigos 5xx indicam problemas no serviço no lado da API.

As respostas de erro incluem no corpo detalhes do erro seguindo o schema da RFC 7807.

O campo type identifica o tipo de erro e na API segue o padrão:

    https://yourdomain.com.br/rspedidos/v1/error/<TipoErro>

O padrão acima listado, referente ao campo type, não consiste, necessariamente, em uma URL que apresentará uma página web válida, ou um endpoint válido, embora possa, futuramente, ser exatamente o caso. O objetivo primário é apenas e tão somente identificar o tipo de erro.

Abaixo estão listados os tipos de erro e possíveis violações da API.

### Gerais
Esta seção reúne erros que poderiam ser retornados por quaisquer endpoints listados na API.

#### RequisicaoInvalida
- Significado: Requisição inválida.
- HTTP Status Code: [400 Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1).

#### AcessoNegado
- Significado: Requisição de participante autenticado que viola alguma regra de autorização.
- HTTP Status Code: [403 Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3).

#### NaoEncontrado
- Significado: Entidade não encontrada.
- HTTP Status Code: [404 Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4).

#### PermanentementeRemovido
- Significado: Indica que a entidade existia, mas foi permanentemente removida.
- HTTP Status Code: [410 Gone](https://tools.ietf.org/html/rfc7231#section-6.5.9).

#### ErroInternoDoServidor
- Significado: Condição inesperada ao processar requisição.
- HTTP Status Code: [500 Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1).

#### ServicoIndisponivel
- Significado: Serviço não está disponível no momento. Serviço solicitado pode estar em manutenção ou fora da janela de funcionamento.
- HTTP Status Code: [503 Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4).

#### IndisponibilidadePorTempoEsgotado
- Significado: Indica que o serviço demorou além do esperado para retornar.
- HTTP Status Code: [504 Gateway Timeout](https://tools.ietf.org/html/rfc7231#section-6.6.5).

## Teste

### Servidor bloqueando métodos HTTP

Teste rapidamente se seu servidor está habilitado para receber requisições com os métodos HTTP ```GET```
```POST``` ```PUT``` ```PATHC``` ```DELETE``` enviando comandos CURL pelo terminal. Especifique ```--request``` ou ```-X```.

- GET

Request:

    curl --request GET https://yourdomain.com.br/v1/testverbs

Response:

    {"method":"GET","status":true}

- POST

Request:

    curl --request POST https://yourdomain.com.br/v1/testverbs

Response:

    {"method":"POST","status":true}

- PUT

Request:

    curl --request PUT https://yourdomain.com.br/v1/testverbs

Response:

    {"method":"PUT","status":true}

- DELETE

Request:

    curl --request DELETE https://yourdomain.com.br/v1/testverbs
    
Response:

    {"method":"DELETE","status":true}

- PATCH

Request:

    curl --request PATCH https://yourdomain.com.br/v1/testverbs

Response:

    {"method":"PATCH","status":true}

## Erros comuns 

### Fatal error: Maximum execution time of 60 seconds exceeded in .. 

[Fatal error: Maximum execution time of 60 seconds exceeded in .. ](https://suporte.hostgator.com.br/hc/pt-br/articles/115000384093-Qual-%C3%A9-o-limite-de-conex%C3%B5es-simult%C3%A2neas-ao-MySQL-#:~:text=Vinte%20e%20cinco%20conex%C3%B5es%20simult%C3%A2neas,raramente%20atingir%C3%A1%2025%20conex%C3%B5es%20simult%C3%A2neas.)