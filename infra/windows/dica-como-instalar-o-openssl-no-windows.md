# Dica - Como instalar o OpenSSL no Windows?

* Baixar o instalador em [http://slproweb.com/products/Win32OpenSSL.html](http://slproweb.com/products/Win32OpenSSL.html)

* Configurar as variáveis de ambiente:

	OPENSSL_CONF = <CAMINHO_INSTALACAO>\bin\openssl.cfg
	
	Path = <CAMINHO_INSTALACAO> (Cuidado para não sobrescrever os outros caminhos do PATH)
	
* Verificando se a instalação

	```bash
	> openssl
	> version
	```
	
Link de Referência:

[https://tecadmin.net/install-openssl-on-windows/](https://tecadmin.net/install-openssl-on-windows/)