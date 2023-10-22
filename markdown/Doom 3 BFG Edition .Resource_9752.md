## Post #1
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-10-17T02:31:26+00:00
- Post Title: Doom 3 BFG Edition .Resource

Resource files contain a file table at the end of the archive. A BMS script or unpacker would be fantastic 

Taken from my own purchased Xbox 360 copy of Doom 3: BFG Edition.

Send me an e-mail if you would like to have a look at it.

[brendan_1_9@hotmail.com](mailto:brendan_1_9@hotmail.com)

EDIT: The developer's console for the PC version of Doom 3 BFG Edition can extract the resource files from both the PC and Xbox 360 versions of the game. You have to add the following to the command line in the launch option in order to get access to the developer's console:

```
+seta com_allowconsole 1
```

Run the game and then press the '~' key to display the console. Type the following into the developer's console to extract the .resources files.

```
extractResourceFile <resource file> <outpath> <copysound>
```

The <copysound> isn't necessary to extract the files. The <outpath> is necessary and it will create a folder in the root directory of where the game is installed.
## Post #2
- Username: doomed
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 09, 2010 7:55 am
- Post datetime: 2012-10-17T08:28:05+00:00
- Post Title: Doom 3 BFG Edition .Resource

You can unpack them with the included console command "extractResourceFile"

Just type eg: extractResourceFile maps/admin.resources base/maps/admin

What we need is someone to make a "repacker" and to figure out the new ".bimage" texture format!

edit: [viewtopic.php?f=18&t=7499](http://forum.xentax.com/viewtopic.php?f=18&t=7499)

Someone needs to get to it ASAP!!
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-17T11:59:42+00:00
- Post Title: Doom 3 BFG Edition .Resource

Here script for unpack.

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

endian big

idstring "\xD0\x00\x00\x0D"
get TABLEOFFSET long
goto TABLEOFFSET
get FILES long

for i = 0 < FILES
    get NSIZE long
    reverselong NSIZE
    getdstring NAME NSIZE
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
## Post #4
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2012-10-18T13:49:17+00:00
- Post Title: Doom 3 BFG Edition .Resource

Thanks Ekey for script, but console command have same function like BMS script which you posted.
Yep and one thing, you are a Trainer maker?
## Post #5
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-10-26T14:29:07+00:00
- Post Title: Doom 3 BFG Edition .Resource

> Reply from GRiNDERKILLER
>
> Thanks Ekey for script, but console command have same function like BMS script which you posted.
And besides that it tells you how to repack such a recourcefile...
## Post #6
- Username: jonwil
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 05, 2011 5:58 pm
- Post datetime: 2012-10-28T02:43:38+00:00
- Post Title: Doom 3 BFG Edition .Resource

Just a heads up for anyone working on Doom 3 BFG, ID Software will be releasing source code for it in the near future per this
[https://twitter.com/ID_AA_Carmack/statu ... 1369502720](https://twitter.com/ID_AA_Carmack/status/259369191369502720)
