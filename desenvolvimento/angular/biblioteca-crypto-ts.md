# Biblioteca - crypto-ts

Typescript library of crypto standards. Ready for AOT and treeshaking in combination with Angular and other modern typescript frameworks.

NPM: https://www.npmjs.com/package/crypto-ts

```javascript
....
import * as CryptoTS from 'crypto-ts';
....

// Encrypt
CryptoTS.AES.encrypt(<dados>, <key>).toString();

// Decrypt
var bytes  = CryptoTS.AES.decrypt(<dados_encrypt>, <key>);
var plaintext = JSON.parse(bytes.toString(CryptoTS.enc.Utf8));

```