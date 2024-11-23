## Objetivo
[keygenme-trial.py](https://mercury.picoctf.net/static/5a4198cd84f87c8a597cbd903d92fbf4/keygenme-trial.py)

## Solucion

```python
import hashlib

# Enter main loop
ui_flow()

if jump_into_full:
    exec(full_version_code)

key_part_dynamic1_trial = ""

indices = [4,5,3,6,2,7,1,8]

for i in indices:
  key_part_dynamic1_trial += hashlib.sha256(bUsername_trial).hexdigest()[i]

key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"

key_part_static2_trial = "}"
key_full_template_trial = key_part_static1_trial + key_part_dynamic1_trial + key_part_static2_trial

print(key_full_template_trial)
```

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/keygenme-py]
└─$ python3 keygenme-trial.py

===============================================
Welcome to the Arcane Calculator, ANDERSON!

This is the trial version of Arcane Calculator.
The full version may be purchased in person near
the galactic center of the Milky Way galaxy.
Available while supplies last!
=====================================================


___Arcane Calculator___

Menu:
(a) Estimate Astral Projection Mana Burn
(b) [LOCKED] Estimate Astral Slingshot Approach Vector
(c) Enter License Key
(d) Exit Arcane Calculator
What would you like to do, ANDERSON (a/b/c/d)? d
Bye!
picoCTF{1n_7h3_|<3y_of_01582419}
```
## Notas adicionales
## Referencias