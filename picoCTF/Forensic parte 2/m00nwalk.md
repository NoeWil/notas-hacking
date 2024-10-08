## Objetivo
Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

Hint 
- How did pictures from the moon landing get sent back to Earth?
- What is the CMU mascot?, that might help select a RX option
## Solucion
Descargamos he instalado un sstv decode de github, despues lo utilizamos en el archivo de audio
```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/moonwalk]
└─$ sstv -d message.wav -o flag.png
[sstv] Searching for calibration header... Found!
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [######################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/moonwalk]
└─$
```

## Notas adicionales
## Referencias
- [SSTV - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/SSTV)
- [GitHub - colaclanth/sstv: SSTV Decoder](https://github.com/colaclanth/sstv)