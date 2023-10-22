## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-12T02:49:23+00:00
- Post Title: Dragon Oath axp

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-12T21:49:09+00:00
- Post Title: Dragon Oath axp

Sorry, I just noticed this now.
This txt gives the filesizes for every file that comes with the client. The client probably uses this to determine how to load the files whenever a new patch comes around.

The first field is the name, the second field is the filesize, don't know about 3rd field, and the 4th field is which package it is in (if it is in one)

Hopefully this will help.
It seems like an extractor will have to read from this file and then go to the corresponding package to get the data out. I'm not sure if it's stored sequentially.

I added up the filesizes and then compared it with the corresponding axp file, but there was quite a difference, so I'm guessing there's padding in the axp.

EDIT: there's some sort of (list) entry at the end of each package, but it's just the same information you see in this file....although there seems to be some difference.

EDIT2: Ok, so I looked at the "Effect" archive since it only has 3 files and they are stored sequentially, but there doesn't seem to be any indication where each file starts even though there's only 3. There is a string of null bytes between each file, but there's no consistency there. Maybe there is offset information somewhere?
[(version).7z](https://xentaxbackup.github.io/file/4479_(version).7z)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T14:32:44+00:00
- Post Title: Dragon Oath axp

Ok after looking at some bms scripts I have figured out some things and decided to try this archive out since it is a simple archive with no encryption or compression.

```

get idstring long
get unk1 long
get null long
get unk2 long
get offsetBlock long #this block gives the offsets and data sizes
get files long #includes the (list) block which holds all filenames and their data size
get unk3 long
get startOffset long #not important, but the data for first file starts here.
get unk4 long
goto offsetBlock
for i = 0 < files
	get offset long
	get size long
	get unk long #always 0x00000008
	log i offset size
next i

```


This currently extracts the data correctly, but you will see that I have substituted the name with the iterator variable.
I know where the names are, but I don't know how to get them.

When you go to startOffset, you will get all of the offsets and data size, but you don't get the name.
The last entry in this block is a pointer to the (list) block that contains all of the names, sizes, and some checksum maybe.

The names are in the order that they are stored in the archive (I think), so one could possibly store all of the offsets and sizes in an array, go to this list offset, then begin looping over each entry, grabbing the name and then getting the data using the information stored in the array.

But I don't know how to do that.

The format for the (list) entry is as follows:

```
numFiles
skip 1 byte

for i = 0 < numFiles
   savepos cur
   find position of next "|" character (0x7C)
   get filename (0x7Cpos - cur - 1 to exclude the pipe)
   skip 1 byte to skip the pipe
   read 8-bytes for data size
   skip 10 bytes
next i

```


EDIT:

Alternatively I guess one could possibly keep a pointer to the offsets and another pointer to the filenames, and then move them both together while parsing files cause we can get the offset of the (list) entry using the number of files and the fact that each offset entry is 12 bytes long (offset, data, unk). This seems easier than storing the data in an array, so I might try this approach.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T15:25:02+00:00
- Post Title: Dragon Oath axp

Ok, so now I've created two pointers and update them at each iteration to get the filenames, offsets, and sizes, and it works. I manually prepended it with the archive name so it'll extract to a folder with the same name as the archive.

Some problems
1: relies on the fact that "/" symbol is used to indicate directory (don't know if it's standard)
2: there are non-ascii names that I don't know how to deal with. You can find some in the config archive and launcherSkin. I don't know what to do with this, and I would like to get the proper names. I don't know the encoding, but it is most likely one of the chinese charsets.

3: I wrote a batch file, but I don't know where the files end up o.O

```
#quickbms script
#by Tsukihime

get idstring long
get unk1 long
get null long
get unk2 long
get offsetBlock long #this block gives the offsets and data sizes
get files long #includes the (list) block which holds all filenames and their data size
get unk3 long
get startOffset long #not important, but the data for first file starts here.
get unk4 long
goto offsetBlock
savepos offsetPtr

get folder basename

#get the (list) offset
math temp = files
math temp -= 1
math temp *= 12
math temp += offsetBlock

goto temp
get listOfs long

#go to the first filename
goto listOfs
goto 9 0 SEEK_CUR
savepos listPtr
findloc newline string "\n"
math newline += 1
goto newline
savepos listPtr
#list pointer is now set

for i = 0 < files

	#======Get offset and size======
	
	goto offsetBlock
	get offset long
	get size long
	get unk long #always 0x0000008
	savepos offsetBlock #remember where we are

	#======Get Filename=============
	#find the pipe character 0x7C
	goto listPtr
	findloc pipeOfs string "|"

	#calculate string length
	math stringlen = pipeOfs
	math stringlen -= listPtr

	#get the string name
	getdstring name stringlen

	#update position of list pointer
	math listPtr = pipeOfs
	math listPtr += 19
	goto listPtr
	
	#========save file===============
	set outName = folder
	string outName += "/"
	string outName += name
  log outName offset size
next i

```


Code looks long and ugly despite my attempts to prettify it. Maybe someone can come up with a different way of doing it that's more efficient?
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T22:50:14+00:00
- Post Title: Dragon Oath axp

Ok, all of the model names are in chinese.
What to do? Lol...I don't know if quickbms can handle non-english words.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-04T19:27:51+00:00
- Post Title: Dragon Oath axp

Ok this script unpacks the archives, but your computer encoding must be set to simplified chinese otherwise the names will be garbled (pretty much everything uses chinese names)

The models are just ogre3D's binary mesh format.
[dragonOathmesh.jpg](https://xentaxbackup.github.io/file/4687_dragonOathmesh.jpg)
## Post #7
- Username: Mippithedork
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 20, 2012 10:47 am
- Post datetime: 2012-02-20T02:54:00+00:00
- Post Title: Dragon Oath axp

I don't want to seem like i'm beating a dead horse here lol, I'm new to bms scripting and all, and i've used the supplied scripts, and i'm having issues with having to rename each file pretty much, even tho i have all eastern languages fully supported on my PC, I'm unable to get the naming to work properly, i get garbled junk and wingding looking symbols. What am i doing wrong? 

I need pretty much all files to be named correctly as they are originally within the pack, also on another note, how to recompile the content correctly again? Like say, the music is in one of these axp packs, the script works, names it right, but to get it to work in the game with new music i need to recompile it, how would i reverse the decompile to get a compiler back to axp again? 

Thanks for your help  This forum site has been really useful so far.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T03:25:53+00:00
- Post Title: Dragon Oath axp

I set system locale to chinese simplified.
Seems like having support for the characters didn't really make a difference.

I don't know if applocale might work in this scenario (run quickbms using applocale lol)

For re-packing...don't know I did a lot of weird stuff with the unpacking as you can see from the script, so I'm not sure if it could be re-packed using the same script.

You can just run the re-import link and select this script and the target archive and see if it works I guess.
## Post #9
- Username: Mippithedork
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 20, 2012 10:47 am
- Post datetime: 2012-02-20T03:28:46+00:00
- Post Title: Dragon Oath axp

ah, ok, so change my locale to chinese, and as for repacking, quickbms has an option for re-importing, ok, i'll give it a wack, i'm gonna try with something easy first, like the music, i got it to decompile correctly, as it didn't have chinese character naming.

I'll post my results of both. Thanks tons!
## Post #10
- Username: Mippithedork
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 20, 2012 10:47 am
- Post datetime: 2012-02-22T01:38:20+00:00
- Post Title: Dragon Oath axp

I've yet to try the change locale thing, but went ahead and tried the reimport option, after reading the readme file it says to click on the reimport shortcut, but problem is, that seems to do nothing, i checked the shortcut target, and it says z:\ and z:\quickbms.exe -r -w. So i figured the z was the issue considering the exe is in a folder on my desktop, went to change it to c: and the correct paths, and all but the short cut isn't the same thing for two reasons: 1. the original reimport shortcut shows as a dos file, and 2. i can't seem to be able to put the -r -w at the end without it giving an error saying path doesn't exist or what not. Any ideas? I think so far i've only ran quickbms as the gui mode, not familiar at all with the command prompt method. Is this my issue? any work arounds? thanks for any advice before hand
