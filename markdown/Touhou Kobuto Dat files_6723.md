## Post #1
- Username: Jousway
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 04, 2011 8:45 pm
- Post datetime: 2011-06-04T13:13:02+00:00
- Post Title: Touhou Kobuto Dat files

Yo some of you guys might now DDR (Dance Dance Revolution) well there is an free pc version called StepMania and I'm working on a theme for it.
This theme is mainly based on Touhou 12.3 because I mainly like the interface it uses.
Also in DDR you have these dancing characters on the background that just randomly dance and I tought it was a cool idea to include these Touhou characters.
There is this 3D fighter fan made game thats called Touhou Kobuto and I'm trying to get the 3D models from it so I can edit them in Milkshape 3D and add them in StepMania.

I have already checked the files in a C++ IDE, a Hex editor and Notepad++ but I cant find a readable line that defines what the file is so I'm kinda stuck.
Please help me to find a way to open these .dat files and it will be greatly appreciated. 

The files in question:

[http://www.jousway.co.uk/res.dat](http://www.jousway.co.uk/res.dat) 90.237 KB
[http://www.jousway.co.uk/resL.dat](http://www.jousway.co.uk/resL.dat) 186,904 KB
[http://www.jousway.co.uk/resS.dat](http://www.jousway.co.uk/resS.dat) 49,611 KB

only a 44 kb file that probably only includes system info but I still included it in case it has information that can tell what the file type the dat files are but I doubt it.
[http://www.jousway.co.uk/system.dat](http://www.jousway.co.uk/system.dat)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-08T16:06:03+00:00
- Post Title: Touhou Kobuto Dat files

Looks like it XOR's each byte with its offset, looping 00 to FF and repeat.
First 4 bytes is the idstring.

Don't know how to write the script to deal with that kind of encryption though lol (haven't come across any examples for reference)

Might have to do something after XOR'ing everything though..
## Post #3
- Username: Jousway
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 04, 2011 8:45 pm
- Post datetime: 2011-06-08T17:17:25+00:00
- Post Title: Touhou Kobuto Dat files

aw :< oh well thanks for trying
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-08T19:07:00+00:00
- Post Title: Touhou Kobuto Dat files

script for quickbms (you need the latest version):

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

encryption "incremental xor" 0x00
get SIZE asize
log MEMORY_FILE 0 SIZE
encryption "" ""

endian big
idstring MEMORY_FILE "AAFC"
get DUMMY long MEMORY_FILE
getdstring DUMMY 8 MEMORY_FILE
get FILES long MEMORY_FILE
savepos START MEMORY_FILE
for EXTRACT = 0 < 2
    goto START MEMORY_FILE
    for i = 0 < FILES
        get NAMESZ long MEMORY_FILE
        math NAMESZ *= 2
        getdstring NAME NAMESZ MEMORY_FILE
        putvarchr NAME NAMESZ 0 short
        set NAME unicode NAME
        get DUMMY long MEMORY_FILE
        get SIZE long MEMORY_FILE
        if EXTRACT != 0
            log NAME OFFSET SIZE MEMORY_FILE
            math OFFSET += SIZE
        endif
    next i
    savepos OFFSET MEMORY_FILE
next EXTRACT
```
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-12T14:54:11+00:00
- Post Title: Touhou Kobuto Dat files

lol I looked at the model files and it seems they've also got that incremental XOR encryption.
Is this common?
