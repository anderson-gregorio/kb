# Dica - Versionamento de um API

* Adicionar os seguintes pacotes:

    * Microsoft.AspNetCore.Mvc.Versioning
    * Microsoft.AspNetCore.Mvc.Versioning.ApiExplorer

* Em Startup.cs -> ConfigureServices adicionar o seguinte código

    ```csharp
        // Versionamento
        services.AddApiVersioning(options =>
        {
            options.DefaultApiVersion = new ApiVersion(majorVersion: 1, minorVersion: 0);
            options.ReportApiVersions = true;
            options.AssumeDefaultVersionWhenUnspecified = true;
        });

        services.AddVersionedApiExplorer(options =>
        {
            options.GroupNameFormat = "'v'VVV";
            options.SubstituteApiVersionInUrl = true;
        });
    ```

* Nos controllers adicionar as seguintes anotações

    ```csharp
    [ApiController]
    [ApiVersion("1.0")]
    [Route("api/v{version:apiVersion}/empresas")]
    ```