## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-05-23T22:28:31+00:00
- Post Title: Archlord Game File Format

Well i found this game and i see have lot of good stuff to see, this its the .data files of the animations, texture and meshes files, first need unpack this data files then make a importer or exporter of the model.

download link
[http://www.megaupload.com/?d=UFTDQ4ZG](http://www.megaupload.com/?d=UFTDQ4ZG)
## Post #2
- Username: jin76
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 06, 2010 12:31 am
- Post datetime: 2011-06-14T14:55:03+00:00
- Post Title: Archlord Game File Format

yes this game is definitely worth looking into and is one my fav till this day
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-16T17:52:40+00:00
- Post Title: Archlord Game File Format

Yep but its not easy unpack the .Dat format, i see this its very encrypted.
## Post #4
- Username: saurav
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-16T18:15:11+00:00
- Post Title: Archlord Game File Format

I found a tool to decrypt the index file after that the extractor is easy.
[ALCryptDecryptINI.rar](https://xentaxbackup.github.io/file/4343_ALCryptDecryptINI.rar)
## Post #5
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-06-17T13:58:50+00:00
- Post Title: Archlord Game File Format

One man also can extract .DAT files - [http://www.elitepvpers.com/forum/archlo ... hread.html](http://www.elitepvpers.com/forum/archlord/525510-data-dat-extraction-developer-thread.html)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-17T18:26:53+00:00
- Post Title: Archlord Game File Format

quickbms script to extract these.
make sure you use the ini decryptor first.

```
#Archlord PC
#from chrrox

open FDSE Data.Dat 0
open FDSE Reference.Dat 1


get files long 1
get foldersz long 1
get folder string 1
string folder + \
for i = 0 < files
    set name folder
    get NAMESIZE long 1
    getdstring name1 NAMESIZE 1
    string name + name1
    get offset long 1
    get size long 1
        log name offset size
next i

```
## Post #7
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-17T22:23:08+00:00
- Post Title: Archlord Game File Format

Amazing advance in only something Hours chroxxx, thanks man.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-18T00:14:15+00:00
- Post Title: Archlord Game File Format

I am working on the model format its not to hard the structure is just a little weird once i get that a converter will not be hard.
[archlord2.png](https://xentaxbackup.github.io/file/4349_archlord2.png)
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-18T19:00:51+00:00
- Post Title: Archlord Game File Format

Texture Converter only use on unencrypted textures.

```
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
get dxt long
get height short
get width short
get null byte
get mips byte
putVarChr MEMORY_FILE 0xC width long
putVarChr MEMORY_FILE 0x10 height long
putVarChr MEMORY_FILE 0x54 dxt long
get size asize
math size - 0x90
get name basename
string name + .dds
append
log MEMORY_FILE 0x90 size
append
math size + 0x80
log name 0 SIZE MEMORY_FILE
```
## Post #10
- Username: pao com ovo
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-19T03:29:59+00:00
- Post Title: Archlord Game File Format

Ok here is a 3ds max import script.
--supported
Bones
Meshes
Uv's
Weights
--not yet supported
animation
auto material assignment
Correct Bone id match-up

If anyone sees how to line up the bones please let me know
[Archlord3.rar](https://xentaxbackup.github.io/file/4355_Archlord3.rar)
## Post #11
- Username: jin76
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 06, 2010 12:31 am
- Post datetime: 2011-06-20T17:22:29+00:00
- Post Title: Archlord Game File Format

wow great progress, keep it up guys
## Post #12
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-21T00:09:16+00:00
- Post Title: Archlord Game File Format

i take the time of chrox to develop this script for this game and i think its a record, 4 days, incredible, but also i have a question this code to decrypt the textures, how to use this?ç
i need save this like a .exe file and drag the textures to the .exe?

goto 0x80
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
get dxt long
get height short
get width short
get null byte
get mips byte
putVarChr MEMORY_FILE 0xC width long
putVarChr MEMORY_FILE 0x10 height long
putVarChr MEMORY_FILE 0x54 dxt long
get size asize
math size - 0x90
get name basename
string name + .dds
append
log MEMORY_FILE 0x90 size
append
math size + 0x80
log name 0 SIZE MEMORY_FILE
## Post #13
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-06-21T01:52:29+00:00
- Post Title: Archlord Game File Format

its a BMS lol use quickBMS

also I converted all the main models (4200+)

took screenshot of everything (No Materials Assigned)
[http://www.megaupload.com/?d=V5BKJ2EI](http://www.megaupload.com/?d=V5BKJ2EI)

use the screenshots to help you locate content
## Post #14
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-06-21T02:30:59+00:00
- Post Title: Archlord Game File Format

Thank you chrrox, everything working fine.

@mariokartn64 did you make any progress on Nariko?
## Post #15
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-21T20:24:12+00:00
- Post Title: Archlord Game File Format

Omg thanks MarioKart this png files are very ussefull, Well, two issues, the first its the script to import have error to me in max2010 and max 9



The second its i use the DDS size of the quickbms texture its now a 202MB DDS FILE. the image its very big and it only one, i test this in character folder. ANY IDEA?
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-21T20:29:25+00:00
- Post Title: Re: Archlord Game File Format

post the model you are trying to import.
## Post #17
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-22T17:27:20+00:00
- Post Title: Re: Archlord Game File Format

Yes of course its the Chacracter Models.

[http://www.megaupload.com/?d=KBAYXT69](http://www.megaupload.com/?d=KBAYXT69)
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-23T10:52:41+00:00
- Post Title: Re: Archlord Game File Format

> Reply from Rimbros
>
> Yes of course its the Chacracter Models.

http://www.megaupload.com/?d=KBAYXT69

You encrypted the model files........

Only the textures are encrypted do not encrypt the model files.
## Post #19
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-24T21:19:50+00:00
- Post Title: Re: Archlord Game File Format

mmm i dont know but i have troubles only with Characters models and textures, objects models works fine and also textures continue with troubles... only to understand this think, i follow this steps.

1.- I drag the characters.dat (Meshes) to ALCryptDecryptINI.exe

2.- I use this quickbms script to unpack the files in character.dat (230MB Size File)

```
#Archlord PC
#from chrrox

open FDSE Data.Dat 0
open FDSE Reference.Dat 1


get files long 1
get foldersz long 1
get folder string 1
string folder + \
for i = 0 < files
    set name folder
    get NAMESIZE long 1
    getdstring name1 NAMESIZE 1
    string name + name1
    get offset long 1
    get size long 1
        log name offset size
next i

```


3.- I download and put in MAX the file 
Archlord3.rar (the maxscript file inside of this .rar its Archlord2 name)

4.- After of this i import the files in max but i have error. Tested in max 9 and max 10.

FOR TEXTURES I TRY THIS 2 WAYS

1.- I drag the texture .DAT file to ALCryptDecryptINI.exe

2.- I use this QuickBMS script to extract the DDS files from DAT.

```
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
get dxt long
get height short
get width short
get null byte
get mips byte
putVarChr MEMORY_FILE 0xC width long
putVarChr MEMORY_FILE 0x10 height long
putVarChr MEMORY_FILE 0x54 dxt long
get size asize
math size - 0x90
get name basename
string name + .dds
append
log MEMORY_FILE 0x90 size
append
math size + 0x80
log name 0 SIZE MEMORY_FILE
```


After of this i get a single 200MB DDS file.

The other way i try with textures its not drag the files to ALCryptDecryptINI.exe But a the least i have the same 200MB DDS file.

Something Idea or correction are welcome.
## Post #20
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-24T21:55:35+00:00
- Post Title: Re: Archlord Game File Format

dont do that for meshes.
1.- I drag the characters.dat (Meshes) to ALCryptDecryptINI.exe
this is wrong
## Post #21
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-24T23:19:23+00:00
- Post Title: Re: Archlord Game File Format

> Reply from chrrox
>
> quickbms script to extract these.
make sure you use the ini decryptor first.
Code: Select all#quickbms script
#Archlord PC
#from chrrox

open FDSE Data.Dat 0
open FDSE Reference.Dat 1


get files long 1
get foldersz long 1
get folder string 1
string folder + \
for i = 0 < files
    set name folder
    get NAMESIZE long 1
    getdstring name1 NAMESIZE 1
    string name + name1
    get offset long 1
    get size long 1
        log name offset size
next i

Ok bro i lost here, how to use the ini decryptor first? Its only for textures right?.
Also i try the same with Textures with ini and withouth ini but this its rare also i have the same error of criticalerror on this post

[viewtopic.php?f=16&t=6393](http://forum.xentax.com/viewtopic.php?f=16&t=6393)

the texture found its 1 in 0 seconds and the file generated its a big .DDS.
maybe its the QUICKBMS version, i search QUICKBMS latest version but i found a lot of trash in the net, if anyone can post here the latest version of quickbms this can be usefull.
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-24T23:58:54+00:00
- Post Title: Re: Archlord Game File Format

Step1

Only decrypt the reference files that is it nothing else.........



After the textures are extracted you must run the ini decryptor On the small texture files only.
Also you must use the key command with it.
The key to use on ONLY the textures is asdfqwer
## Post #23
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-25T16:30:09+00:00
- Post Title: Re: Archlord Game File Format

> Reply from chrrox
>
> Step1

Only decrypt the reference files that is it nothing else.........



After the textures are extracted you must run the ini decryptor On the small texture files only.
Also you must use the key command with it.
The key to use on ONLY the textures is asdfqwer

Thanks chroxxx, all works perfect now man, its posible maybe extract the HQ textures? the small are very bad and smooth with lowres, its imposible make renders with this   .
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-25T17:32:29+00:00
- Post Title: Re: Archlord Game File Format

those are the only textures
## Post #25
- Username: jin76
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 06, 2010 12:31 am
- Post datetime: 2011-06-26T17:04:47+00:00
- Post Title: Re: Archlord Game File Format

WOW AWESOME progress guys     

I was able to extract the textures using Archlord Data Editor
but is there a way to attach the animations and the textures to the models and 
what format should the texture be inorder for max to auto detect them

thanks in advance
## Post #26
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-27T17:42:19+00:00
- Post Title: Re: Archlord Game File Format

> Reply from chrrox
>
> Step1

Only decrypt the reference files that is it nothing else.........



After the textures are extracted you must run the ini decryptor On the small texture files only.
Also you must use the key command with it.
The key to use on ONLY the textures is asdfqwer

I try this comand lines in the DOS window, 
D:/Textures/ALCryptDecryptINI.exe reference.dat asdfqwer
D:/Textures/ALCryptDecryptINI.exe asdfqwer reference.dat
But i fail to extract the textures with this comand lines, wath comand line you use to extract man? Thanks.
## Post #27
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-27T18:17:06+00:00
- Post Title: Re: Archlord Game File Format

just drag the reference.dat onto the decryptor no need for a key.
## Post #28
- Username: jin76
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 06, 2010 12:31 am
- Post datetime: 2011-06-30T00:29:38+00:00
- Post Title: Re: Archlord Game File Format

Is there a way to  automatically attach the texture and animations to the models.
## Post #29
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-06-30T00:57:46+00:00
- Post Title: Re: Archlord Game File Format

> Reply from jin76
>
> Is there a way to  automatically attach the texture and animations to the models.

Forget animations, only textures its a head pain, cause the name of the meshes its like this:

0646a00

and texture name its like this

963258

and the total of textures extracted its around 4000 or something.

its a true problem found wath textures are for the meshes.
## Post #30
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-12T16:42:12+00:00
- Post Title: Re: Archlord Game File Format

Well i found this interesting in the .ecl files (3D format), the file already have the name of the textures necesary for each file, the true problem its in something point the extractor or the plugin of chroxxx flat all the objects, here a sample of one file with multiple textures but flated objects group.


This its curious, here the model have 2 objects, one its the armor body flated all, but the weapons its not flated, maybe this can help to understand how to fix the flated parts.
## Post #31
- Username: wangdin1982
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 06, 2011 2:45 am
- Post datetime: 2011-10-07T19:30:01+00:00
- Post Title: Re: Archlord Game File Format

asdfasdfasdfasdfasfasfasdf
## Post #32
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-12-02T11:46:04+00:00
- Post Title: Re: Archlord Game File Format

I tried to download the new Archlord Global client. The quickBMS of chrox not work anymore.
Any news to decrypt the .dat file ?
## Post #33
- Username: angels85
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 07, 2011 6:22 am
- Post datetime: 2011-12-20T02:17:35+00:00
- Post Title: Re: Archlord Game File Format

> I use this quickbms script to unpack the files in character.dat (230MB Size File)

Sorry, Could you explain me how i do to create this "quickbsm file" ? pls
## Post #34
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-12-20T10:08:05+00:00
- Post Title: Re: Archlord Game File Format

you just save the code in notepad as blah.txt and open with quickbms
## Post #35
- Username: raziel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 15, 2012 2:46 am
- Post datetime: 2012-07-14T19:07:23+00:00
- Post Title: Re: Archlord Game File Format

Anyone can upload the files from megaupload to another place?

These links are dead.

Thanks in advance.
## Post #36
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2013-02-12T12:38:16+00:00
- Post Title: Re: Archlord Game File Format

Can anyone help me to unpack DAT files?
I've tried with bms but i got this error

[http://i46.tinypic.com/34pm0as.png](http://i46.tinypic.com/34pm0as.png)
## Post #37
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2013-02-15T18:46:14+00:00
- Post Title: Re: Archlord Game File Format

Can anyone give me the client of the dead link? plz
## Post #38
- Username: Feldunost
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 18, 2011 2:58 am
- Post datetime: 2014-11-21T22:36:45+00:00
- Post Title: Re: Archlord Game File Format

Hello everyone,

I'm in need to advance on that subject, because the server side has been reworked entirely and i'm stuck on graphical import. 
The issue i have is about animations that are based on Renderware and some others files that have .dff files packed in a .dat (different script to be used)[/b].


Indeed i can see IK points to keep the consistency of a 3D model, however i can't find how to use the animation .ean to make that model moving.
I think it's about import, since the extension is based on Renderware software and i currently don't really know how to use, since Renderware's files seems to be hard to convert ?

Some files are packed with several .dff files and we would like to be able to use them, can someone do a QuickBMS script for thoses ?


Can someone help with some wisdom ? 
I'm willing to make an entire community happy with a real server.
## Post #39
- Username: Feldunost
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 18, 2011 2:58 am
- Post datetime: 2014-11-26T14:04:29+00:00
- Post Title: Re: Archlord Game File Format

UP Someone ?
## Post #40
- Username: darkness89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 27, 2011 4:07 am
- Post datetime: 2016-06-15T00:53:19+00:00
- Post Title: Re: Archlord Game File Format

Any chance someone could take a look at animation files again? Those are .ean files which are actually dummy renderware files with the animations inside.

No clue what file format those are in, I don't have any idea where to start...



Any help would be much appreciated! The 3dsMax importer from Chroxx helped a lot already, it would be nice though to have the 100% correct animations as well though.
## Post #41
- Username: bjorn130
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 16, 2018 5:56 pm
- Post datetime: 2020-04-20T14:04:41+00:00
- Post Title: Re: Archlord Game File Format

Hi,

Would it be possible for someone to look into this again? i'm looking for the models with the animations for messing around with them in Unity.

Regards,
bjorn130
