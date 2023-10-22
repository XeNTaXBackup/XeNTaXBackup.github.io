## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-15T14:19:46+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

Hey guys,
again diving into Backyard Wrestlings world and trying to have better access to the textures. Good news: They have been figured out a long time ago and i was able to save the script:

```
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE4 0 0 ;
log MEMORY_FILE5 0 0 ;
Get Q ASIZE 0 ;
Math number = 0 ;
For T = 0 < Q ;
Math number += 1 ;
findloc OFFSET string "\x50\x32\x4E\x00\x00\x00\x00\x00" 0 0 ;

If OFFSET = 0 ;
Math T = Q ;
Math T += 1 ;
EndIF ;

Math test = 0 ;

If OFFSET != 0 ;
GoTo OFFSET 0 ;
SavePos Start 0 ;
GoTo 0x28 0 SEEK_CUR ;
Get test Long 0 ;
Math T = Start ;
EndIF ;

If test = 0x400 ;
Put Start Long MEMORY_FILE4 ;
Put 0 Long MEMORY_FILE4 ;
EndIf ;

If OFFSET != 0 ;
Math T += 12 ;
Math T -= 1 ;
EndIF ;

Next T ;
```

The issue being that they get exported in a weird .TXD file format that only seems to open with this tool:
[http://www.thegtaplace.com/downloads/f4 ... txd-viewer](http://www.thegtaplace.com/downloads/f457-ps2-txd-viewer)
And now some of them don't even seem to be exportable for me anymore....

To get the .TXD files you need to use the above listed quickbms script on the GAMEDATA.WAD file ----> get it here: [https://we.tl/t-3U4LAbwobT](https://we.tl/t-3U4LAbwobT) (Link only exists for 7 Days!)

So I kindly want to ask everybody with the required knowledge to change the script so it exports ALL textures (alot of them are missing...mainly level textures and weapons...maybe because of different resolution?) and to a more common format like .png. Would a Noesis script be better?
If you just want to crack open the GAMEDATA.WAD use this script:

```
Get files Long 0 ;
GoTo 0x800 0 ;
SavePos base 0 ;
For x = 1 To files ;
GoTo base 0 ;
Get offset Long 0 ;
Get size Long 0 ;
SavePos base 0 ;
GoTo offset 0 ;
Get test Long 0 ;
Math name = x ;
If test = 1347241266
string name += .mesh ;
EndIF ;
Log name offset size 0 ;
Next x ;
```


If you want more detailed information about the scripts and the games files, please see my older post about the character models:
[viewtopic.php?f=16&t=19370&hilit=backyard+wrestling](https://forum.xentax.com/viewtopic.php?f=16&t=19370&hilit=backyard+wrestling)

Thank you guys again for listening and providing the help to make this awesome forum.....so awesome 

Best regards
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-25T07:30:00+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

Friendly bump 

Or might this be to much to ask for?
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-11-27T07:53:23+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

i had no luck with the scripts you posted so i whipped up this one to get all tex files from your sample.  

```
math i = 1
findloc OFFSET binary "\x50\x32\x4E\x00\x00\x00\x00\x00"
do
    goto OFFSET
    goto 0x40 0 seek_cur
    get SIZE long
    string NAME p "%s\%d.tex" FOLDER i
    log NAME OFFSET SIZE
    findloc NEXT_OFFSET binary "\x50\x32\x4E\x00\x00\x00\x00\x00" 0 "" -1
    math OFFSET = NEXT_OFFSET
    math i + 1
while NEXT_OFFSET != ""

```

and still no luck getting decent results with many of the extracted tex files
even using Console Texture Explorer.   
i'm guessing some ps2 shuffling thing going on with many of them.
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-27T21:29:07+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

> i had no luck with the scripts you posted so i whipped up this one to get all tex files from your sample.
KILLA!! Thank you Very much for helping me out here 
Im still at work, but im going to Test your script as soon as im back home 

Do the textures export into something readable or this weird gta 3 .txd files? Because they only seem to open with that program i Linked in my first Post....nur success with magictxd for example :-/

Thank you again man
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-11-28T02:35:46+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

i don't know what txd files you refer to, your first script posted looks incomplete and gets no results from your sample.
the script i posted only finds and extracts each tex file from the sample, you still need to find a way
to parse the tex files, this PS2 stuff has always been weird to me.  

edit
okay i think we got something here, a Noesis python script to open the tex files extracted by my bms script.  


 tex_BackyardWrestlingDTTAH_PS2_tex.zip
(936 Bytes) Downloaded 35 times


supports 4bit and 8bit textures with shuffled palette.
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-28T14:29:09+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

WOW! Thank you for the Noesis script!
I just tested it and had a brief look through the exported textures. It looks like they are all there! 

2296 to be exact 

Some seem to double export but thats no problem 
They export halftransparent though... with cycle blend (F11) I can get the "clear" image after a few clicks. Do you happen to know on how I can let them export opaque?

Thank you very much again for making this happen
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-11-28T17:35:25+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

i don't think removing the alpha is a good idea being that some rely on it
but if you insist you can go into the script and change these lines:

```
...
    data = rapi.imageDecodeRawPal(data, palette, imgWidth, imgHeight, 4, "r8 g8 b8 a8")
```


to this:

```
...
    data = rapi.imageDecodeRawPal(data, palette, imgWidth, imgHeight, 4, "r8 g8 b8 p8")
```


just change the two a8 to p8  

i may look at this again later to see if i spot any flags that may enable/disable transparency on some textures.
## Post #8
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-29T01:38:04+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

Thank you!
That helped alot! Is there any Name reference for the .tex files?
## Post #9
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-01-02T23:42:04+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

> Reply from Acewell ↑Thu Nov 28, 2019 10:35 am at Thu Nov 28, 2019 10:35 am
>
> 
...this PS2 stuff has always been weird to me.

I hope you have some more energy for another round of backyard wrestling 

Backyard Wrestling 2 - There goes the Neighborhood seems to use the same engine/setup/structure with minor tweaks to it.......thats my rookie view on it. In the first installment characters where limited two one texture....a few exceptions used a second smaller one (like hair or boots). this time they come with more textures for the whole body and some of them are not square (i checked with ninja ripper once back in the day).
The same BMS script to extract the gamedata.wad file works here, too. The old tex script i shared in my first post got me .txd files again....they couldnt be viewed with ps2txdviewer though. When I use the script that you kindly made for me it gave me this error:


So I was hoping you could have another look at it this time a slightly different file and work your texture magic once more.
Heres a download link to the game file, some texture samples and the scripts i used:
[https://we.tl/t-k7gBTdjzFp](https://we.tl/t-k7gBTdjzFp) (Link will only last for 7 days!)

Thank you very much and happy new year
## Post #10
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-01-07T01:58:52+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

...so i kinda got help by a friend


```

struct{
    char header[84];
    int width;
    int height;
    int bbp;
    char header2[100 - 4 - 32];

    struct{
        int header[5];
        int16 zero;
        int16 type; //0 => dxt5 or 64 => swizzle pallete
        int header3[2];
        int width;
        int height;
        char unk[40 - 16 + 7];
        char headerSize;
        char header2[headerSize];

        if (type == 64){ //palette
            char data[width*height];
        
        }else{ //real image
            char data[width*height*4];
        }


    }data[2]<optimize=false>;

}entry;
```

DXT5 Textures with normal ps2 swizzeling
this is the info he got me.
could you guys please create a noesis script for it?
heres a sample file:
[https://cdn.discordapp.com/attachments/ ... .162.0.TXD](https://cdn.discordapp.com/attachments/550649773363822672/796445026904702996/texture.162.0.TXD)
[https://cdn.discordapp.com/attachments/ ... .216.0.TXD](https://cdn.discordapp.com/attachments/550649773363822672/796445062811877386/texture.216.0.TXD)
[https://cdn.discordapp.com/attachments/ ... 2983.0.TXD](https://cdn.discordapp.com/attachments/550649773363822672/795102435349233674/texture.2983.0.TXD)
## Post #11
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-01-18T01:17:16+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

*bump*
Please, any help is appretiated
## Post #12
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-01-25T08:10:22+00:00
- Post Title: Backyard Wrestling - Don't Try This At Home Textures (HELP!)

A Manual way (except ninja ripper, 3dripperx) would be already enough aswell! I just wanna finish the collection
