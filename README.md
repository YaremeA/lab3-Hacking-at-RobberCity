# lab3-Hacking-at-RobberCity

import sys
import math

def xor(a, b):
    result = ""
    for i in range(len(a)):
        # XOR two hex characters
        xor_result = int(a[i], 16) ^ int(b[i], 16)
        result += format(xor_result, 'x')
    return result

# Read three hex inputs
hex_input1 = input().strip()
hex_input2 = input().strip()
hex_input3 = input().strip()

# XOR the inputs
xor_result = xor(xor(hex_input1, hex_input2), hex_input3)

# Convert hex to ASCII
ascii_result = ''.join(
    chr(int(xor_result[i:i+2], 16)) for i in range(0, len(xor_result), 2)
)

# Print final ASCII result
print(ascii_result)


