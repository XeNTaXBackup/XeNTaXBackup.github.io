## Post #1
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2020-08-14T01:40:16+00:00
- Post Title: Decryption Algorithm Reverse

This is a decryption algorithm for a game could someone reverse this into c++. This is ppc

loc_39F50:
addi      r29, r26, 0x18C
li        r6, 1
lis       r4, 4
clrldi    r5, r29, 32
mr        r3, r31
bl        sub_18E8D0
nop
mr        r3, r31
bl        sub_8619C
nop
lis       r6, 0x23CF # 0x23CF405D
lis       r0, 4
li        r7, 0
ori       r6, r6, 0x405D # 0x23CF405D
mtspr   CTR, r0
li        r9, 0x7A69

loc_39F90:
add       r10, r7, r29
addi      r7, r7, 1
clrldi    r10, r10, 32
mulli     r11, r9, 0x1A3
addi      r11, r11, 0x181D
lbz       r8, 0(r10)
mulhwu    r0, r11, r6
srwi      r9, r0, 12
mulli     r9, r9, 0x7262
subf      r9, r9, r11
slwi      r0, r9, 8
subf      r0, r9, r0
mulhwu    r0, r0, r6
extrdi    r0, r0, 8,44
xor       r0, r0, r8
stb       r0, 0(r10)
bdnz+     loc_39F90
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-14T09:54:08+00:00
- Post Title: Decryption Algorithm Reverse

Try to use Ghidra or IDA Pro to decompile this.
