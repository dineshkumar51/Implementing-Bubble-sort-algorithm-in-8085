;Bubble sort

;Elements to be sorted are stored from 2200h to 2209h
         
           MVI B,09h        ;1.initializing loop1
START: LXI H,2200h.    ;2.Loading the HL pair with base address (2200h)
           MVI C,09h        ;3.initializing loop2
BACK:  MOV A,M.         ;4.Moving the content of adddress stored in HL pair to A-register 
           INX H               ;5.Moving to next address(incrementing HL pair)
           CMP M.            ;6.compare the content of address in HL pair with A-register
          JZ SKIP             ;7.jump to skip when the two numbers are equal
          JC SKIP             ;8.jump to skip when value in (A)<content of (M)
          MOV D,M           ;9.  
          MOV M,A.          ;10.
          DCX H               ;11.
          MOV M,D           ;12.
          INX H                ;13. code for swaping the two numbers using D register 
SKIP:  DCR C               ;14.decrementing the control variable of loop1
        JNZ BACK           ;15.jump to BACK if the condition is satisfied 
        DCR B                ;16.decrementing the control variable of loop2
       JNZ START          ;17.jump to START if the condition is satisfied






;sum of even numbers

;After sorting the elements this code  finds the sum of even numbers and stores it in location     220Bh (if the lsb of a number is 1 then its odd if the lsb is 0 then its even)  

       MVI C,0Ah         ;1.initializing loop
       MVI B,00h         ;2.initialing B to 0 as we are to store the sum during every iteration in B
       LXI H,2200h      ;3.initialing HL pair with starting address of the array of elements 
BACK1: MOV A,M       ;4.moving the content of address in HL pair to A
      ANI 01h             ;5.ANDing the content A register with (00000001) so that we can find the LSB
      JNZ SKIP1        ;6.jump to skip1 if the condition is satisfied
        MOV A,B.       ;6.Coping the content of B to A 
        ADD M           ;7.ADD the content of A with content at the address stored in HL pair
        MOV B,A        ;8.moving the result back into B-register
SKIP1: INX H          ;9.incrementing the content of HL pair
        DCR C           ;10.decrementing the control variable of the loop
        JNZ BACK1    ;11.Jump to BACK1 if the condition is satisfied
        STA 220Bh     ;12.finally moving the result(sum) to the memory location 220Bh

;sum of ODD numbers
; Same as sum of even numbers only line 6 and line 12  is changed
       
       MVI C,0Ah
       MVI B,00h
       LXI H,2200h
BACK2: MOV A,M
       ANI 01h
       JZ SKIP2
       MOV A,B
       ADD M
       MOV B,A
SKIP2: INX H
       DCR C
       JNZ BACK2
       MOV A,B
       STA 220Dh

