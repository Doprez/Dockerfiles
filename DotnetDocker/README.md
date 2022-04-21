# Base Dotnet Dockerfile

This Dockerfile is a starter for adding any dotnet application.

# Setup

In the below you need to make sure to change "AppName" to the name of your application

```
ENTRYPOINT ["dotnet", "./AppName.dll"]
```

And you should change "EXPOSE" to the port you want to use in this case I use 5000 by default

```
EXPOSE 5000
```

finally add this Dockerfile to you apps directory and run it

# Running

To run just enter the below in your terminal
```
dotnet restore -r linux-musl-x64
dotnet publish -c release -o /app -r linux-musl-x64 --self-contained false --no-restore

docker build -t AppName:latest
```