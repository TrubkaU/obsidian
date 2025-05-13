A **Man-in-the-Middle (MITM)** attack occurs when an attacker intercepts and potentially alters the communication between a client (e.g., an Android app) and a server. This can happen over insecure channels like HTTP or poorly configured HTTPS connections. The attacker essentially becomes the middleman between the two parties and can intercept sensitive data such as login credentials, credit card information, or any other private communication.

In a typical MITM attack:
- The attacker intercepts the traffic between the **client** (your Android app) and the **server**.
- If the app uses **HTTP** (unencrypted), the attacker can easily **read** and **modify** the traffic.
- If the app uses **HTTPS**, but there's an issue with the SSL/TLS setup (like improper certificate validation or use of weak cipher suites), the attacker can **manipulate the connection** and decrypt the data.
- In some cases, attackers can inject malicious content, such as **malware** or **phishing redirects**, into the communication stream.

How to protect [[00 Android]] 
1. Always use [[HTTPS]]
2. Always use the latest [[TLS]] 
3. Use a strong [[AES]] algorithm to encrypt not a weak cipher, like XOR
4. Use the Certificate Pinning technique
```kotlin
val certificatePinner = CertificatePinner.Builder()
    .add("example.com", "sha256/AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=")
    .build()

val client = OkHttpClient.Builder()
    .certificatePinner(certificatePinner)
    .build()
```
5. Strict Certificate Validation
6.  
