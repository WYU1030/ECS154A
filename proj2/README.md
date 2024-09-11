# Project 2 README

Student 1: Weiyang Yu (919410927)
Student 2: Dunh Adam Lee (921476881)

## References
https://www.youtube.com/watch?v=R7KKE1jXYns

## Project Status
Part 1 and 2 are implemented. Part 3 partially implemented.

## Known Issues
The project fails to function properly in part 3. The lock can cycle through the 4 states: Unlocked -> Locking -> Locked -> Locking.
H

## Part 1
For part 1, we used a decoder to break down the outputs from 7 bits to 4 bits. 


## Part 2

For part 2, we have 3 states: Idle (00), Valid (01), and Invalid (10) that are represented by 2 D-Flip Flops. 

During idle, if V = 0, the state remains idle. Otherwise, it goes to valid.

During valid, if V = 0 or V = 1, then it proceeds to invalid.

During invalid, if V = 0, then it goes to idle, else, if V = 1, then the state transitions back to valid.

## Part 3

For part 3, we have 4 main states: Unlocked (000), Locking (001), Locked (100), Unlocking (101)

Each main state also has 4 substates. 
Part 3 is not complete, however, it can cycle from the 4 main states. The only thing left to implement is storing a 3-digit combination and checking to see if a matching combination is input to unlock the lock.