## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL/TLS encryption.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**
## Datos de acceso al nivel
* Username = bandit15
* password = 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
## Solucion
````bash

bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 247CE7A76893544B3179958B243393704F52E283261618421F7530D4DD059124
    Session-ID-ctx:
    Resumption PSK: 27AB17272BAF2A5472C950326228E774F50185B401B20422910ADB0F7F5538DC7466E548E7F406A03A79BEAA0BB0E899
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 43 87 d0 c4 a5 49 95 26-c8 3e eb 08 d7 47 78 ca   C....I.&.>...Gx.
    0010 - 8d 20 84 91 b8 16 3b 52-2f 32 38 78 ac ef 22 6b   . ....;R/28x.."k
    0020 - f1 8f ea 4d 4d 03 ad 9f-0d c5 a4 33 6e cb 13 fd   ...MM......3n...
    0030 - b0 9b bf 3d e3 97 97 a7-b3 92 6f 92 b8 4d bf 68   ...=......o..M.h
    0040 - 82 ed 42 04 90 0d 30 8a-69 d3 3d 7b 6a a6 64 68   ..B...0.i.={j.dh
    0050 - dc a9 6e 82 fd d9 73 65-0f 45 80 e1 13 14 a0 86   ..n...se.E......
    0060 - e9 c1 b1 e6 cd ef 5b f3-a4 48 42 3f 44 34 2f 2b   ......[..HB?D4/+
    0070 - 7b 0a bf f5 74 8a ef 13-55 5d 0b c3 72 8e c8 7b   {...t...U]..r..{
    0080 - 4a 22 2f c6 c2 34 19 15-4a 65 3b 29 30 83 5d 04   J"/..4..Je;)0.].
    0090 - 10 a1 0e 2e 54 09 95 46-38 6e 23 59 59 f0 79 38   ....T..F8n#YY.y8
    00a0 - 15 83 53 3c d2 26 1d ca-25 4c 37 20 56 e5 39 42   ..S<.&..%L7 V.9B
    00b0 - c7 d7 0d b4 47 54 cc 7a-40 82 21 a1 ba d2 75 26   ....GT.z@.!...u&
    00c0 - 75 54 2d 69 be 50 42 db-72 e7 97 76 68 d3 ae 5b   uT-i.PB.r..vh..[
    00d0 - 87 0c a0 3a e6 62 99 56-89 89 7f 63 44 91 4e 89   ...:.b.V...cD.N.

    Start Time: 1724986115
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 0F42A2CD50DD22C83C520460E225FC6E79826E60C851783C77B8CB010B03523F
    Session-ID-ctx:
    Resumption PSK: 8813D5C7DF12ED67380497E1460F6AF5BA2E93AE20A4E27129AA56C94E08FC39D49E1C9C95B00A9B1741FC6D5547DE0A
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 43 87 d0 c4 a5 49 95 26-c8 3e eb 08 d7 47 78 ca   C....I.&.>...Gx.
    0010 - a6 f8 5b 9a 6d 6e fc 68-89 61 cf e9 e9 81 9d 8c   ..[.mn.h.a......
    0020 - 7c 31 d9 6c ad 3c 8e 72-4f 08 98 3e 5b 9a 61 69   |1.l.<.rO..>[.ai
    0030 - b8 b3 33 11 07 5e 52 50-d2 95 77 38 9f 04 e3 76   ..3..^RP..w8...v
    0040 - 58 2a 55 e1 9e ff c4 31-f3 f6 4c 9f 37 cd d9 2a   X*U....1..L.7..*
    0050 - b1 ef 77 8a 55 c2 ca dd-6c 2c b6 e5 38 79 5f 79   ..w.U...l,..8y_y
    0060 - c4 2d 64 96 6b e8 60 c0-e7 0c fd d4 af 54 35 19   .-d.k.`......T5.
    0070 - 38 ac a1 93 06 c0 81 2f-0d 47 aa fa 54 53 1e 82   8....../.G..TS..
    0080 - 6b 8f 55 f0 b4 a6 46 43-5c 98 65 3c 90 28 49 5c   k.U...FC\.e<.(I\
    0090 - 14 f6 bf e0 57 fb f0 9c-d1 20 3a 79 fc c3 07 79   ....W.... :y...y
    00a0 - 42 05 ed a5 4e f1 83 c4-1b 33 6c f1 3c d3 d6 38   B...N....3l.<..8
    00b0 - 57 e5 42 49 ff d9 1c a1-88 76 c5 be 6d 33 bc 87   W.BI.....v..m3..
    00c0 - 4c e7 c3 68 0c 3b c8 26-a8 bc 24 dd 80 db 4d 71   L..h.;.&..$...Mq
    00d0 - 03 18 4d 9a be 19 0b 37-24 a7 70 14 7b a2 0a 10   ..M....7$.p.{...

    Start Time: 1724986115
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

closed
````
## Notas adicionales
- El comando intenta establecer una conexión TCP al puerto especificado (30001) en el host (localhost). Luego, intenta negociar un canal de comunicación seguro utilizando el protocolo SSL/TLS.
- `openssl s_client`: Este es el comando que invoca la utilidad `s_client` de OpenSSL. La utilidad `s_client` actúa como un cliente de conexión SSL/TLS para probar y depurar conexiones seguras.
- `-connect localhost:30001`: Esta opción especifica el punto de conexión al que el cliente debe conectarse.
## Referencias
- [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Transport_Layer_Security)
- [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/testing-with-openssl/index.html)