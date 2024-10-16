## Objetivo
Bank security personnel have intercepted a photograph taken with a thermal camera of a suspicious employee loitering near a safe. An investigation is underway to determine if this individual was able to obtain the code to the safe. Investigation of the safe's keypad reveals that it only accepts four-digit codes.
https://ctfd.anuies.mx/files/b21b1742c780e5cb9d0fc5886e68192d/Thermal_camera.png?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6MTF9.Zw8lXA.HB56yHP1Q0rOkukpIMpbn_9-9H8

## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/termal]
└─$ wget https://ctfd.anuies.mx/files/b21b1742c780e5cb9d0fc5886e68192d/Thermal_camera.png?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6MTF9.Zw8lXA.HB56yHP1Q0rOkukpIMpbn_9-9H8
--2024-10-15 20:32:41--  https://ctfd.anuies.mx/files/b21b1742c780e5cb9d0fc5886e68192d/Thermal_camera.png?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6MTF9.Zw8lXA.HB56yHP1Q0rOkukpIMpbn_9-9H8
Resolving ctfd.anuies.mx (ctfd.anuies.mx)... 189.254.1.194
Connecting to ctfd.anuies.mx (ctfd.anuies.mx)|189.254.1.194|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 380358 (371K) [image/png]
Saving to: ‘Thermal_camera.png?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6MTF9.Zw8lXA.HB56yHP1Q0rOkukpIMpbn_9-9H8’

Thermal_camera.png?token=eyJ1c2VyX2lkIjoz 100%[=====================================================================================>] 371.44K   538KB/s    in 0.7s

2024-10-15 20:32:42 (538 KB/s) - ‘Thermal_camera.png?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6MTF9.Zw8lXA.HB56yHP1Q0rOkukpIMpbn_9-9H8’ saved [380358/380358]


┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/termal]
└─$ eog Thermal_camera.png\?token\=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6MTF9.Zw8lXA.HB56yHP1Q0rOkukpIMpbn_9-9H8
```
Probar todas las combinaciones  de 3,5,7,0
## Notas adicionales
## Referencias