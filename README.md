# CPU ReadMe

# Run Time
For my run time, I estimated around 84ns, as I have around 84 gates total in my circuit. This ends up to be around 12 MHz. I may have miscounted my gates as there are a lot of them, but I believe this is in the ballpark based off of the gates I counted in the subcircuits.

# What works and what does not
The majority of it *does* work. The data unit functions, the control unit is as the lab requires. However, I believe I went wrong when it comes to handling the flags and the jumps in the jump unit. I am also not confident with the instruction decoder and I am not sure if it was properly implemented. In my opinion, those two are the problems stopping my CPU from working correctly. However, I do believe that the majority of it is right and with some more time for adjustment and fine tuning it would be functioning properly. As a summary, the ALU works, the data unit works, the control unit works, and I believe the ROM's work as well. 

#ROM-IV Code
MOV R0, 0      ; Initialize R0 to 0 (accumulator)
MOV R1, 5      ; Initialize R1 to 5 (start of countdown)

loop:
CMP R1, 0      ; Check if R1 == 0
JE done        ; If yes, jump to done
ADD R0, R1     ; Add R1 to R0
ADD R1, -1     ; Decrement R1
JMP loop       ; Repeat loop

done:
NOP            ; No operation (halt)

#Explanation for ROM-IV
This program adds the numbers 5-1 into R0. It then uses a simple loop with a counter (R1), that is decremented with each pass. When R1=0, the program ends by using the jump if equal instruction and ends using NOP.
