## Post #1
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2012-07-20T15:43:55+00:00
- Post Title: The Dark Knight Rises .gla

Gameloft has used this format for almost all of their mobile games since NOVA, and now it's most notable as an archive in TDKR. The textures and almost everything else are held up in .gla archives I can't seem to extract. I can PM a file sample if needed.

Thanks
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-07-31T02:31:04+00:00
- Post Title: The Dark Knight Rises .gla

I'm interested too anyone?
## Post #3
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-08-03T23:55:04+00:00
- Post Title: The Dark Knight Rises .gla

Agreed. A QuickBMS script to unpack those gla files would be very handy.
## Post #4
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-22T09:42:15+00:00
- Post Title: The Dark Knight Rises .gla

here is a quickbms code I wrote to extract .bdae files from the actors.gla file.

```
get UNK long
get START long
get BDAEOFFSET long
get FILES long
for i = 0 < FILES
get OFFSET long 
get SIZE long
get CURSET long
Math CURSET + BDAEOFFSET
savepos END 
goto CURSET
getdstring NAME 0x32
goto END
get UNK2 long


log NAME OFFSET SIZE
next i
```


the bdae files seem to contain the textures and 3ds max files, they have the header BRES.
## Post #5
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-09-22T11:42:50+00:00
- Post Title: The Dark Knight Rises .gla

> Reply from rman2
>
> here is a quickbms code I wrote to extract .bdae files from the actors.gla file.
Code: Select allendian BIG
get UNK long
get START long
get BDAEOFFSET long
get FILES long
for i = 0 < FILES
get OFFSET long 
get SIZE long
get CURSET long
Math CURSET + BDAEOFFSET
savepos END 
goto CURSET
getdstring NAME 0x32
goto END
get UNK long


log NAME OFFSET SIZE
next i

the bdae files seem to contain the textures and 3ds max files, they have the header BRES.
Excellent work! now how do we unpack those .bdae files
## Post #6
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-22T11:47:06+00:00
- Post Title: The Dark Knight Rises .gla

I'll have a look at it but I'm new to this, this is the first thing I've ever written :s
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-09-22T11:49:21+00:00
- Post Title: The Dark Knight Rises .gla

> Reply from rman2
>
> I'll have a look at it but I'm new to this, this is the first thing I've ever written :s
well its good to have you trying out man! I have been wanting to extract these gameloft game data files since 2010
If you ever need any files Im here to provide them
## Post #8
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-09-22T23:39:58+00:00
- Post Title: The Dark Knight Rises .gla

rman - Great work on the script. It extracts the gla archives perfectly.

I look forward to someone examining the bdae files. Also, the textures are extracted to tga format, but they are not standard tgas and are not recognized by Noesis or any other image editing program I have.
## Post #9
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-09-23T07:11:36+00:00
- Post Title: The Dark Knight Rises .gla

Can anyone try extracting the Modern Combat 3 files?

The Raw unencrypted files from gameloft looks like this



I still have the old unencrypted Modern combat sandstorm .ipa file before they started encrypting them

Gameloft MC3 1003233780.sobfs

.sobfs files can be opend in vlc player

They are just .WAV files but renamed .sobfs
## Post #10
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2012-10-24T01:54:44+00:00
- Post Title: The Dark Knight Rises .gla

I have a GLA extractor on hand with decryption implemented. I just disassembled the NOVA3 code, and it contains better code flow than what I derived from NOVA2, so I'll be tidying up the code a bit.

Note: for DDS files you need The Decompressonator to convert to a standard DDS.
## Post #11
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-10-24T02:16:22+00:00
- Post Title: The Dark Knight Rises .gla

> Reply from GMMan
>
> I have a GLA extractor on hand with decryption implemented. I just disassembled the NOVA3 code, and it contains better code flow than what I derived from NOVA2, so I'll be tidying up the code a bit.

Note: for DDS files you need The Decompressonator to convert to a standard DDS.
Oh great when will you release?
## Post #12
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2012-10-24T22:50:44+00:00
- Post Title: The Dark Knight Rises .gla

I'm done tidying up my code, so it's time for a release. Attached you will find the extractor build, extractor source, and encryption algorithm source. This program is written in C#, with the encryption implemented in C++ because it's easier to deal with arbitrary amounts of bytes and shifting and what not in C++ than C#. Anyway, just drag and drop the .gla file over the extractor executable and it'll extract the files into a folder with the same name as the .gla file with "_extracted" appended to it. In the extractor is an implementation of CCustomPakFileReader, which is the pak reader used in Gameloft games. It's not identical (I'm too lazy to go try to emulate it exactly), but its methods should return more or less what you would expect from the corresponding methods in Gameloft's games. The extractor can be included as a referenced assembly if anyone wants to use it as a reader in their Gameloft game modding program.

A pak writer is not implemented, though a quick test with the ENCODE_XOR32 method seems to produce the correct encrypted files.

Please note there are many types of archives used by Gameloft games. There's one used for their older games (I have a quickly whipped up extractor called GameloftCrapEngineExtract, because the games made with their old engine are crap (Assassin's Creed: Altair's Chronicles, anybody?)), this one, scrambled ZIP (used in Asphalt 6 for audio, can be converted with a quick binary search and replace plus recovering byte patterns that has been mistakenly replaced in the process), and something using a different type of encryption that I haven't gotten to (also with .gla extension). Make sure you stick the right type of file into the extractor, or else it will choke and crash. This particular format is in big endian, 16 bytes of header, and the an array of 16 byte entries. You'll see a lot of zeros in the first kilobyte or so of the file. The last column of 4 bytes for entries is either 0 (no encryption) or 1 (encrypted). All file names are encrypted, but file data may or may not be encrypted. Note this program may not be compatible with .gla files that do not have file names encrypted.

For further study: Vox Native audio (Vox is the sound engine used in Glitch games, and the native format can specify effects, playlists, and segments while storing audio data in a big chunk), and Binary Collada (BDAE) models (tried once, very confusing; will try again with symbols, and hopefully it's easier).

Download: [blog/?p=659](http://forum.xentax.com/blog/?p=659)
## Post #13
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-10-25T02:43:09+00:00
- Post Title: The Dark Knight Rises .gla

> Reply from GMMan
>
> I'm done tidying up my code, so it's time for a release. Attached you will find the extractor build, extractor source, and encryption algorithm source. This program is written in C#, with the encryption implemented in C++ because it's easier to deal with arbitrary amounts of bytes and shifting and what not in C++ than C#. Anyway, just drag and drop the .gla file over the extractor executable and it'll extract the files into a folder with the same name as the .gla file with "_extracted" appended to it. In the extractor is an implementation of CCustomPakFileReader, which is the pak reader used in Gameloft games. It's not identical (I'm too lazy to go try to emulate it exactly), but its methods should return more or less what you would expect from the corresponding methods in Gameloft's games. The extractor can be included as a referenced assembly if anyone wants to use it as a reader in their Gameloft game modding program.

A pak writer is not implemented, though a quick test with the ENCODE_XOR32 method seems to produce the correct encrypted files.

Please note there are many types of archives used by Gameloft games. There's one used for their older games (I have a quickly whipped up extractor called GameloftCrapEngineExtract, because the games made with their old engine are crap (Assassin's Creed: Altair's Chronicles, anybody?)), this one, scrambled ZIP (used in Asphalt 6 for audio, can be converted with a quick binary search and replace plus recovering byte patterns that has been mistakenly replaced in the process), and something using a different type of encryption that I haven't gotten to (also with .gla extension). Make sure you stick the right type of file into the extractor, or else it will choke and crash. This particular format is in big endian, 16 bytes of header, and the an array of 16 byte entries. You'll see a lot of zeros in the first kilobyte or so of the file. The last column of 4 bytes for entries is either 0 (no encryption) or 1 (encrypted). All file names are encrypted, but file data may or may not be encrypted. Note this program may not be compatible with .gla files that do not have file names encrypted.

For further study: Vox Native audio (Vox is the sound engine used in Glitch games, and the native format can specify effects, playlists, and segments while storing audio data in a big chunk), and Binary Collada (BDAE) models (tried once, very confusing; will try again with symbols, and hopefully it's easier).

Note: Pending posting to tools blog. Source code will be available there.
#1     


Thankyou for your efforts man will test this out soon
## Post #14
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-12-17T02:45:34+00:00
- Post Title: The Dark Knight Rises .gla

for Gameloft's Modern Combat 4 i have been playing around with the filetype .sobfs 

currently working on getting them to export out to usable formats
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-12-25T04:26:27+00:00
- Post Title: The Dark Knight Rises .gla

> Reply from GMMan
>
> Download: blog/?p=659i can't extract .gla files from dark knight, it cause me na error about unavaliable path, but i CAN extract .gla from '9mm' game (gameloft game) without any problem, can you help me?
## Post #16
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2012-12-30T07:28:40+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from cra0
>
> for Gameloft's Modern Combat 4 i have been playing around with the filetype .sobfs 

currently working on getting them to export out to usable formats

If the engine used is Glitch, then chances are .vox files are in Vox format. Vox is the audio engine. I used to have a program for deserializing chunks from the format, but lost it in a hard drive crash. I've seen it being the container for IMA ADPCM, regular PCM, and Microsoft ADPCM audio.
## Post #17
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2012-12-30T07:30:06+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from Tosyk
>
> GMMan wrote:Download: blog/?p=659i can't extract .gla files from dark knight, it cause me na error about unavaliable path, but i CAN extract .gla from '9mm' game (gameloft game) without any problem, can you help me?

Upload a sample, and also the .so library file if you're using the Android version (Android versions seem to contain a good amount of symbols).
## Post #18
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-01-16T15:16:50+00:00
- Post Title: Re: The Dark Knight Rises .gla

Hey Gman i can't seem to open .gla files for the textures  mind checking them out


[https://dl.dropbox.com/u/10798900/DUMPB ... ons_tex.7z](https://dl.dropbox.com/u/10798900/DUMPBOX/commons_tex.7z)
[https://dl.dropbox.com/u/10798900/DUMPB ... ms_tex.gla](https://dl.dropbox.com/u/10798900/DUMPBOX/particlesystems_tex.gla)

this comes from the apple version iOS
## Post #19
- Username: Shurtugal
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 04, 2013 1:38 am
- Post datetime: 2013-05-03T23:22:16+00:00
- Post Title: Re: The Dark Knight Rises .gla

Do you have any update for this? I am trying to use it to mod sprites on the Amazing Spider-Man iOS game. But it refuses to work. I have a screen of the error if you need it.
## Post #20
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2013-06-15T20:15:51+00:00
- Post Title: Re: The Dark Knight Rises .gla

does anyone know how to get the .bdae format into 3ds max?? or convert it?
## Post #21
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-06-16T03:33:39+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from reappper
>
> does anyone know how to get the .bdae format into 3ds max?? or convert it?
I looked into that format a while back but couldn't figure out the delta animations it seems to be a modified version of the DAE fbx format 

I did manage to solve some of those sobfs files here is a tool I made a while ago 

[https://dl.dropboxusercontent.com/u/107 ... toolkit.7z](https://dl.dropboxusercontent.com/u/10798900/Software/gameloft_toolkit.7z)
## Post #22
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2013-06-16T22:08:38+00:00
- Post Title: Re: The Dark Knight Rises .gla

thanks its a step closer so its a modified version of the DAE fbx format? ohhh so stupid question how do you study the file format I'm not a big scripter just learning what other program can you study the file format?
## Post #23
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-08-24T06:13:03+00:00
- Post Title: Re: The Dark Knight Rises .gla

K I'm so stupid those .gla files are containers for PVR

Ill reverse them this afternoon
## Post #24
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-08-26T09:12:12+00:00
- Post Title: Re: The Dark Knight Rises .gla

Ok so taking a look at this example which is not even compressed -_-
[https://dl.dropboxusercontent.com/u/107 ... ms_tex.gla](https://dl.dropboxusercontent.com/u/10798900/DUMPBOX/particlesystems_tex.gla)

what I have analyzed so far I plan to do more soon


WIP


-EDIT-
Lol I talked to one of the programmers @ gameloft and he gave me some pretty insightful info
## Post #25
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-08-27T13:06:59+00:00
- Post Title: Re: The Dark Knight Rises .gla

Ok here you guys go first release please test it and get back to me
[Gameloft Archive Tool.7z](https://xentaxbackup.github.io/file/6572_Gameloft Archive Tool.7z)
## Post #26
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-08-28T14:24:19+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from reappper
>
> thanks its a step closer so its a modified version of the DAE fbx format? ohhh so stupid question how do you study the file format I'm not a big scripter just learning what other program can you study the file format?

K up next .bdae (gameloft's binary Collada format)
## Post #27
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-19T15:48:45+00:00
- Post Title: Re: The Dark Knight Rises .gla

Hmm... I was going to try this on a file I took out of Gameloft LIVE! client. The program download's missing from the tools blog, and the attachment crashes on file load.

P.S. Mind PMing me the source code? Looks like it needs a bit of cleanup or something (you should try putting business code in a new class; at least you've got some threading going, which most people forget when writing GUI programs).
## Post #28
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-19T15:53:19+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from GMMan
>
> Hmm... I was going to try this on a file I took out of Gameloft LIVE! client. The program download's missing from the tools blog, and the attachment crashes on file load.

P.S. Mind PMing me the source code? Looks like it needs a bit of cleanup or something (you should try putting business code in a new class; at least you've got some threading going, which most people forget when writing GUI programs).
[http://cra0kalo.com/public/Gameloft%20Archive%20Tool.7z](http://cra0kalo.com/public/Gameloft%20Archive%20Tool.7z)

^ this crashes does it give an error msg an yeah ill pm you
## Post #29
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-19T20:22:07+00:00
- Post Title: Re: The Dark Knight Rises .gla

I'm being so stupid. Apparently there's also little endian CustomPaks being distributed. All I needed to do in my tool was add an option for little endian paks. Download [here](http://forum.xentax.com/blog/?p=1085). Just add "/l" to the options if you know you're extracting a little endian pak.

Ninja update: Just added an option to not decrypt file names. If you see cleartext file names, add "/n" to the arguments.

Other notes: If you are going to post this tool to other forums, please link back to this thread and give attribution. Please and thank you!
## Post #30
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-24T11:10:05+00:00
- Post Title: Re: The Dark Knight Rises .gla

THE GUI updated version

[blog/?p=1061](http://forum.xentax.com/blog/?p=1061)
## Post #31
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-30T15:11:27+00:00
- Post Title: Re: The Dark Knight Rises .gla

k wip BDAE
## Post #32
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-10-01T05:16:31+00:00
- Post Title: Re: The Dark Knight Rises .gla

Looks very promising. I wish you the best of luck
## Post #33
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-05T16:54:24+00:00
- Post Title: Re: The Dark Knight Rises .gla

Still have yet to figure out the UVMAP mesh but at least I got the LOD and mesh objects separate now

-EDIT- 

UV's fixed ty again for the help GMMan
## Post #34
- Username: francoiscoiscois
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 06, 2006 8:02 pm
- Post datetime: 2013-12-29T20:21:45+00:00
- Post Title: Re: The Dark Knight Rises .gla

Hi Cra0

How did you get to import the .bdae into 3DSmax ?
I didnt found any importer script so far ...

Even if it only import LOD I would really like to experiment with it
## Post #35
- Username: theaya
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 19, 2011 7:09 pm
- Post datetime: 2014-03-04T01:02:38+00:00
- Post Title: Re: The Dark Knight Rises .gla

This post is dead?
I hope not.
## Post #36
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-03-08T12:54:13+00:00
- Post Title: Re: The Dark Knight Rises .gla

Same here,.... any chance there is a release of some kind of the script ?

T.
## Post #37
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-03-09T22:54:53+00:00
- Post Title: Re: The Dark Knight Rises .gla

Oh sorry wasn't subscribed to this for some reason yeah ill make a script/tool soon but bare in mind the bdae format changes from game to game.
## Post #38
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2014-04-03T06:46:09+00:00
- Post Title: Re: The Dark Knight Rises .gla

Hey Cra0 can you look into the new gla format with Captain America Winter Soldier? Loads with mangled filenames into your extractor.

[http://www.mediafire.com/download/k0qlk ... oldier.rar](http://www.mediafire.com/download/k0qlkc28tdfpw12/Winter+Soldier.rar)
## Post #39
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-07-23T13:48:27+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from francoiscoiscois
>
> Hi Cra0

How did you get to import the .bdae into 3DSmax ?
I didnt found any importer script so far ...

Even if it only import LOD I would really like to experiment with it
Chipicao made an [import script](http://forum.xentax.com/viewtopic.php?p=91256#p91256).

> Reply from pepsiguy2
>
> Hey Cra0 can you look into the new gla format with Captain America Winter Soldier? Loads with mangled filenames into your extractor.
Interesting. It is in the format of a CustomPak, and your options appear proper. There is a new 0x04 flag, though. I'll take a look at it.

Update: modified my extractor to work with the new format. See [here](http://forum.xentax.com/blog/?p=1085) for download.
## Post #40
- Username: SSingh511
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 23, 2015 12:52 pm
- Post datetime: 2020-04-02T11:47:42+00:00
- Post Title: Re: The Dark Knight Rises .gla

Sorry for bumping this old topic but i've spend ample amount of time, trying to figure how to extract this .bdae files, i was able to get textures easily and was even able to convert them in .png but i ain't able to extract these .bdae models
I've use each and every .bdae script available on xentax/zenhax or other sources in both quickbms and noesis (which even includes Spider-Man Unlimited, Disney Magic Kingdoms, AS, GT Racing scripts and even Ironman 3 .BDAE script) and also used Chipicao's GT Racing 2 importer script which always gave me this error (yes i have installed PVRTexTool plugins and also checked whether it's running or not and had kept raw .TGAs in directory and also even tried keeping them in subdirectory but it didn't worked- even tried after converting them into PVR)

Error :

After getting this error, even if i make a fake "dependancies.txt" or not, in both the scenarios i get the error shown below:


So can anyone please help me out with this situation?
## Post #41
- Username: Beridow
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 03, 2020 6:33 pm
- Post datetime: 2020-08-03T11:51:58+00:00
- Post Title: Re: The Dark Knight Rises .gla

Do you have any update for this?
## Post #42
- Username: jamesmiller57
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 7:50 am
- Post datetime: 2020-09-20T20:48:01+00:00
- Post Title: Re: The Dark Knight Rises .gla

hello can anywone know that the amazing spider man gameloft game also have actors.gla but the tool that is named gameloft archieve tool isnt working so can anywone make a tool that also works on the amazing spider man
## Post #43
- Username: Rahgar635
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 21, 2020 12:55 am
- Post datetime: 2020-11-20T17:11:39+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from francoiscoiscois ↑Mon Dec 30, 2013 4:21 am at Mon Dec 30, 2013 4:21 am
>
> 
Hi Cra0

How did you get to import the .bdae into 3DSmax ?
I didnt found any importer script so far ...

Even if it only import LOD I would really like to experiment with it

Hi!

I was able to extract and access the .gla files, but I couldn't find any way to recompact all the extracted files back to .gla.

Is there a softawere that compresses more than one file for .gla?

Thanks for listening.
## Post #44
- Username: Myxtar6
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 20, 2021 12:00 am
- Post datetime: 2021-12-23T13:51:09+00:00
- Post Title: Re: The Dark Knight Rises .gla

Hi, Heroes of the Dark unfortunately the program does not work for Gameloft Archive Tool  
Really no is hope?
[https://www.gameloft.com/game/heroes-of-the-dark](https://www.gameloft.com/game/heroes-of-the-dark)
## Post #45
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-23T18:46:53+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Really no is hope?

Check the scripts and tools listed in this article [http://wiki.xentax.com/index.php/Gameloft_CustomPak_GLA](http://wiki.xentax.com/index.php/Gameloft_CustomPak_GLA)
## Post #46
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-12-24T19:10:31+00:00
- Post Title: Re: The Dark Knight Rises .gla

I decided to look at the files, in general, in these archives the header is always encrypted (in the files from the game Sniper Fury) by xor with seed like:

```
0x19660D * dwSeed  + 0x3C6EF35F
```


After decrypting the header you got next structure:

```
{
   //Values in big endian
   public UInt32 dwVersion { get; set; } // Always 0
   public UInt32 dwTableOffset { get; set; }
   public Int32 dwTotalFiles { get; set; }
   public UInt32 dwMagic { get; set; } // A9D10201
}
```
## Post #47
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-12-25T14:09:26+00:00
- Post Title: Re: The Dark Knight Rises .gla

Hashing algorithm is FNV1a. Entry table

```
{
   public UInt32 dwHash { get; set; }
   public UInt32 dwOffset { get; set; }
   public Int32 dwDecompressedSize { get; set; }
   public Int32 dwCompressedSize { get; set; }
   public Int32 dwReserved { get; set; }
   public Int32 dwEncrypted { get; set; } // if value > 0 then encrypted (can be 0/1/8) algo type???
}
```
## Post #48
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-10-02T16:18:28+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from ikskoks ↑Fri Dec 24, 2021 2:46 am at Fri Dec 24, 2021 2:46 am
>
> 
Really no is hope?

Check the scripts and tools listed in this article http://wiki.xentax.com/index.php/Gameloft_CustomPak_GLA

Link is dead, leads to a 404. Any workaround?
## Post #49
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-10-02T21:24:24+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from AxelNoir ↑Tue Oct 03, 2023 12:18 am at Tue Oct 03, 2023 12:18 am
>
> 
Link is dead, leads to a 404. Any workaround?

Try this [https://web.archive.org/web/20230203035 ... tomPak_GLA](https://web.archive.org/web/20230203035944/http://wiki.xentax.com/index.php/Gameloft_CustomPak_GLA)
## Post #50
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-10-02T22:17:08+00:00
- Post Title: Re: The Dark Knight Rises .gla

> Reply from ikskoks ↑Tue Oct 03, 2023 5:24 am at Tue Oct 03, 2023 5:24 am
>
> 
AxelNoir wrote: ↑Tue Oct 03, 2023 12:18 am
Link is dead, leads to a 404. Any workaround?


Try this https://web.archive.org/web/20230203035 ... tomPak_GLA

Thanks looks like it works. I managed to extract the .gla files but inside there are .bdae files, I can't find any scripts to import these particular types of bdae files for TDKR. Any help maybe?

I uploaded a sample on this thread: [viewtopic.php?t=14336](https://forum.xentax.com/viewtopic.php?t=14336)
