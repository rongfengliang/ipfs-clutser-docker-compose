# ipfs cluster docker-compose running demo

## how to running

```code
docker-compose up -d
```

## add files

* mkdir some static web pages in export0 directory

```code
mkdir -p compose/export0/users
cd compose/export0/users
touch index.html
touch index.css

content like below
index.html:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>user info page</title>
    <link rel="stylesheet" href="index.css">
</head>
<body>
    userinfo from ipfs0
</body>
</html>

index.css:

body  {
    font-size: 80px;
    text-align: center;
}

```

* add files to ipfs

inside any contain of ipfs

```code
docker-compose exec ipfs0 sh

ipfs add -r /export/users

some result:

added QmQPZwCUtjjTnWiMuyS7un6T2WdHtxWfa5YyFqwwSp9UwF users/index.css
added QmSj9817rjvUYLCWXSxgMT89Sfr8jdYWJevrPDU2rACpvf users/index.html
added QmZEubFCffhFAfPro18PSt78M1mtR32wcC82y13so91zcN users

```

* access website

```code
http://localhost:8080/ipfs/QmZEubFCffhFAfPro18PSt78M1mtR32wcC82y13so91zcN

or:

http://localhost:8180/ipfs/QmZEubFCffhFAfPro18PSt78M1mtR32wcC82y13so91zcN

```
