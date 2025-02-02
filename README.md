# SALIC api Divino [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=102)](https://github.com/ellerbrock/open-source-badge/) [![Open Source Love](https://badges.frapsoft.com/os/gpl/gpl.svg?v=102)](http://www.gnu.org/licenses/gpl.html)


API aberta para o sistema [SALIC](http://centraldevops.com/cidadao/consultar). Tem por objetivo expor os dados de projetos da lei Rouanet.

A documentação da API pode ser acessada [aqui](http://api.centraldevops.com/doc/).

O projeto ainda se encontra em **desenvolvimento**, sujeito ainda a muitas alterações, reformulações e atualizacões.



## Requisitos

A aplicação foi testada em ambientes LINUX com distribuições Debian e Ubuntu.

Os requisitos mínimos de hardware recomendados podem variar muito dependendo do ambiente
onde será implantada e ainda não foram oficializados. O seguinte, contudo, deve oferecer um desempenho
satisfatório:

-	Processador Dual Core 2 GHz
-	2 GB de RAM
-	2 GB livres em disco

## Instalação Automatizada

Execute como root o script **install.sh**

```bash
$ chmod +x install.sh
```

```bash
$ sudo ./install.sh
```

Se tudo ocorrer bem, a aplicação deve estar instalada em **/opt/salic/salic-api/**, pronta para uso, bastando apenas configurar alguns parâmetros

## Instalação Manual

### Dependências básicas

-	`python-dev`
-	`python-pip`
-	`freetds-dev`
-	`libxml2-dev`
- `libxslt1-dev`
- `libz-dev`

### Pacotes python

Basta executar

```bash
$ sudo pip install -r requirements.txt
```

Caso apareça a seguinte mensagem..
 ```bashs
 Could not import setuptools which is required to install from a source distribution.
 Please install setuptools.
 ```
 ..basta reinstalar o setuptools
 ```bashs
 sudo pip install -U setuptools
 ```
 
 

## Configuração

Edite o arquivo **salic-api/app/example_config.py** de acordo com seu ambiente.
Edite o arquivo **salic-api/app/general_config.py** apontando o arquivo de configuração a ser usado.

## Execução

Por padrão a aplicação executa com o web server **Tornado**

O executável é o arquivo  **run.py**

```bash
$ python run.py
```

Caso tenha optado pela instalação automatizada, basta executar

```bash
$ /etc/init.d/salic-api start
```


Ao executar

```bash
$ /etc/init.d/salic-api
```

Você pode conferir os demais comandos disponíveis

## Teste

Para verificar se a API está de fato executando corretamente, faça uma requisição para a URL

[http://localhost:8000/test](http://localhost:8000/test)

Se tudo estiver correto, você deve obter uma resposta com conteúdo:

```json
{"content": "API is up and running :D"}
```

## License

Licensed under the [GPL License](http://www.gnu.org/licenses/gpl.html).
