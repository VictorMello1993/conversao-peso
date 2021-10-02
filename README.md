### Executando a aplicação:

```docker build -t <nome_imagem> .```

 A porta de comunicação da imagem do .NET é a 80. Dessa forma, é preciso expor a porta da aplicação (vide arquivo launchSettings.json acessando pela chave ```applicationUrl:``` ) para a porta 80.

Ex:
```docker run -d -p 5000:80 <nome_imagem>```

## Kubernetes

A porta a ser exposta para rodar na aplicação é a 80 mesmo que o padrão seja a 5000. Isso porque a imagem do .NET Core muda o valor da porta na variável de ambiente ```ASPNETCORE_URLS ``` para ```http://+:80/```

Para confirmar isso, execute
```docker run --rm mcr.microsoft.com/dotnet/aspnet printenv ASPNETCORE_URLS```

Ou para ver todas as variáveis de ambiente da imagem do .NET 
```docker run --rm mcr.microsoft.com/dotnet/aspnet printenv```

## Referências:
https://docs.microsoft.com/pt-br/aspnet/core/host-and-deploy/docker/building-net-docker-images?view=aspnetcore-5.0

