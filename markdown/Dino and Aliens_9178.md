## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T12:37:51+00:00
- Post Title: Dino and Aliens

```
# script for QuickBMS http://quickbms.aluigi.org

get FULLSIZE asize
for OFFSET = 0 < FULLSIZE
    get NAME string
    get SIZE long
    savepos OFFSET
    encryption xor NAME
    log NAME OFFSET SIZE
    math OFFSET += SIZE
    goto OFFSET
next
```
## Post #2
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-06-30T13:35:23+00:00
- Post Title: Dino and Aliens

thanks the script works
but how to read the encrypted key?
also I would like to know how
maybe is some a tutorial?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T13:36:41+00:00
- Post Title: Dino and Aliens

in this case it was easy because you had many tga files that contain 0x00 bytes in them so the key was clearly visible and it was just the same filename :)
file_content XOR filename
## Post #4
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-06-30T14:54:49+00:00
- Post Title: Dino and Aliens

thanks
like you recognize and as a looking?
can you give decrypted key?
