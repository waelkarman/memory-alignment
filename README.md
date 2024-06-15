
Alignment Process

```
    32 = 100000
    31 =  11111 

--

    Allocated Memory with malloc.
    ^                                                $
    |<--------------------->|<----->|<-------------->| 
    |         size         sizeof(void*) alignment-1 |
   ptr*
   4097

--

   4096 is aligned.
   +31 For ensuring to reach the next aligned address.
   4097 + 31 = 4128  ->  0001000000100000
   4100 + 31 = 4131  ->  0001000000100011

    Aligned address to 2^n should have last n-1 bit to zero counting from zero: 
   0001000000100000
              11111  <- AND mask
   0001000000100000  <- aligned addr : 4128
   
   0001000000100011
              11111  <- AND mask
   0001000000100000  <- aligned addr : 4128

    Aligned memory
    ^                                          $
    |<--------->|<-------->|<----------------->| 
    |           |          |       size     
   ptr*   sizeof(void*)  aligned
                          addr
   4097                   4128
```
