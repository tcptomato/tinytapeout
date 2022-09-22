# Pseudo-random number generator using a 16-bit Fibonacci linear-feedback shift register

16 flip flops are connected in a chain, and the output of some is XORed together and fed back into the first flip flop.
The outputs that are XORed together are chosen in such a way as to give the longest possible cycle (2^16-1).
All bits being zero is a special case and is treated separately (all negative outputs of the flip flops are ANDed together to generate a 1 as feedback).
                 
On each clock pulse (pin 1) one new bit is generated.
Setting load_en (pin 3) to HIGH allows the loading of a user defined value through the data_in pin (pin2). On each clock pulse one bit is                  read into the flip flop chain. When load_en (pin 3) is set to LOW the computed feedback bit is fed back into the flip flops.
                 
The outputs of the last 8 flip flops are connected to the output pins. For each clock pulse a random bit is generated and the other 7 are shifted.

https://en.wikipedia.org/wiki/Linear-feedback_shift_register
