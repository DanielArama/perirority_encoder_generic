##### perirority_encoder_generic
generic priority encoder module. It takes an input vector x of size n-1:0, an enable signal enb, and provides two outputs: v and y. v is a single-bit output 
indicating whether any of the enabled inputs in x are high, and y is a binary-encoded output representing the highest enabled input.

Here's a breakdown of the code:

The assign statement assigns the value of |x & enb to v. This expression performs a bitwise AND between the input vector x and the enable signal enb. 
The result is then bitwise ORed, |, to produce a single bit v indicating whether any of the enabled inputs are high.

The always block is triggered whenever there is a change in either x or enb. It initializes y to 0 at the beginning of the block.

If enb is high, the for loop iterates over each bit of x from the least significant bit to the most significant bit (i ranges from 0 to n-1). If a bit x[i] is high, 
the corresponding index i is assigned to y. This means y will hold the index of the highest enabled input that is high.

If enb is low, meaning none of the inputs are enabled, y is set to 0 to indicate no valid input is present.
