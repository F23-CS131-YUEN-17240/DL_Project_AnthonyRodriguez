# DL_Project_AnthonyRodriguez
Anthony Rodriguez presentation on Zeckendorf theorem

CODE IN ARM ASSEMBLY
		
		;		Rodriguez, Anthony
		;		Assignment - Zeckendorf Number
		MOV		R0,#17  ; this will be the value of k
		BL		zeck ;start zeck function
DONE		END
		
zeck
		MOV		R4,R0
		
fib
		MOV		R1, #0 ;numbers to begin fib sequence fn-2
		MOV		R2, #1 ;fn-1
		MOV		R3, #1 ;fn
		BL		loop ;start looping to find highest fibonacci number in value 'k'
loop
		CMP		R4,#0 ;compare to stop when number is 0
		BEQ		fin
		MOV		R1,R2 ;moves value of r2 into r1
		MOV		R2,R3 ; moves value of r3 into r2
		ADD		R3,R1,R2 ; adds both values
		CMP		R3, R4
		BLE		loop ;if less then 'k' repeat loop again
		ADD		R5,R5,#1 ;add to zeck value
		MOV		R0,R2 ;moves highest fib # in r0
		SUB		R4,R4,R2 ;subtracts to find new value
		BL		fib ;repeats with new value
		
fin
		MOV		R0,R5 ;store zeck number in r0
		B		DONE ;branch back "End"
		
