FROM mcr.microsoft.com/dotnet/sdk:6.0-jammy AS build
WORKDIR /work
COPY . /work
RUN dotnet build -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:6.0-jammy
EXPOSE 80
WORKDIR /app
COPY --from=build /work/out /app/
ENTRYPOINT ["dotnet", "WebApplication_DIT_Docker.dll"]
