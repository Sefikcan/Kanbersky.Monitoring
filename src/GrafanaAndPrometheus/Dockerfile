#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["src/GrafanaAndPrometheus/GrafanaAndPrometheus.csproj", "src/GrafanaAndPrometheus/"]
RUN dotnet restore "src/GrafanaAndPrometheus/GrafanaAndPrometheus.csproj"
COPY . .
WORKDIR "/src/src/GrafanaAndPrometheus"
RUN dotnet build "GrafanaAndPrometheus.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "GrafanaAndPrometheus.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "GrafanaAndPrometheus.dll"]