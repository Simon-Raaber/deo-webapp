FROM mcr.microsoft.com/dotnet/sdk:9.0-alpine3.23 AS build
WORKDIR /build
COPY . .
RUN dotnet publish

FROM mcr.microsoft.com/dotnet/aspnet:9.0-alpine3.23 AS runtime
WORKDIR /app
COPY --from=build /build/bin/Release/net9.0/publish .
ENTRYPOINT ["/app/Deo.Frontend"]