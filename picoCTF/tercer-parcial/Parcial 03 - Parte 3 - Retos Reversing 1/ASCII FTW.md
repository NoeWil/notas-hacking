## Objetivo
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/508/asciiftw).

Hint
- The combined range of hex-ascii for English alphabets and numerical digits is from 30 to 7A.
- Online hex-ascii converters can be helpful.
## Solucion
```python
from ghidra.program.model.mem import MemoryAccessException

start_addr = currentProgram.getAddressFactory().getAddress("00101184")
end_addr = currentProgram.getAddressFactory().getAddress("001011fc")

byte_list = []


current_addr = start_addr
while current_addr <= end_addr:
	instruction = getInstructionAt(current_addr)
	if instruction is not None:
		
		operand = instruction.getOpObjects(1)[0] # get second operand
		byte_val = operand.getValue() & 0xFF # convert to unsigned byte
		byte_list.append(byte_val)
                
       
        current_addr = current_addr.next()

flag = list(map(chr, byte_list))
print("Flag:", "".join(flag))
```

uso de ghidra
## Notas adicionales
## Referencias