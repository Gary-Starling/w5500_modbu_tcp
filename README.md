# w5500_modbu_tcp 1
 the project was prepared for a controller with small capabilities.
 for debugging i used f4-directory.
 this is a template for porting
____
# directory structure 2
![alt text](/directory.png)
____	
# implementation 3	

server.c/.h
all functions for work modbu_tcp in uint8_t 
tcp_ip_ser_run(uint8_t sock_number)
//==================================================//
1)mbconfig.h //only tcp
#define MB_ASCII_ENABLED                        (  0 )
#define MB_RTU_ENABLED                          (  0 )
#define MB_TCP_ENABLED                          (  1 )
//==================================================//
2)portevent.c // like a bare demo
//==================================================//
3)in directory port/port.h -> rename portm.h and all #include "port.h" changed to #include "portm.h"
it was did because the project had conflict port.h(freeRTOS) and port.h(freeModbus)
//==================================================//
4)mbtcp.h
/* input regs*/
#define REG_INPUT_START 1
#define REG_INPUT_NREGS 10

/* holding regs*/
#define  REG_HOLDING_START 1
#define  REG_HOLDING_NREGS 10 
____