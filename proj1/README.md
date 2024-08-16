# Project 1 README

Student Name: Weiyang Yu,  Student ID: 919410927

## Part 1 explaination:

## References for Part 1

* [Used link](https://www.youtube.com/watch?v=hQXA73nDVB0)

## Generative AI Use

I didn't use any kind of generative AI for this part, instead, I just search up straightfully for the copy and paste
the entire question from part 1 into the Google search bar, and then the first video it pops out (https://www.youtube.com/watch?v=hQXA73nDVB0) 
are basically having the same logic with part 1.

## Interpretation for Part 1

From the given in part 1, E will output 1 and return true when Y = X, meanwhile N will output 0 and return false.
But for the circuit I bulid for this part, N will be output 1 and return true when Y are not equal to X. Which I think
it's also mean that they are not equal for either X>Y or Y>X.

And the input for X is X1 X2 X3, and same as Y. Since they are representing different digits in binary numbers,
then we can compare and check each digit to see if they are the same. For example, we will compare X1 and Y1, and then X2 and Y2 and so on, if they are the same, that will return true and output 1, else will be false and output 0.
Then we can generate a truth table in this situation:

| X | Y | output|
| 0 | 0 |   1   |
| 0 | 1 |   0   |
| 1 | 0 |   0   |
| 1 | 1 |   1   |    Since the logic for this truth table is corresponding to the XNOR table, we will use the XNOR gate to compare all three pair of inputs. And then at the end we will use the And gate to input all three outputs from the XNOR gate to check if they are all true which also mean that they are all output 1 to determine the whether N or E will return 1. Also, I notice that the AND gate will only output one result which is true or false, so I connect the wire to both N and E, and then put an NOT gate in between the AND and N. So, once the circuit is returning true, N will be 0 and E will be 1.

## Part 2 explaination:

# References for Part 2

* [Used link](https://www.youtube.com/watch?v=7v_Vn75iJYI)

## Generative AI Use

No generative AI used for this part

## Interpretation:

I watch that video online which it gave me the idea about how to get start it, I understand that what it want us to do which we enter an 4 bit digit binary number, and then we will get the corresponding number with our last digit of our student ID, since my last digit of my SID is 7, then I will have this table as following:

In this situation, the video prompt me using the K-Map to solve for all four digit this problem, so we have four set of number and we denote them as G3, G2, G1, and G0, each letter represent each column of the bit, and we denote each row to m1 ~ m15,
now we only want the row that has 1 for each column, so we will get:
G1 = m5, m6, m7, m8, m9, m10, m11, m12
G2 = m1, m2, m3, m4, m5, m6, m7, m8
G3 = m0, m1, m2, m7, m8, m9, m10
G4 = m2, m3, m6, m7, m10, m11, m14, m15
B3-B0 represent the number to input, and the output is G1-G4
Then we draw the K-Map for each of them to find out the boolean expression:
For example for the "G0" Set, the K-Map will look something like this


                    | B3  | B2  | B1  | B0  | G3  | G2  | G1  | G0  |
                    |-----|-----|-----|-----|-----|-----|-----|-----|
                    | 0000 | 0010 | m0  |
                    | 0001 | 0110 | m1  |
                    | 0010 | 0111 | m2  |
                    | 0011 | 0101 | m3  |
                    | 0100 | 0100 | m4  |
                    | 0101 | 1100 | m5  |
                    | 0110 | 1101 | m6  |
                    | 0111 | 1111 | m7  |
                    | 1000 | 1110 | m8  |
                    | 1001 | 1011 | m9  |
                    | 1010 | 1010 | m10 |
                    | 1011 | 1001 | m11 |
                    | 1100 | 1000 | m12 |
                    | 1101 | 0001 | m13 |
                    | 1110 | 0011 | m14 |
                    | 1111 | 0011 | m15 |



                    |         |   B3   |
                    |---------|--------|
                    |         | 0 0 0 0 |
                    |         | 0 0 0 0 |
                    |---------|--------|
                    |         |   B0   |
                    |    B1   | 1 1 1 1 |
                    |    1    | 1 1 1 1 |
                    |---------|--------|
                    |         |   B2   |


So we will get B1(B3')+B3(B1) for G0
             

For this boolean expression, we will apply a NOT gate B3 which represent B3' AND gate for B1 and B3', and AND gate for B3 and B1, And then we use OR gate to connect them together, and this will represent the logic to get the last digit of the output. Hence repeating the same step to all other G3-G1, then we will get our output result.

## Part 3 explaination:

# References for Part 3:
* [Used link](https://www.geeksforgeeks.org/5-variable-k-map-in-digital-logic/)
* [Used link](https://www.geeksforgeeks.org/bcd-to-7-segment-decoder/)

# Generative AI Use

No generative AI used for this part

## Interpretation:

I search the question up online and found this web page (https://www.geeksforgeeks.org/bcd-to-7-segment-decoder/) that is basically explain the idea about how to get start with this, but this web page only talks about the 4 bit represent from 0-9. What the question wants us to do is the last four bit represent 1-4, and the first bit will represnet 5 only. So, we will use VWXYZ to represent them. And then we can set ABCDEFG to represent the horizontal and vertical line for the segment display.

So, we will have the truth table somthing look like this:

                                    | V | W | X | Y | Z | | A | B | C | D | E | F | G |   |
                                    |---|---|---|---|---|---|---|---|---|---|---|---|---|---|
                                    | 0 | 0 | 0 | 0 | 0 | | 1 | 1 | 1 | 1 | 1 | 0 | 0 | m0 |
                                    | 0 | 0 | 0 | 1 | 1 | | 0 | 1 | 1 | 0 | 0 | 1 | 0 | m1 |
                                    | 0 | 0 | 1 | 1 | 1 | | 1 | 1 | 0 | 1 | 1 | 0 | 1 | m3 |
                                    | 0 | 1 | 1 | 1 | 1 | | 0 | 1 | 1 | 0 | 1 | 1 | 0 | m7 |
                                    | 1 | 0 | 1 | 1 | 1 | | 0 | 1 | 0 | 0 | 1 | 0 | 1 | m15 |
                                    | 1 | 0 | 0 | 0 | 0 | | 1 | 0 | 1 | 0 | 1 | 1 | 1 | m16 |
                                    | 1 | 0 | 0 | 0 | 1 | | 1 | 0 | 1 | 1 | 1 | 0 | 1 | m17 |
                                    | 1 | 0 | 1 | 1 | 1 | | 1 | 1 | 0 | 0 | 0 | 0 | 0 | m19 |
                                    | 1 | 1 | 1 | 1 | 1 | | 1 | 1 | 1 | 0 | 0 | 0 | 1 | m23 |
                                    | 1 | 1 | 1 | 1 | 1 | | 1 | 1 | 1 | 0 | 1 | 1 | 1 | m31 |


And in this web page (https://www.geeksforgeeks.org/bcd-to-7-segment-decoder/), it shows how to solve this problem in 4 variables of K-Map, but our current problem has 5 variables, So I search how to solve 5 variables K-Map through this link (https://www.geeksforgeeks.org/5-variable-k-map-in-digital-logic/), it basically shows me in this situation, I notice that the first variable which is the Letter "V" has 0 and 1, then we can draw 2 K-maps to represent the 5 variables, since 2 to the 5 power, two 4X4 K-map will also represent 32 variables, and I suppose this will also work in drawing the K-Map in professor's way so we will have:

         V = 0                      V = 1
        m0 m4 m12 m8            m16 m20 m28 m24
        m1 m5 m13 m9            m17 m21 m29 m25
        m3 m7 m15 m11           m19 m23 m31 m27
        m2 m6 m14 m10           m18 m22 m30 m26

Then, I can now try to input all the numbers into the K-Map from every column of the letter, for example, we can try to input G, and we get:

            V = 0                       V = 1

                |   W                        |   W
        --------|--------            --------|--------               For V = 0, we get: V'XYZ + V'W'X'YZ
        | 0 | 0 | 0 | 0 |            | 1 | 0 | 0 | 0 |               And for V = 1, we get: VXYZ + VW'X'Y'
        ---------------------        ---------------------
        | 0 | 0 | 0 | 0 |            | 1 | 0 | 0 | 0 |               And then OR them together we will get: V'XYZ + V'W'X'YZ + VXYZ + VW'X'Y'
    --------------------- Z      --------------------- Z             (But I have V'W'YZ + V'WXYZ + VXYZ + VW'X'Y' in my circuit, they are the same thing)
        | 1 | 1 | 1 | 0 |            | 0 | 1 | 1 | 0 |               Since V'XYZ + VXYZ can be denote as XYZ, then we can have: XYZ + V'W'X'YZ + VW'X'Y'for G
      Y ---------------------      Y ---------------------
        | 0 | 0 | 0 | 0 |            | 0 | 0 | 0 | 0 |
    ---------------------        ---------------------
            |   X   |                    |   X   |

So by repeating the rest of the letter ABCDEF, we'll complete this 7 segement decoder.