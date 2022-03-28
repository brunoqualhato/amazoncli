# Instruções Lambda

**Instala dependências**<br/>
```sh
$ npm install -g serverless #instala a dependencia
```

**Verifica a versão**<br/>
```sh
$ sls --version # verifica a versão 
```

**Cria o prijeto em python**<br/>
```sh
$ sls create --template aws-python3 #cria o projeto em pythob
```

**Envia o código para o lambda**<br/>
```sh
$ sls deploy #envia para amazon
```

# Instruções para o CloudFront

**Envia o Código para o Bucket**
```sh
$ aws s3 sync <diretorio/Do/Projeto> s3://<url-bucket> --profile <perfil>
```

**Apaga cache e propaga novamente**

```sh
$ aws cloudfront create-invalidation --profile <perfil>  --distribution-id=<id-distribuicao>  --paths /pasta/para/invalidar
```
