# Dica - Documentando uma API

## Utilizando o Swagger

* Adicionar os seguintes packages

    * Swashbuckle.AspNetCore
    * Swashbuckle.AspNetCore.Annotations

* Em **Startup.cs -> ConfigureServices** incluir o seguinte código:

    ```csharp
            // Swagger
            services.AddSwaggerGen(c =>
            {
                c.SwaggerDoc("v1", new OpenApiInfo
                {
                    Version = "v1",
                    Title = "#TITLE",
                    Description = "#DESCRIPTION",
                    TermsOfService = new Uri("URL"),
                    Contact = new OpenApiContact
                    {
                        Name = "#NAME",
                        Email = "#EMAIL",
                    }
                });

                var xmlFile = $"{Assembly.GetExecutingAssembly().GetName().Name}.xml";
                var xmlPath = Path.Combine(AppContext.BaseDirectory, xmlFile);
                c.IncludeXmlComments(xmlPath);

                c.EnableAnnotations();
            });
    ```

* Em **Startup.cs -> Configure** incluir o seguinte código:

    ```csharp
            app.UseSwagger();

            app.UseSwaggerUI(c =>
            {
                c.SwaggerEndpoint("/swagger/v1/swagger.json", "MQ NFSe Api");
            });
    ```

* Em **<NOME_PROJETO>.csproj** incluir o seguinte código:

    ```xml
    <PropertyGroup>
        ...
        <GenerateDocumentationFile>true</GenerateDocumentationFile>
        <NoWarn>$(NoWarn);1591</NoWarn>
    </PropertyGroup>
    ```

## Documentando uma Model

```csharp
    public class Empresa
    {
        [JsonIgnore]
        public int Id { get; set; }

        [Required]
        [SwaggerSchema("CPF ou CNPJ da Empresa")]
        public string CpfCnpj { get; set; }
        ...
    }
```

Onde:

* **JsonIgnore** ignora a propriedade na geração da documentação

* **SwaggerSchema** cria uma descrição conforme o texto informado

## Documentando um Controller

```csharp
        /// <summary>
        /// Teste do comentário
        /// </summary>
        /// <remarks>
        /// Sample request:
        ///
        ///     POST /Todo
        ///     {
        ///        "id": 1,
        ///        "name": "Item1",
        ///        "isComplete": true
        ///     }
        ///
        /// </remarks>
        /// <returns>A newly created TodoItem</returns>
        /// <response code="201">Returns the newly created item</response>
        /// <response code="400">If the item is null</response>  
        [HttpGet]
        [ProducesResponseType(StatusCodes.Status201Created)]
        [ProducesResponseType(StatusCodes.Status400BadRequest)]
        public IEnumerable<WeatherForecast> Get()
        {
            ...
        }
```