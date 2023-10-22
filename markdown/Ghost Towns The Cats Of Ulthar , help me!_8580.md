## Post #1
- Username: danny
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Apr 11, 2011 6:16 pm
- Post datetime: 2012-03-17T23:07:40+00:00
- Post Title: Ghost Towns The Cats Of Ulthar , help me!

I need to decompress this archive of the game Ghost Towns - The Cats Of Ulthar help me please.

The archive is here!

[http://www.mediafire.com/?ixbxzbsvsa16ti7](http://www.mediafire.com/?ixbxzbsvsa16ti7)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-20T15:44:05+00:00
- Post Title: Ghost Towns The Cats Of Ulthar , help me!

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "rpfe"
get NUM long
for i = 0 < NUM
    get NAMESZ long
    getdstring NAME NAMESZ
    putarray 0 i NAME
next i
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get NUM long
    getarray EXT 0 NUM
    get NUM long
    getarray NAME 0 NUM
    string NAME += "."
    string NAME += EXT
    log NAME OFFSET SIZE
next i
```
