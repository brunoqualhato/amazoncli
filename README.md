# Instalação das bibliotecas


**Serverless**<br/>
```sh
$ npm install -g serverless #instala a dependencia
```

**Verifica a versão**<br/>
```sh
$ sls --version # verifica a versão 
```

**AWS CLI**<br/>

Oficial doc: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

```sh
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

# Configurar Perfil no Ambiente

**Criar um profile com sls**<br/>


```sh
sls config credentials \
  --provider aws \
  --key <KEY> \
  --secret <SECRET-KEY>
```
**Ou com AWS CLI**

```sh
$ aws configure
AWS Access Key ID [None]: <AWS-AKID>
AWS Secret Access Key [None]: <AWS-SAK>
Default region name [None]: <regiao>
Default output format [None]: json
```


**Arquivo profile**<br/>

Oficial doc: https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html
```
[perfil1]
aws_access_key_id=<KEY>
aws_secret_access_key=<SECRET-KEY>

[perfil2]
aws_access_key_id=<KEY>
aws_secret_access_key=<SECRET-KEY>
```

# Instruções Lambda

**Cria o projeto em python**<br/>
```sh
$ sls create --template aws-python3 #cria o projeto em python
```

**Testa o código**<br/>
```sh
sls invoke local -f <funcao_principal>
```

**Envia o código para o lambda**<br/>
```sh
$ sls deploy #envia para amazon
```

# Instruções para o CloudFront

**Envia o Código para o Bucket**
```sh
$ aws s3 sync <diretorio/Do/Projeto> s3://<nome-bucket> --profile <perfil>
```

**Apaga cache e propaga novamente**

```sh
$ aws cloudfront create-invalidation --profile <perfil>  --distribution-id=<id-distribuicao>  --paths /pasta/para/invalidar
```
