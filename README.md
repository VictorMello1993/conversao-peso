### Executando a aplicação:

```docker build -t <nome_imagem> .```

A porta de comunicação da imagem do .NET é a 80. Dessa forma, é preciso expor a porta da aplicação (vide arquivo launchSettings.json acessando pela chave ```applicationUrl:``` ) para a porta 80.

Ex:
```docker run -d -p 5000:80 <nome_imagem>```

## Referências:
https://docs.microsoft.com/pt-br/aspnet/core/host-and-deploy/docker/building-net-docker-images?view=aspnetcore-5.0
