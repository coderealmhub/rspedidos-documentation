# App Android

# Requerimentos

- [Android Studio](https://developer.android.com/studio?hl=pt-br)

## Clone project

Clone esse repositório para o seu computador local ou servidor, diretório www ou public_html.

    git clone https://github.com/coderealmhub/rspedidos-android.git

ou faça o download do projeto diretamente.

[https://github.com/coderealmhub/rspedidos-android/archive/master.zip](https://github.com/coderealmhub/rspedidos-android/archive/master.zip)

## Configuration Endpoint

Navegando dentro do projeto abra o pacote ```br.com.coderealm.rspedidos``` >>> ```api``` >>> ```API.java``` e altere a URL Base:

    public static final String URL_BASE = "https://youtdomain.com.br/rspedidos/v1/";

## Configuration Endpoint

Navegando dentro do projeto abra o pacote ```br.com.coderealm.rspedidos``` >>> ```config``` >>> ```Config.java``` e altere SECRET_KEY_APP_CLIENT:

    public static final String SECRET_KEY_APP_CLIENT = "you_secret_key_app_client";

## Generating an APK

No menu do Android Studio clique em: Build >> Build Bundle(s)/ APK(s) >> Build APK.

# Banco de Dados

[Diagrama do banco de dados.](https://drive.google.com/file/d/1bfNfXLuHHE43d_TW_YnZnUsCCwpFQbTK/view?usp=sharing)