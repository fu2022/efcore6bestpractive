# Ef core 6 : Best Practices

#   Ch2 - Structuring Project for Cleanliness and Testability

#   ef bundle deploy need **********************

## create migration bundle
dotnet ef migrations bundle 
  -p .\kp.infr\ 
  -s .\kp.api\
  --self-contained
  --target-runtime linux=x64
  

note : run dotnet ef bundle in docker after run dotnet build and test in dockerfile

### Install EF tool

    RUN dotnet tool install --global dotnet-ef
    ENV PATH="${PATH}:/root/.dotnet/tools"
    ENV GLOBOTICKET_ADMIN_CONNECTION_STRING="Server=tcp:mssql;Database=GloboTicket;User=sa;Password=notused;TrustServerCertificate=True;"
    RUN dotnet ef migrations bundle -p ./GloboTicket.Infrastructure -s ./GloboTicket.API --configuration Release --no-build --self-contained
    
**need practive the flow of deployment**

