## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-12T12:07:50+00:00
- Post Title: Complete: Alpha Prime *.RES filename encryption

[ from viewtopic.php?t=2648 ]

The encryption method for the filenames is as follows:

```
// Demystified by M.W.Zuurman (Mr.Mouse/Xentax)
// 
// General idea:
//
// 1. The encryption XORs the characters in the strings with a seed value 
// 2. The seed value is the ascii-code of a letter picked from the encryption string 'insanity' 
//
// The method to pick the right character from the encryption string is:
//
// 1. Take the position of the character to be XORed (starting from 0)
// 2. AND this value with 7 
// 3. Look up the character in the encryption string that is at this position
// 4. XOR the character in the original string with the ASCII value of that encryption character
// 5. Loop this until the whole string is encrypted
//
// In raw useless code: 
//
// Declare and assign the following variables:
int Count ; // counter to loop through each character in the original string (OString)
int Lookup ; // Lookup value to get the character from the encryption string 'insanity' (EString)
int SSize ; // the size of the original string 

while (Count < SSize) {
Lookup = Count AND 7;
DString[Count] = OString[Count] XOR EString[Lookup] ;
Count += 1 ;
}

// That should be it in schematic code. 
// Note that the filenames will never be long enough for the 'AND 7' method to fail getting a number between 0 and 7.

```
