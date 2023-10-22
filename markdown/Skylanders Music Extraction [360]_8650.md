## Post #1
- Username: Garrland
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 28, 2012 6:11 am
- Post datetime: 2012-03-27T22:34:46+00:00
- Post Title: Skylanders Music Extraction [360]

I'm attempting to extract the level music from the 360 version of the game. I've used quickbms to get the audio/levels/level_hub.bnk extracted to 260 files. Looking in a hex editor they are all RIFX files that are mono/44100.   The format tag is coming up 358 (0x0166). What format is that? Google is failing me an it's not in the windows headers. I've attempted to run ToWav but it doesn't do anything.  Running ww2ogg I just gets a "Parse error: RIFF truncated" error. I'm suspecting that files are in a format the tools just don't understand. I even tries to change it to a RIFX to RIFF and load it in Audacity as a raw file but no luck.   

Any help would be appreciated. This is my first attempt at extracting audio from a 360 title. 

Here is a link to the .bnk file. 
[http://www.sendspace.com/file/w9xmfm](http://www.sendspace.com/file/w9xmfm)

Here is the bms script I used to extract. It's not mine, I got it from a Google search.

```
idstring "BKHD"
get OFFSET long
math OFFSET += 8
goto OFFSET
idstring "DIDX"
get DIDX_SIZE long

savepos BASE_OFF
math BASE_OFF += DIDX_SIZE
math BASE_OFF += 8  # DATA chunk

math FILES = DIDX_SIZE
math FILES /= 12

for i = 0 < FILES
    get DUMMY long
    get OFFSET long
    get SIZE long

    math OFFSET += BASE_OFF
    log "" OFFSET SIZE
next i
```



Thanks
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-03-28T03:51:03+00:00
- Post Title: Skylanders Music Extraction [360]

I'm trying to modify xmash to deal with this correctly, at issue is the fact that these are XMA data, and also some of the data is stored in a separate stream file.

Is there a file called 884179355.wav or 884179355.xma around? If so could you upload that?
## Post #3
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-20T21:06:43+00:00
- Post Title: Skylanders Music Extraction [360]

it's about arc and bld ? it's possible to extract voice
