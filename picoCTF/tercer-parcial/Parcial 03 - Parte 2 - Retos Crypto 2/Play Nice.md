## Objetivo
Not all ancient ciphers were so bad... The flag is not in standard format. `nc mercury.picoctf.net 33686` [playfair.py](https://mercury.picoctf.net/static/aec5fd7b1ec96307c4eda752a3353f68/playfair.py)

## Solucion

```python
SQUARE_SIZE = 6
def generate_square(alphabet):
        assert len(alphabet) == pow(SQUARE_SIZE, 2) #can be ignored here
        matrix = []
        for i, letter in enumerate(alphabet):
                if i % SQUARE_SIZE == 0: #i%6==0
                        row = []
                row.append(letter)
                if i % SQUARE_SIZE == (SQUARE_SIZE - 1):
                        matrix.append(row)
        return matrix

def get_index(letter, matrix):
        for row in range(SQUARE_SIZE):
                for col in range(SQUARE_SIZE):
                        if matrix[row][col] == letter:
                                return (row, col)
        print("letter not found in matrix.")
        exit()

def decrypt_pair(pair, matrix):
        #print("pair=",pair)
        p1 = get_index(pair[0], matrix) #(row,col)
        p2 = get_index(pair[1], matrix) #(row,col)

        if p1[0] == p2[0]: #same row
                return matrix[p1[0]][(p1[1] - 1)  % SQUARE_SIZE] + matrix[p2[0]][(p2[1] - 1)  % SQUARE_SIZE]
        elif p1[1] == p2[1]: #same col
                return matrix[(p1[0] - 1)  % SQUARE_SIZE][p1[1]] + matrix[(p2[0] - 1)  % SQUARE_SIZE][p2[1]]
        else: #neither
                return matrix[p1[0]][p2[1]] + matrix[p2[0]][p1[1]]

def decrypt_string(s, matrix):
        result = ""
        for i in range(0, len(s), 2):
                print("now i=",i)
                result += decrypt_pair(s[i:i + 2], matrix)
        return result

alphabet = "v60ufmk7edg4z13h2oyqa9ib58ntwxlrscjp"
m = generate_square(alphabet) #key table
enc_msg="4celvfdkoq5a0dx7pr40ifzctd8488"
msg=decrypt_string(enc_msg,m)
print(msg)
```

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/crypto2/playnice]
└─$ python3 solve.py
now i= 0
now i= 2
now i= 4
now i= 6
now i= 8
now i= 10
now i= 12
now i= 14
now i= 16
now i= 18
now i= 20
now i= 22
now i= 24
now i= 26
now i= 28
dpksmue41bnyue84jlem2jhl9ux755

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/crypto2/playnice]
└─$ nc mercury.picoctf.net 33686
Here is the alphabet: v60ufmk7edg4z13h2oyqa9ib58ntwxlrscjp
Here is the encrypted message: 4celvfdkoq5a0dx7pr40ifzctd8488
What is the plaintext message? dpksmue41bnyue84jlem2jhl9ux755
Congratulations! Here's the flag: 3a64de31e7b5acb6c87ae45050e187ee
```
## Notas adicionales
## Referencias