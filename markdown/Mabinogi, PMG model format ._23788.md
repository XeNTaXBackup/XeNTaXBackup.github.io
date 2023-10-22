## Post #1
- Username: jackyjoy123
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 26, 2021 10:47 pm
- Post datetime: 2021-04-24T11:22:37+00:00
- Post Title: Mabinogi, PMG model format ?.

Hello,

I do not have much experience with model formats other than very basics, so I thought I'd ask here.

This is what I have determined of the file format so far:
CODE: SELECT ALL

char[4] magic // 'pmg\0'
byte majorversion // 2
byte minorversion // 1
dword unk1
char[128] name
dword groupcount
[https://creditcardsupportx.com/bobs-fur ... edit-card/](https://creditcardsupportx.com/bobs-furniture-credit-card/)
[https://creditcardsupportx.com/quicklane-credit-card/](https://creditcardsupportx.com/quicklane-credit-card/)
[https://creditcardsupportx.com/barnes-a ... astercard/](https://creditcardsupportx.com/barnes-and-noble-barclay-mastercard/)
structure * groupcount
char[64] groupname
dword meshcount
substructure * meshcount
dword meshdatasize
char[32] meshname
char[168] unk2

thanks
jackyjoy
