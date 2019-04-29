[![goodtables.io](https://goodtables.io/badge/github/AntoineAugusti/gharchive-gouv-fr.svg)](https://goodtables.io/github/AntoineAugusti/gharchive-gouv-fr)

# GH Archive Gov BR
Download data from [GH Archive](https://www.gharchive.org) and extract push events done with `@*.gov.br` email addresses.

## Requirements
This works with a single Bash script. Dependencies are :
- `gunzip`
- `jq`
- `wget`

This should be straightforward to run on a UNIX machine.

## Usage
You can download the GitHub archive for a given month, extract log files and process them with the following command:

```sh
./run.sh 2017-01
```

Be aware that this will take a good amount of bandwidth, storage and processing power. For example, the compressed log files for 2018-01 weight 95 GB.

## Schema details

Modelos de Dados originalmente feito por:
- Auteur : Antoine Augusti <antoine.augusti@data.gouv.fr>
- Schéma créé le : 2019-04-02
- Clé primaire : `id`

Adaptado por:
- Autor : Luis Felipe Coimbra Costa <luisfcosta@cos.ufrj.br>
- Diagrama criado em : 29-04-2019
- Chave Primária: `id`


### Modelo de Dados

|Nome|Tipo|Descricao|Exemplo|Propriedades|
|-|-|-|-|-|
|id|numero inteiro|Identificador único do evento|2489811994||
|repository_name|cadeia de caracteres|O nome do diretório GitHub | openchordcharts / openchordcharts-sample-data||
|ref|cadeia de caracteres| branch em questão | refs / heads / master||
|author_email|cadeia de caracteres|O endereço de e-mail do autor do commit|b445c0e632270b31bc0c900a39de4fc4159fb695@data.gouv.fr|Motivo : `.*@.*\.gov\.br$`|
|author_domain|cadeia de caracteres|O nome de domínio do endereço de e-mail do autor do commit|data.gouv.fr|Motivo : `.*\.gov\.br$`|
|author_name|cadeia de caracteres|O nome do autor do commit|Jean Dupont||
|message|cadeia de caracteres|A mensagem de commit|WIP||
|sha|cadeia de caracteres|O commit do SHA1|288e534ef881c3973bc413a60370dfa59caf7fbe||
|organisation_name|cadeia de caracteres|O nome da organização|betagouv||
|created_at|data e hora|A data de criação do commit, en ISO8601|2015-01-01T20:40:32Z||

## License
MIT. See the license file.
