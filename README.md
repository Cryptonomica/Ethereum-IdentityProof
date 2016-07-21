# Ethereum Identity Proof

Smart contract for Ethereum's account owner verification using Cryptonomica.net notary verified OpenPGP public key.

### Usage:

1.Account owner sends a request for verification, in this request he sends a fingerprint of his OpenPGP key stored on cryptonomica.net

2.This contracts sends back a string to sign.

3.Account owner signs this string with his OpenPGP key and sends back to smart-contract.

4. Information about verification is public visible - who needs to chech can download verified public key from cryptonomica.net and check if owner of stated Ehereum acconts is also known owner of verified OpenPGP key on cryptonomica.net

It's also possible to create a web-inerface using Cryptonomica's API like:

GET https://cryptonomica-server.appspot.com/_ah/api/pgpPublicKeyAPI/v1/getPGPPublicKeyByFingerprint?fingerprint=57A5FEE5A34D563B4B85ADF3CE369FD9E77173E5

(Authorization required)

This smart contract deployed on Ehtereum blockchain at:

0xa60df04F73c2c92542ACc86D178B9fc212F7919b

Interface:

```JSON
[{"constant":true,"inputs":[],"name":"creator","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[{"name":"_signedString","type":"string"}],"name":"uploadSignedString","outputs":[],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"signedString","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"urlToVerifyKey","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"keyFingerprint","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[{"name":"_fingerprint","type":"string"}],"name":"getStringToSignWithKey","outputs":[{"name":"","type":"bytes32"}],"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"stringToSign","outputs":[{"name":"","type":"bytes32"}],"type":"function"},{"inputs":[],"type":"constructor"}]
```

Gist:

[Verificator.sol](https://gist.github.com/ageyev/f00e9b425c00531daee2df1728f72d6a)

Solidity Browser-Based Compiler:

[Verificator.sol](https://ethereum.github.io/browser-solidity/#gist=f00e9b425c00531daee2df1728f72d6a&version=soljson-latest.js&optimize=true)

To test functionality you can check verification for: 
0x3b24D5ce666bF060900989E9Bd4E511b7a201AdA

