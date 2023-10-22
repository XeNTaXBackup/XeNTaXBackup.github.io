## Post #1
- Username: ravage
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-05T15:40:20+00:00
- Post Title: Rise of Immortals

Here is a 3ds max import script for these models.
Characters are supported with bones and weights
static objects are just imported i did not assign bones to them.
[http://www.riseofimmortals.com/](http://www.riseofimmortals.com/)

and the 2 bms scripts
Run this first

```
get unk01 long
get totalheader long
get namecount long
get files long
get infoOff long
savepos nstart
math infoOff + nstart

for i = 0 < files
get nsize short
getdstring name nsize
putarray 0 i name
next i

goto infoOff
for i = 0 < files
get unk01 long
get unk02 short
get id long
get size long
get offset long
get nameid short
getarray NAME 0 nameid
log name offset size
next i

```

Then run this second on the model files

```
get ext EXTENSION
string name + ".ext."
string name + ext
goto 0x10
get zsize long
set size zsize
math size * 10
comtype zlib_noerror
clog name 0x24 zsize size

```


To have textures auto applied extract the model and texture archive to the same destination then replace the compressed models with the uncompressed ones.
[Rise Of Immortals.rar](https://xentaxbackup.github.io/file/4689_Rise Of Immortals.rar)
## Post #2
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-09-05T21:40:58+00:00
- Post Title: Rise of Immortals

I run sript 1 and appear files .ALO and .ALA in the folder and now? What i have do? Run script 2 for what files?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-05T21:48:50+00:00
- Post Title: Rise of Immortals

Next run the 2nd script on the alo files.
you can run them on all of them at once with this command

quickbms.exe -f "*.ALO" c:\file.bms c:\model-folder c:\model-folder-new

but remember after you get the files with the .ext.alo extention you will want them in the original model folder so the textures can be auto applied correctly
## Post #4
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-09-05T22:08:29+00:00
- Post Title: Rise of Immortals

.ALO inside folder ATTACHEMENTS? or out but inside folder models.???
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-05T22:12:14+00:00
- Post Title: Rise of Immortals

just run it on the folder 
DATA\ART\MODELS\
it will extract the models folder and any folder under it.
then put it in a new folder like
DATA\ART\MODEL2\
if you want it to auto apply textures with the correct path you have 2 choices

1. place the new extracted model files into
DATA\ART\MODELS
or
2 place them in a new folder with the same name length like
DATA\ART\MODEL2
## Post #6
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-09-05T22:25:52+00:00
- Post Title: Rise of Immortals

Thanks for reply so fast!

.ALA is animation? can i delete .ALA?
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-05T22:37:31+00:00
- Post Title: Rise of Immortals

yes those are animation files delete them if you want.
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-06T12:13:19+00:00
- Post Title: Rise of Immortals

well thanks a lot for great news, the game have good models, really good the only problem is need select 1 per 1 alo files to make readable in your script
## Post #9
- Username: angels85
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 07, 2011 6:22 am
- Post datetime: 2011-12-06T22:58:42+00:00
- Post Title: Rise of Immortals

Sorry can you help me?

I open 3ds max 2012 32 bit (windows xp), when it finish to loading i go to ----> MAX Script ---> Run Script ---> Rise of Immortals2.ms 



I select the file to open and 3ds Max does not open anything!!! why? o.O

What should I do? Can explain the steps? Please   

Respond me pls
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-07T00:02:28+00:00
- Post Title: Rise of Immortals

you need to extract the alo files first.
## Post #11
- Username: angels85
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 07, 2011 6:22 am
- Post datetime: 2011-12-07T16:52:46+00:00
- Post Title: Rise of Immortals

i have all package models decrypted(a package with .alo and .ala files).... i used Mega File editor to extract file....

3ds max doesn't import the model <.<

Can you help me?

Sorry for my English =/
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-07T18:04:21+00:00
- Post Title: Rise of Immortals

Follow the instuctions in the top of this thread.
run the 2 bms scripts.

or if you want to do it the easy way
use noesis
[viewtopic.php?f=29&t=7813](http://forum.xentax.com/viewtopic.php?f=29&t=7813)
## Post #13
- Username: angels85
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 07, 2011 6:22 am
- Post datetime: 2011-12-19T02:55:47+00:00
- Post Title: Rise of Immortals

it doesn't work!!! =(

Could you add me on skype for help:

ale.rozzi               

(IT) italian...

TNHKS =)
## Post #14
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2012-07-18T01:47:00+00:00
- Post Title: Rise of Immortals

Hi,

Sorry to bump this thread,


but I only want to know if their is a way of restoring the models to their T-pose within max, as they are imported in an action pose?

(I'm just not very familiar with max)

Thanks
## Post #15
- Username: ravage
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 13, 2014 1:39 am
- Post datetime: 2015-08-05T14:31:53+00:00
- Post Title: Rise of Immortals

hi chrrox your script is great! however when i use it to import some ALO models from End of Nations Alpha, the 3DSMAX9 reports:
">> MAXScript FileIn Exception: -- Runtime error: buildTVFaces: mesh has no texture vertices - $Editable_Mesh:Object01 @ [0.000000,0.000000,0.000000] <<". 
the rest models are imported fine.

i uploaded some of these alo file, will you check them? thanks a lot!
[EON_ALO.zip](https://xentaxbackup.github.io/file/9485_EON_ALO.zip)
