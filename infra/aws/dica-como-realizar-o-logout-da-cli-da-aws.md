# Dica - Como realizar o logout da CLI da AWS?

Suas crendencias são salvas no arquivo chamado config na pasta .aws. 

No Windows está pasta está em c:\Users\<USERNAME>\.aws\config

Opção para realizar o Logout:

* Excluir os dados nesta pasta;

* Executar o comando a baixo e inserir dados nulos

```bash
aws configure
```

Link de referência: [https://forums.aws.amazon.com/thread.jspa?threadID=148833](https://forums.aws.amazon.com/thread.jspa?threadID=148833)