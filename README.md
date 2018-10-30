# 16bitALU
Building a 16 bit Arithmetic Logic Unit using a Mojo FPGA and Lucid


General Outline of ALU:
  1. Adder/Subtractor Unit
  2. Compare Unit
  3. Boolean Unit
  4. Shifter Unit
  
  
  Input of ALU:  16 bit binary number a
                 16 bit binary number b
                 6 bit binary number aufn[6:0]
                 
  Output of ALU: 16 bit binary number ALU
                 1 bit boolean z
                 1 bit boolean v
                 1 bit boolean n
               
  Adder/Subtractor Unit:
  Either adds a to b or subtracts a from b depending on alufn[0]
  
      Input: a, b, alufn[0]
      Output: sum, z, v, n
      
      sum is a 16 bit binary number
      *sum might overflow
      
      if (alufn[0] == 0):
        sum = a+b
      if (alufn[0] == 1):
        sum = a-b
        
      z is true if all bits of sum are 0
      v is true if there is an overflow during calculation
      n is true if sum is a negative number
  
  Compare Unit:
  Checks if a is equal to, less than, less than or equal to b depending on alufn[2:1]
  
      Input: a, b, alufn[2:1]
      Output: cmp
      
      cmp is a 16 bit binary number
      
      cmp[15:1] = 0
      if (output of comparison is true):
         cmp[0] = 1
      if (output of comparison is false):
         cmp[0] = 0
         
  Boolean Unit:
  Outputs boolean operations such as AND, OR, XOR, "A", on a and b
  
    Input: a, b, alufn[3:0]
    Output: bool
    
    bool is a 16 bit binary number
    
    bool applies the logic based on alufn[3:0]
    
    Operation   alufn[3:0]
      AND         1000
      OR          1110
      XOR         0110
      “A”         1010
      
   Shifter Unit:
   Outputs a after it has been shifted by b bits. The type of shift depends on alufn[1:0]
   
      Input: a, b, alufn[1:0]
      Outut: shift
      
      shift is a 16 bit binary number
      
      Operation                               ALUFN[1:0]
      SHL (shift left)                            00
      SHR (shift right)                           01
      SRA (shift right with sign extension)       11
