# Webservice

## Requerimentos

- PHP 7.4
- Apache 2
- MySQL
- PHPMyAdmin

## Install 

### Clone project

Clone esse repositório para o seu computador local ou servidor, diretório ```www``` ou ```public_html```.

    git clone https://github.com/coderealmhub/rspedidos-webservice.git

ou faça o download projeto.

[https://github.com/coderealmhub/rspedidos-webservice/archive/main.zip](https://github.com/coderealmhub/rspedidos-webservice/archive/main.zip)

### Configurando ```.htaccess``` no webservice

No diretório raiz do seu projeto, crie um arquivo ```.htaccess``` e cole o seguinte bloco de código,
para dar permissão de escrita nos arquivos e remover ```ìndex.php``` da url.

    <IfModule mod_rewrite.c>
        RewriteEngine On
        #Checks to see if the user is attempting to access a valid file,
        #such as an image or css document, if this isn't true it sends the
        #request to index.php
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteCond %{REQUEST_FILENAME} !-d
        #This last condition enables access to the images and css folders, and the robots.txt file
        RewriteCond $1 !^(index\.php|public|images|robots\.txt|css)
        RewriteRule ^(.*)$ index.php/$1 [L]
    </IfModule>

### Database

#### Manualmente

Para configurar o banco de dados manualmente, importe o arquivo ```.sql```
que está nesse repositório [https://github.com/coderealmhub/rspedidos-database](https://github.com/coderealmhub/rspedidos-database) para o seu banco de dados.

#### Automaticamente

> Experimental, em construção

Para configurar o banco de dados automaticamente use migration.

1. Acesse ```config >> migration.php``` e ative/desative a migração em:
    
        $config['migration_enabled'] = TRUE;
   
2. Inicie a migração da seguinte forma:

        https://yourdomanin.com/rspedidos/migrate

        {
            "message": "Table Migrated Successfully."
        }

> Atenção: após a migração, desative a mesma para evitar migrações por terceiros ou acidentais.

### Configuração do ambiente de desenvolvimento

Na raiz do seu projeto, crie um arquivo ```.env``` de acordo com seu ambiente, copiando conforme
exemplifica o arquivo ```.env.example``` para a configuração do banco de dados e outras configurações.

Exemplo: ```.env```, ```.env.development```, ```.env.testing```, ```.env.production```.

    DB_CONNECTION    = mysqli
    DB_HOST          = localhost
    DB_DATABASE      = database
    DB_USERNAME      = root
    DB_PASSWORD      = root

## Update source code

Para receber atualizações da API RS Pedidos, execute a seguinte instrução:

    git pull


## Guia de uso

Acesse a documentação [Postman](https://documenter.getpostman.com/view/2943437/TVsygRJg).

## Evolução

Essa API busca respeitar [SemVer](https://semver.org/lang/pt-BR/). Nesse sentido, mudanças compatíveis não devem gerar nova versão major.

A versão da API é composta por 4 elementos: major, minor, patch e release candidate. A versão v[x]que consta no path da URL é o elemento major da versão da API. A evolução da versão se dá seguinte forma:

* Major: alterações incompatíveis, com quebra de contrato (v1.0.0 → v2.0.0)
* Minor: alterações compatíveis, sem quebra de contrato (v1.1.0 → v1.2.0)
* Patch: bugfixes, esclarecimentos às especificações, sem alterações funcionais (v1.1.1 → v1.1.2)
* Release candidate: versões de pré-lançamento de qualquer patch futuro, minor ou major (v1.0.0-rc.1 → v1.0.0-rc.22)

Alterações sem quebra de contrato e esclarecimentos às especificações podem ocorrer a qualquer momento. Clientes devem estar preparados para lidar com essas mudanças sem quebrar.

# Banco de Dados

[Diagrama do banco de dados.](https://drive.google.com/file/d/1bfNfXLuHHE43d_TW_YnZnUsCCwpFQbTK/view?usp=sharing)