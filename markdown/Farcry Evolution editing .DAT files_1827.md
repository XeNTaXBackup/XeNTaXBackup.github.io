## Post #1
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2006-04-12T02:28:11+00:00
- Post Title: Farcry Evolution editing .DAT files

I'm pretty noobish when it comes to modding but me and a group of noob modders are anxious to start hacking away at the new game farcry evolution, I searched the forums and noticed about 2 threads asking to add support for this game in the editor

could you guys add support for farcry evolution .DAT files, which i believe are the same as teh first game's Farcry Instincts .DAT files

interested in editing and the weaponspack.DAT and stock map files which are .DAT and .FAT files

for Farcry Instincts Evolution for XBOX

these are some sample files i've uploaded each .DAT is accompanied by a .FAT file which is about half the size of the dat file

[http://www.files.bz/files/2563/weaponpack.dat](http://www.files.bz/files/2563/weaponpack.dat)
[http://www.files.bz/files/2563/weaponpack.fat](http://www.files.bz/files/2563/weaponpack.fat)

thanks in advance

p.s. i'm not a cheater
## Post #2
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2006-04-15T18:15:29+00:00
- Post Title: Farcry Evolution editing .DAT files

i have a lot of views and still no reply, the Farcry Series are becoming more popular than halo

Farcry Evolution servers in Xlink Kai boast more than 80 + users and more than 10 private arenas daily

this is an awesome fps
we would like to add new objects and templates to the map editor
upgrade and improve the weapons, with skins/projectiles


a program like multi-ex can make this all happen as all we can view in hex editors are a couple hex strings, extracting that data would be awesome!

could someone please add support for this game, i even uploaded some sample files -------thanks
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-15T20:48:59+00:00
- Post Title: Farcry Evolution editing .DAT files

A quick look at the DAT file. it seems that it contains DXT textures,
but without any kind of DXT headers.

if this is of any use....

so at the moment, even if you should be able to extract the textures
you would need a converter to view and edit them. but thats
another story. first we need an extractor.

i guess you wanted to extract the textures? ...
## Post #4
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2006-04-16T09:22:51+00:00
- Post Title: Farcry Evolution editing .DAT files

firsty of all strobe you rock! , thanks for replying 

okay tell me more about this extracting textures, I have no clue what DXT textures are but would like to know

I really wanted to mod weapons/ change projectiles let me post you some more files from user created custom maps from the game

here is my hunches on the game:
1. either weapons are located in a single file like weaponspack.DAT
2. or I can mod a customm map file where a weapons is simply coded or called on, which it too may contain its own weapons in the custom map

this is a sample custom map
[http://www.files.bz/files/2563/custom_map.zip](http://www.files.bz/files/2563/custom_map.zip)



if you want to meet up on msn i can give you my msn via PM
## Post #5
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-20T02:06:55+00:00
- Post Title: Farcry Evolution editing .DAT files

Reading only Fat Files will / should  allow texture manipulation.

Open .Fat to read .dat file

.Fat Archive:
[4] - ID (DAT2)
[4] - Int32 - Number of Files

Number of Files Loop (12 bytes a entry)
[4] - Offset: In .Dat
[4] - File Size
[4] - ID/Hash?

There looks to be a few offsets in .Dat file but haven't worked out a system. ((well to match up correctly) See first few bytes) until 0x70

For Textures:

Texture Start 
[4] - Unknown   (00010403) seems to initiate all textures?
[4] Dimension x
[4] Dimension y
[4] Image Size in Bytes
[4] Type?  0x12 (18 ) = DXT3  / 0x10 (16) = DXT1 (All this is guess work based on math :p )
[4] Mip Maps
[4] Alpha?
[4] ?
[4] ?
## Post #6
- Username: jeoffry
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 09, 2006 7:38 am
- Post datetime: 2006-05-08T23:47:11+00:00
- Post Title: Farcry Evolution editing .DAT files

Hey,  

I too would like to modify the game in a couple of areas.....

There seems to be a glitch where user created maps allow you to adjust the ambient sounds,  however,  this only works for the person hosting.  All other people joining a system link game will be stuck with the default ambient sound levels.  (Which are FAR TOO LOUD & OBNOXIOUS, especially when listening over stereo with digital sound.)  I would like to completely remove these sounds so I wont have to hear them EVER!!!!  

Also,  it would be awesome to be able to replace objects with custom objects.   

Advance thanks to anyone who might be able to help point us in the right direction to help make this AWESOME game even better!!!!

Till my next post,
FRYd
## Post #7
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2006-07-18T02:49:28+00:00
- Post Title: Farcry Evolution editing .DAT files

hey back after a long time, and yes i'm still a sucker for farcry
but i need help again in a slightly different manner

in farcry evolution there is a map editor on which people make many maps
however you have the option to sign onto xbox live before you make the map, and then when u publish the map, that map is accesible on xbox live, system link , and split screen

THEN, if you choose NOT to sign in on xbox live (maybe you don't have an account at the time), once your map is published it can only be accesible in system link (xlink kai), or split screen gameplay, and NOT ON XBOX LIVE

what i want to do is somehow hack a system link map via hex editor or other tools (wink wink xentax please) to make the map xbox live accesible

i have ran a number of tests and experiments by simply dragging and dropping the map into the appropiate xbox live tdata sections, but the maps are unrecoqnizable unless they have xbox live signatures, i realize that xbox live signatures are near impossible or extremely hard to replicate (cough cough mimesis and dlc homebrew content), thats not the route i want to go, i'd rather just open up let's say a .dat file (the largest of 4 files that make up a map in farcry) and in the .dat file somehow distinguish between the xbox live signatures (maybe an md5) and then the actual map data, such as textures.. and etc..

if i can distinguish between the sigs in the file and the map data itself, then i can simply copy and paste the map data of a system link only map and replace the map data of the xbox live compatible map, keeping the sigs in place

i realize if any of this is going to happen the sig must be MY sig, not someone's else's since, the xbox live sig is unique to u, ur eeprroom, serial, and other unknown things

that's not a problem at all i have xbox live now, and have several xbox live maps, with my signatures from xbox live ready to experiment with

can anyone help me with this venture? I'm not very skilled in reading hex, only little is converted in ascii, and the rest is in hex which i can't read or understand

i will link to map files for you to play around with
samplemaps:
[http://allaboutgames.org/fanmail/samplemaps.rar](http://allaboutgames.org/fanmail/samplemaps.rar)


on the list of important games to hack farcry is up there with halo 2, so i beg of you for assistance
## Post #8
- Username: deadlydata
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 02, 2006 7:48 am
- Post datetime: 2006-08-01T23:52:27+00:00
- Post Title: Farcry Evolution editing .DAT files

This game is truley easily modfied but only on stock maps why beacuse stock maps don't have sig's where the multiplayer custom maps do this is beacuse it compares your maps sig to the other persons for purposes of downloading well it also disables you from being able to modfiy the map so I did some checking around and we found out the checks for this is written in the defualt.xbe so here is a defualt.xbe for you guys to look at it's what checks the maps.dat and .fat and .fat.sig along with .dat.sig so I dunno if it helps but I've tried hexing it already and All I can do with it is make all my maps say their damaged same thing if you modfiy a map the games says it's damaged when you do the mod to a stock map the same mod it works fine so Just seeing if any of you can help us null out the sig checking...

[http://www.zack6924-underground.net/farcry/default.rar](http://www.zack6924-underground.net/farcry/default.rar)

A lil update on this for Dsaba

This game is not like halo2 the porjectiles and stuff are not set inside the map the only thing set are graphics and postions for spawns weapons ect. to mod the properties of somthing it's contained inside lua scripts Even then you would have to make your own resinger for the custom map so It doesn't veiw it as damaged I have came up with a way to remove the check my self all though I'd like a resinger.

Heres a vid of what I've been able to do in the game so far...
[http://youtube.com/watch?v=w1gZ6PV9hIs](http://youtube.com/watch?v=w1gZ6PV9hIs)
## Post #9
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2006-10-04T13:23:35+00:00
- Post Title: Farcry Evolution editing .DAT files

xentax support for extracting .dat archives for farcry for xbox, please?
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-13T19:47:29+00:00
- Post Title: Farcry Evolution editing .DAT files

Allright, with this little piece of MexScript you are able to extract from those dat files. Just use it on a DAT file, but make sure the FAT file with the same name is also in the same directory. 

```
GetDString MW 4 1 ;
Get FN Long 1 ;
For T = 1 To FN ;
Get Off Long 1 ;
Get Size Long 1 ;
Get Hash Long 1 ;
Log "" Off Size 0 0 ;
Next T ;
```


Get the zipped txt file and use Run MexScript on..., then select the txt file and then select the dat file.
[dat.zip](https://xentaxbackup.github.io/file/914_dat.zip)
## Post #11
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2006-10-16T20:46:15+00:00
- Post Title: Farcry Evolution editing .DAT files

thanks mr. mouse! been about a year now for someone to reply to this post, i forgot about it actually and had moved on, but nevertheless appreicate the work you've done for it, i was talking with watto with watto.org and his game extractor, he developed a farcry plugin to extract these dat2 files, only problem is, is that u can succesfully extract over 1000 files from lets say weaponpak.dat, but all the files are missing extensions and its almost impossible to figure out what file is what, whether its an animation, a bitmap, a sound, whatever

the headers of hex dont tell u much either

so u can check it out here
[http://allaboutgames.org/fanmail](http://allaboutgames.org/fanmail)
download extracter.exe and farcryplugins.zip

thats watto's prog, only reason i'm telling u this is that maybe both of u can put ur heads together and figure out how to decrypt the filenames and the file locations within the archive, which is extremely important

i'll def. check out the mexcom script though
## Post #12
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2006-10-17T00:03:37+00:00
- Post Title: Farcry Evolution editing .DAT files

oh i can't try out the mex script mr. mouse, because i have the free version of multi-ex, i would love to buy it but i need to know for sure it can do what i want it to do, and that is to succesfully extract .dat archives for farcry, and in order to test that i can't do that


u see my predicament, shame i can't try out the work u've done mouse
## Post #13
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-10-21T20:19:25+00:00
- Post Title: Farcry Evolution editing .DAT files

> Reply from sababa
>
> thanks mr. mouse! been about a year now for someone to reply to this post, i forgot about it actually and had moved on, but nevertheless appreicate the work you've done for it, i was talking with watto with watto.org and his game extractor, he developed a farcry plugin to extract these dat2 files, only problem is, is that u can succesfully extract over 1000 files from lets say weaponpak.dat, but all the files are missing extensions and its almost impossible to figure out what file is what, whether its an animation, a bitmap, a sound, whatever

the headers of hex dont tell u much either

so u can check it out here
http://allaboutgames.org/fanmail
download extracter.exe and farcryplugins.zip

thats watto's prog, only reason i'm telling u this is that maybe both of u can put ur heads together and figure out how to decrypt the filenames and the file locations within the archive, which is extremely important

i'll def. check out the mexcom script though

That link is broken. I have this game finally. I did a few hours of work on it. You don't have filenames because they are hashed as I spec'd above. The map files do show 85% of the names and the CRC's. I dumped them and built a definition file to lookup in the .fat files for names. I didn't figure out how to calculate the value yet...

<File Name="objects_xbox\island_7_shanty\_vegetation\vegetationalpha_df.xbt" CRC="343072680" Type="1" />

I cannot get value 343072680 for the life of me. I tried Upper Case, CRC 32 and a bunch of Custom 32's 1s & 2s complements. Maybe I'm missing something  

:Edit Nevermind, I figured it out. The name was not an exact value. The correct way to CRC the string to get the value is \objects_xbox\island_7_shanty\_vegetation\vegetationalpha_df.xbt  and it is a standard CRC
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-21T21:36:52+00:00
- Post Title: Farcry Evolution editing .DAT files

With standard you mean crc32? May we peek at the def file of yours?
## Post #15
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-10-25T21:32:55+00:00
- Post Title: Farcry Evolution editing .DAT files

> Reply from Mr.Mouse
>
> With standard you mean crc32? May we peek at the def file of yours?

Yeah it is just a regular crc32. The def file is still missing a few matches. I need to brute force the rest from paths within the xbe and then filter out the un-needed ones. The entries from just maps is around 9000 unique matches. I know most are not being used :\
## Post #16
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2006-10-25T23:53:57+00:00
- Post Title: 

yeah sorry my former webserver was a target of a hackers and now everything is deleted, i'm working on getting a new link working again

for now you can pm me to get my msn, and i can send u the prog to extract the archives
## Post #17
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2007-09-21T01:01:23+00:00
- Post Title: 

Hi its been a very long time, but I'm still intersted in getting full support for this game in xentax, I'm reading the guide to file explorations but it is very hard for me to just pick up this up... however, i'm trying

some things that may help you complete it:
1. watto with gamextractor made a special plugin, but it has some bugs and is not very useful (its not complete)
2. silver made a def file of some sort, see earlier post

for #1 I can supply this plugin which is not avail on watto's site, (he made this almost a year ago special for me)
DOWNLOAD:
[http://tzfiles.com/users/hello123/fc_plugins.zip](http://tzfiles.com/users/hello123/fc_plugins.zip)

for #2 I have never seen this def file, I would like too, I PMed Silver, but it seemed has dissapeared since it was about a year ago since he made this post, if anyone has this or knows how to contact Silver or get this def file I'd love to see and try to work from there

Mr. Mouse I have never tried your MexCom script, u mark this game as complete
I can't try your mexcom script b/c I have to pay for the full version of multiex in order to use mexcom scripts, I would only pay for it if u have full support for this game, yet I cannot test what you've done to see if it is supported or simply a beta whatever... You see the predicament I am in

-please reply to these concerns, and thank you for your interest and hard work, may I remind you I have been patient and this topic has existed for over a year while other games have been fully supported and completed in less than that time

*EDIT: I can supply sample .dat files to experiment with as well, just let me know.
## Post #18
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-09-21T05:17:43+00:00
- Post Title: 

I don't know what happened to my def list it has been forever! I looked around for a bit and found my small def file. This is not complete! I do not know what happened to my other work.


This file is worthless really without something that uses it. The filenames were chopped in this def list. See my previous post about long directory filenames. I used only the file + ext as a name and rid of the path in this definition file. It is a binary file so you need to read it like this:

[CRC] [String Length] [String]
4 Bytes for the CRC
1 Byte for the String Length
String

I do not remember if these were filtered (dupes, matches) etc. I just saw the file. Again the CRC's will not line up to the string because the paths were eliminated to save space. I do not know where the source files are. If the hash ID's matched any in this file the goal was to display the string associated with it. Good Luck
[DefList.zip](https://xentaxbackup.github.io/file/1340_DefList.zip)
## Post #19
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2007-09-21T23:00:28+00:00
- Post Title: 

AWESOME SILVER! glad to see you are still around 

I know a lot more than I used to before, but I still don't know everything.  
Could you explain these things to me?
1. the CRC (wiki) says its a way to sign files with a code.. bal bla bla, what  is it really pertaining to the crc's found in the .DAT file ? Do you have to decrypt the CRC like a md5 hash? (which is not decryptable) What is the relevance of the crc in the .dat file period? How will it help me unpack the archive?
2. I looked at the file in notepad, and i looked at some other files as well, the state that it is currently in is binary right? I know php, so i can convert the strings to hex, ascii or whatever.. What kind of string manipulation/searching would I need to do to? bin 2 hex? and then look for what?

3. you say its a binary file so read it like this... you mean with some kind of program/script?? or just with the naked eye? I can write something in php to "look" in the file, but explain a little mroe what you mean by
[CRC] [String Length] [String] 
4 Bytes for the CRC 
1 Byte for the String Length 
String 


Another thing I don't understand is, yes I've looked through the files myself, I see ascii strings of the locations of files like "/weapon/flamthrower.xbt".. but why is this important at all in extracting the actual files from the archive? for all we know it is simply a line of code in a particular file, sure we can tell that there are definetely refernces to files in the archive, but how the hell to unpack them? how do these strings/locations help in any way?


4. Did you try Mr. Mouse's mexcom script? I never could because I didn't pay for multiex, what does it do anyways... ? can anyone who has the registered version of multiex try it and tell me?

5. Did you try watto's plugins for the .DAT files in gameExtractor, (i linked to the package in my earlier post which inclues the exe executable for gamextractor as well as the plugins and other useful text files) Does this help you in any way?



-thank you
## Post #20
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-09-22T01:40:52+00:00
- Post Title: 

Extracting from these files is god-awful easy.

Notice this is in the completed section because it is done. The archive specs are complete. I'm saying that to use the data you need to know what it is. That is the next step you can either seperate it into 4 categories by looking at header data and guessing what the file is. Or you can go all out and go for the names and extensions.

1. CRC is how they named their files. You need to follow past instructions to get the rest of them.

2. Notepad is not for editing these files. Get a hex editor.

3. My file is setup the way I said it was. A simple loop will read it.

What good are files without names? This is important to know. flamethrower.xbt is a lot better than "file 1". You know it is a DDS texture (xbt) and it pertains flamethrower. The path is crucial because they CRC'd the string with the path included.

4. No I have not. I write demo tools and keep them to myself.

5. See 4:

If you know PHP you can simply write something in php to extract.

I haven't even looked at the files but this should still hold true or close to it. 
> Open .Fat to read .dat file 
>
> 
>
> .Fat Archive: 
>
> [4] - ID (DAT2) 
>
> [4] - Int32 - Number of Files 
>
> 
>
> Number of Files Loop (12 bytes a entry) 
>
> [4] - Offset: In .Dat 
>
> [4] - File Size 
>
> [4] - ID/Hash?
The ID/Hash? is the CRC that is discussed in later posts.
## Post #21
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2007-09-22T06:15:34+00:00
- Post Title: 

...
## Post #22
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2007-09-22T18:28:28+00:00
- Post Title: 

obsolete...
## Post #23
- Username: sababa
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 12, 2006 10:23 am
- Post datetime: 2007-09-24T13:49:57+00:00
- Post Title: 

...
