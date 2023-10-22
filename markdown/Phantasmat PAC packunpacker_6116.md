## Post #1
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2011-02-21T15:42:33+00:00
- Post Title: "Phantasmat" PAC pack/unpacker

More about the game can be found here : [http://www.bigfishgames.com/download-ga ... index.html](http://www.bigfishgames.com/download-games/11073/phantasmat/index.html)
This is the first module for my tool called "Unpakke", so you will need both the unpakke.exe and upkk_phtsm.dll to pack/unpack these PAC files.


Learn more by clicking here: [http://nullsecurity.org/unpakke/](http://nullsecurity.org/unpakke/)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T12:47:43+00:00
- Post Title: "Phantasmat" PAC pack/unpacker

I have just downloaded the game now and noticed it had a very very basic format so I wrote a quick script for it:

```
get FILES long
for i = 0 < FILES
    get NAMESZ short
    getdstring NAME NAMESZ
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
