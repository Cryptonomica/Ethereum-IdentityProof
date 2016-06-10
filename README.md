# Ethereum Identity Proof

Smart contract for Ethereum's account owner verification using Cryptonomica.net

Usage:
1. Account owner sends a request for verification, in this request he sends a fingerprint of his OpenPGP key stored on cryptonomica.net
2. This contracts sends back a string to sign
3. Accont owener signs this strign with his OpenPGP key and sends back to smartcontract.
4. Information about verification is public visible - who needs to chech can download verified public key from cryptonomica.net and check if owner of stated Ehereum acconts is also known owner of verified OpenPGP key on cryptonomica.net

