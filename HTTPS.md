The idea is simple.
1. The client initiates the security connection to get the Server's public certificate. (goes in plain text)
2. The client validates the Servers public certificate, checks the data expiration, cert domain, etc
3. The client generates a temporary key that is encrypted by the Server's public key.
4. The server takes the encrypted key, decrypts it, and starts using that key to encrypt the response.
All that interaction goes via [[TLS]] / SSL protocol.
