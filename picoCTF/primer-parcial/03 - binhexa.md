## Objetivo
How well can you perfom basic binary operations?

Additional details will be available after launching your challenge instance.
## Solucion
```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ nc titan.picoctf.net 49174

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11010101
Binary Number 2: 11010101

Question 1/6:
Operation 1: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 011010101
Correct!

Question 2/6:
Operation 2: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1011000100111001
Correct!

Question 3/6:
Operation 3: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 110101010
Correct!

Question 4/6:
Operation 4: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 110101010
Correct!

Question 5/6:
Operation 5: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11010101
Correct!

Question 6/6:
Operation 6: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 1101010
Correct!

Enter the results of the last operation in hexadecimal: 6a

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}
```

## Notas adicionales
## Referencias
- [Calculadora a nivel de bits - Calculadora de desplazamiento de bits (miniwebtool.com)](https://miniwebtool.com/es/bitwise-calculator/bit-shift/?data_type=2&number=11010101&place=1&operator=Shift+Right)
- [Binary Calculator (rapidtables.com)](https://www.rapidtables.com/calc/math/binary-calculator.html)

