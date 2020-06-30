# Dica - Como realizar deploy hosting com múltiplo domínios

[Ver como iniciar um projeto]()

* Abra o arquivo firebase.json, ele deve apresentar a seguinte estrutura

    ```json
    {
        "hosting": {
            "public": "public",
            "ignore": [
                "firebase.json",
                "**/.*",
                "**/node_modules/**"
            ],
            "rewrites": [
                {
                    "source": "**",
                    "destination": "/index.html"
                }
            ]
        }
    }
    ```
* Deve ser alterardo para a seguinte estrutura

    ```json
    {
        "hosting": [
            {
                "target": "prod",
                "public": "public",
                "ignore": [
                    "firebase.json",
                    "**/.*",
                    "**/node_modules/**"
                ],
                "rewrites": [
                    {
                        "source": "**",
                        "destination": "/index.html"
                    }
                ]
            }
        ]
    }
    ```

    Ou seja, transforma o "hosting" em Array e adicionar a propriedade target

* Além disso deve se aplicar um target ao site

    ```bash
    firebase target:apply hosting <TARGET> <NOME_SITE>
    ```

* Para realizar o deploy deve se usar o comando

    ```bash
    firebase serve --only hosting:<TARGET>
    ```

Link de Referência: [https://fireship.io/lessons/deploy-multiple-sites-to-firebase-hosting/](https://fireship.io/lessons/deploy-multiple-sites-to-firebase-hosting/)