## Objetivo
Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/475/enc_flag).
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ cat enc_flag
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKVVZXcE9VazFXV2toT1dHUllDbUY2UWpSWk1GWlhWa2RHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ base64 -d enc_flag
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVkM0JUVWpOUk1WWkhOWGRYCmF6QjRZMFZXVkdGdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ base64 -d enc_flag | base
base32       base64       basecsp.dll  basename     basenc       basesrv.dll
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ base64 -d enc_flag | base64 -d | base64 -d
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aTwpSR3Q1VG5wWk0xcEVTamxEWnowOUNnPT0K

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ base64 -d enc_flag | base64 -d | base64 -d | base64 -d
Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZO
RGt5TnpZM1pESjlDZz09Cg==

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ base64 -d enc_flag | base64 -d | base64 -d | base64 -d | base64 -d
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfNDkyNzY3ZDJ9Cg==

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ base64 -d enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_492767d2}

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$
```
## Notas adicionales
## Referencias