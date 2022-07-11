# debihestr

Decimal, Binary, Hexadecimal, String Package conversions

# convert decimal to binary

def decimalToBinary(n):
    """
    function converts a decimal number to binary using the python in build function bin
    :param n: parameter n which is a decimal
    :return: return the binary digit
    """
    return bin(n).replace('0b', '')

# convert binary to decimal

def binaryToDecimal(n):
    """
    function converts binary to decimal pass 2 params int(binary, base=2)
    :param n: n param which is a binary digit
    :return: returns and integer value

    """
    return int(n, 2)


# convert binary to hexdecimal


def binaryToHexa(n):
    """
    The function converts a binary number to a hexadecimal using python build in hex in-build passing the decimal value
    :param n: pass param n which is a binary digit
    :return: return a hexadecimal number
    """
    # convert binary to int
    num = int(n, 2)
    # convert int to hexadecimal
    hex_num = hex(num)
    return (hex_num)


# convert hexdecimal to binary
def hexaToBinary(n):
    """
    function converts hexdecimal to binary using int(n, base=16) then convert to binary using bin in-build function
    then use zfill(8) with param 8 to add method adds zeros (0) at the beginning of the string, until it reaches the specified length
    :param n: binary digit to be converted
    :return: returns a binary digit
    """

    return bin(int(n, 16)).replace('0b', '')


def stringToBinary(n):
    """
    The function converts a string to binary using  join() + bytearray() + format()
    08b - divide the digital storage value by 8
    bytearray() - method returns a bytearray object which is an array of given bytes

    :param n: the string to be converted to binary
    :return: value should be binary.
    """
    return ''.join(format(i, 'b') for i in bytearray(n, encoding='utf-8'))


def binaryToString(n):
    """
    Function converts binary to String
    slicing the input and converting it
    in decimal and then converting it in string

    :param n: binary digit param
    :return: return string value
    """
    str_data = ' '
    for i in range(0, len(n), 7):
        temp_data = n[i:i + 7]
        decimal_data = binaryToDecimal(temp_data)
        str_data = str_data + chr(decimal_data)
        
    return str_data

