## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-22T14:37:12+00:00
- Post Title: PS2 Eureka Seven .mb file

Hi,
I need help decompressing the PS2 Eureka Seven .mb file.

```
MB13CDVDy...e?...@..ARCCeureka_us_cpy.ico...................bc.
```

Heres an sample file : 
If you want more samples i can upload more. 

Merry Christmas in advance.
## Post #2
- Username: XeroNazoBlaze
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 06, 2009 3:34 am
- Post datetime: 2010-12-31T19:21:37+00:00
- Post Title: PS2 Eureka Seven .mb file

Hello there, youngmark!

Actually, these files are file containers without any compression. Here's the script:

```
# MB format unpacker script for Quickbms
# Made by XeroNazoBlaze

ImpType Standard ;
Idstring "MB13CDVD" ;
Get NOF long ;
Get NULL long ;
Get FFO long ;
Get NULL long ;
For I = 0 < NOF ;
Getdstring NAME 0x20 ;
Get FOFFSET long ;
Get FSIZE long ;
Get NULL long ;
Get NULL long ;
Math FOFFSET *= 2048 ;
Math FOFFSET += FFO ;
Log NAME FOFFSET FSIZE ;
Next I 
```


Once you've unpacked the MB files, there will be a bunch of FPKs files (these are file containers too). Here's the script:

```
# FPK format unpacker script for Quickbms
# Made by XeroNazoBlaze

ImpType Standard ;
Idstring "FPK" ;
Get NULL byte ;
Get NOF long ;
Get NULL long ;
Get FFO long ;
For I = 0 < NOF ;
Getdstring NAME 0x40 ;
Get FOFFSET long ;
Get NULL long ;
Get FSIZE long ;
Get NULL long ;
Math FOFFSET += FFO ;
Log NAME FOFFSET FSIZE ;
Next I
```


Hope this helps. If there's any problem, please let me know .
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-01-01T03:40:02+00:00
- Post Title: PS2 Eureka Seven .mb file

Thanks XeroNazoBlaze!
Your bms script is perfect.
Here are extract data
## Post #4
- Username: XeroNazoBlaze
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 06, 2009 3:34 am
- Post datetime: 2011-01-01T04:07:01+00:00
- Post Title: PS2 Eureka Seven .mb file

I'm glad it worked. Although the file sizes doesn't match with the values of the file table (due to some padding), don't worry, those files aren't corrupted nor anything. Remember, those scripts work for both titles of Eureka Seven (New Wave/New Vision).

And Happy New Year for you too .

P.S: Sorry for my English .

P.S.S: The content in the MDL and the XPK files can be extracted using the FPK script!
## Post #5
- Username: hien90
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 03, 2012 7:55 pm
- Post datetime: 2012-08-03T12:33:44+00:00
- Post Title: PS2 Eureka Seven .mb file

when unpack a fpk file there are .pak file how to unpack them
## Post #6
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-09-05T06:47:30+00:00
- Post Title: PS2 Eureka Seven .mb file

I have .MB files from another game: Mobile Suit Gundam: Lost War Chronicles [PS2].

Tried using your script, XeroNazoBlaze, but it gives a message: 



So changing "MB13CDVD" to "MB11CDVD" inside the script doesn't quite do the trick. 
It finds the first file with the proper file name, but then stalls and gives an error message. 

It looks like if some slight alterations were made, the script should work on these type of .MB as well. 

If anyone can take a look, I'd be glad to provide the sample files. The smallest one for example is OLM.MB is 2mb.
## Post #7
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-09-07T05:27:55+00:00
- Post Title: PS2 Eureka Seven .mb file

Many thanks to youngmark for pointing to the right script that can handle Gundam's .MB files:

```
# by Fatduck     Nov 09
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "MB11CDVD"
get NUMRES long
get IDXTBLEND long              #no use
get OFSBASERES long
get IDXTBLHEADER long           #no use

for i = 0 < NUMRES
   getdstring RESNAME 0x20
   get OFSRES long
   math OFSRES *= 0x800
   math OFSRES += OFSBASERES
   get SIZERES long
   get UNKNOWN long
   
   log RESNAME OFSRES SIZERES
next i
```
## Post #8
- Username: hien90
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 03, 2012 7:55 pm
- Post datetime: 2013-08-31T03:11:36+00:00
- Post Title: PS2 Eureka Seven .mb file

When i extrack stream.mb there are bmg.adi files. I think this is soundtrack of the game but i dont know how to open it. Can anyone please help me how to open this file type ?
## Post #9
- Username: ruiner9
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 08, 2014 8:47 pm
- Post datetime: 2014-10-08T12:50:55+00:00
- Post Title: PS2 Eureka Seven .mb file

I know I'm dredging up an old topic, but I was researching the audio for the Eureka SeveN series and discovered that the .adi files are actually just .ads files, 100kbps, 48khz.

Rename the extension and they should play using VGMStream.
## Post #10
- Username: Mowthan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 30, 2019 11:17 pm
- Post datetime: 2020-09-06T09:01:47+00:00
- Post Title: PS2 Eureka Seven .mb file

Sorry to necro an old thread again, but I have recently become interested in the ps2 eureka games and have been trying to dig through the files.

I first tried to use ninja ripper with pcsx2, but the game uses back face culling, so the models come out incomplete.

So I tried using the scripts posted here to extract the contents of the game.mb file and the .fpk files within and I now have a bunch of directories with what look like animation files and other assets.

In these, I have .pak files which should contain things like sprites, textures, models and audio, but I can't open them.

I have tried using winrar and 7zip but both say the archives are unreadable. I then tried universal extractor, game extractor and other bms scripts, but to no success.

Has anyone had any luck extracting them, or any ideas on what to try next?

Update:

I was able to extract some files from the first available .pak : mp_aa01_001.pak using the following batch script to run offzip:

    offzip.exe -z -15 -a "input/MP_AA01_001.pak" "output/directory" 0x0

    PAUSE

Where "input/MP_AA01_001.pak" is the location of the .pak and "output/directory" is the output.

"PAUSE" prevents the console from closing once done so I could read the printout.

I have no idea what the parameters "-z -15 -a" are for, but I'm sure "0x0" means start from the first byte (no offset).

The console threw up tonnes of errors saying "zlib z_data_error the data in the file is not in zip format" but it did manage to process 38% of the .pak file and I now have a directory filled with .dat .rpp .yuu .sw7 .fff .ffa files and more, although I suspect some of these may be garbage.

I honestly have very little idea what I'm doing, mostly flying by the seat of my pants, but I'll post more info as I find it.

Update #2:

Ok, so it seems that the directories containing the .pak files might be mission / level data.

The files extracted from game.mb include a set of files named cha_01 -> cha_016 and lfo_01 -> lfo_18.

They are .xts files and may contain the vertex data for characters and mechs meshes.

Update #3:

The .xts files only contain images that look like character profile pictures, not really worth looking into.

There are however .mdls which I overlooked.
They contain a mix of data and textures.

Unpacking them with offzip gives only a small amount of useful data, but there are files that are a couple of textures and some which have what look to be names of bones for an armature.

If anyone can add further insight, I would be grateful.
