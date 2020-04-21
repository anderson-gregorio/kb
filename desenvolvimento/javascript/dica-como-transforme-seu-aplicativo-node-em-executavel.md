# Dica - Como transforme seu aplicativo Node em executável?

Para isso será utilizado o pacote/biblioteca PKG 

```bash
npm install -g pkg
```

O arquivo package.json deve ser ajustado

```json
{
    name": "meuapp",
    "dependencies": {
        ...
    },
    "bin": "index.js",
    "pkg":{
        "assets":[
            "view/\*\*/\*"
        ],
        "target": [
            "node7"
        ]
    }
}
```

Para realizar o empacotamento

```bash
pkg .
```

Link de Referência:

[https://devpleno.com/hands-on-pkg/](https://devpleno.com/hands-on-pkg/)