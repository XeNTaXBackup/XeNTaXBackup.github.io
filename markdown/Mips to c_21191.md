## Post #1
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2019-09-29T22:12:19+00:00
- Post Title: Mips to c

I recently just tried to do some mips to c can someone tell me if this is right I think I did some of it right if someone does correct it can you tell me where I messed up at im really confident that I got a lot of it right what im doing here is trying to reverse engineer a piece of code from a popular ps2 game so much help would be appreciated thank you.

MIPS:

		    var_20          = -0x20
		    var_10          = -0x10

	            addiu   $sp, -0x20       # Add Immediate Unsigned
                    sd      $ra, 0x20+var_10($sp)  # Store Doubleword
                    sq      $s0, 0x20+var_20($sp)  # Store Quadword
                    move    $s0, $a0
                    bnez    $a1, loc_13DF88  # Branch on Not Zero
                    nop

                    move    $a0, $s0
                    jal     sub_13DF20       # Jump And Link
                    nop
                    move    $a0, $v0
                    move    $a1, $zero
                    la      $a2, aAmobject_c  # "amObject.c"
                    li      $a3, 0x8A  # 'è'  # Load Immediate
                    jal     sub_13AAB0       # Jump And Link
                    nop
                    move    $a1, $v0
                    nop

                    loc_13DF88:                              # CODE XREF: sub_13DF40+10j
                    sw      $s0, 0($a1)      # Store Word
                    lw      $v0, 0x10($s0)   # Load Word
                    sw      $v0, 4($a1)      # Store Word
                    addiu   $v1, $a1, 8      # Add Immediate Unsigned
                    move    $a0, $zero
                    b       loc_13DFB8       # Branch Always
                    nop
                   # ---------------------------------------------------------------------------
                   .align 3

                   loc_13DFA8:                              # CODE XREF: sub_13DF40+80j
                   sw      $zero, 0($v1)    # Store Word
                   sw      $zero, 4($v1)    # Store Word
                   addiu   $a0, 1           # Add Immediate Unsigned
                   addiu   $v1, 8           # Add Immediate Unsigned

                   loc_13DFB8:                              # CODE XREF: sub_13DF40+5Cj
                   lw      $v0, 4($a1)      # Load Word
                   slt     $v0, $a0, $v0    # Set on Less Than
                   bnez    $v0, loc_13DFA8  # Branch on Not Zero
                   nop
                   move    $v0, $a1
                   ld      $ra, 0x20+var_10($sp)  # Load Doubleword
                   lq      $s0, 0x20+var_20($sp)  # Load Quadword
                   addiu   $sp, 0x20        # Add Immediate Unsigned
                   jr      $ra              # Jump Register
                   nop










C Code:

#include <iostream>
#include <Windows.h>
#include <string>
using namespace std;


int main()
{

	return 0;
}

int amObject(int *a0, int *a1)
{
	int v0;
	*s0 = *a0;

	if(*a1 == 0)
	{
		*a0 = *s0

		sub_13DF20();

		a0 = v0; // zeroing out the address
		a1 = 0; // zeroing out the address
		a3 = aAmobject_c; // aAmobject_c is a address to something

		sub_13AAB0();

		a1 = v0;

		goto loc_13DF88;
	}


	if(*a1 != 0)
	{
		loc_13DF88:

		*a1 = *s0;
		v0 = *s0; // address in s0 is moved 16 bytes over
		*a1 = v0; // address in a1 is moved 4 bytes over
		v1 = a1 + 8;
		a0 = 0; // zeroing out the address


		v1 = *a1 // adress in a1 is moved 4 bytes over

		if(a0 < v0)
		{
			v0 = 1;

			while(v0 != 0)
			{
				*v1 = 0;
				*v1 = 0; // v1 is moved 4 bytes over
				a0 = 1; 
				&v1 + 8;
			}
		}

		else
			{
				v0 = &a1
				return;
			}
	}

}
## Post #2
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2019-10-11T08:58:55+00:00
- Post Title: Mips to c

Not really. More like:

```
unsigned int *function(unsigned int *pointer1, unsigned int *pointer2)
{
	if (pointer2 == NULL)
	{
		//pointer2 = NULL; //useless
		pointer2 = sub_13AAB0(sub_13DF20(pointer1), pointer2, "amObject.c", 0x8a);
	}
	pointer2[0] = (unsigned int)pointer1;
	pointer2[1] = pointer1[4];
	
	unsigned int *tempPointer = pointer2 + 2;
	for (unsigned int i = 0; i < pointer2[1]; i++, tempPointer += 2)
	{
		tempPointer[0] = 0;
		tempPointer[1] = 0;
	}
	return pointer2;
}
```


I just quickly scanned it, so there may be mistakes, but it should be mostly correct. It is possible all these were void**, not unsigned int*, but the usage later as both pointer storage (32bit system) and counters suggests otherwise.
