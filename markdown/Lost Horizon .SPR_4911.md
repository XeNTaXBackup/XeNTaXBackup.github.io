## Post #1
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2010-08-22T03:54:19+00:00
- Post Title: Lost Horizon *.SPR

Lost horizon 
How extract this file : 

sample 283ko compressed :  [http://www.zshare.net/download/79589016578c9328/](http://www.zshare.net/download/79589016578c9328/)

or demo at here : [http://www.gamershell.com/download_62252.shtml](http://www.gamershell.com/download_62252.shtml)

is *.spr extension i have try with sprext.exe but not works ( error reading structures) and tunguska explorer 1.1 seem dead links...if you can help me !
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-08-22T15:54:19+00:00
- Post Title: Lost Horizon *.SPR

It looks like it's the modified version of the .SPR file format of
Secret Files: Tunguska and Secret Files 2: Puritas Cordis
The files are partially encrypted with a KeyNumber, which is game-dependant.
See the SPR description here: [http://wiki.xentax.com/index.php/Secret ... nguska_SPR](http://wiki.xentax.com/index.php/Secret_Files:_Tunguska_SPR)
If you send me the game EXE file, I'll try to find the actual KeyNumber.
## Post #3
- Username: MeteoraMan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 08, 2010 4:39 am
- Post datetime: 2010-08-22T17:19:30+00:00
- Post Title: Lost Horizon *.SPR

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-08-22T19:36:16+00:00
- Post Title: Lost Horizon *.SPR

I couldn't use the EXE file, because it's packed/protected. But, I made a brute-forcer, so I got the KeyNumber: 0x08A0DC
I also created a primitive SPR extractor. Usage: LostHorizon_extr.exe <SPR_File> <TargetDir>
## Post #5
- Username: MeteoraMan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 08, 2010 4:39 am
- Post datetime: 2010-08-22T19:51:04+00:00
- Post Title: Lost Horizon *.SPR

bacter
I want to translate this game to Russian language.
You helped me a lot.
Thank you very much.
## Post #6
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2010-08-24T06:36:23+00:00
- Post Title: Lost Horizon *.SPR

bacter thank you for your help !!! and only the data.spr make 1.53 giga and have a error ( like you said in your *.exe ): 

G:\MES JEUX 6\Lost Horizon2>LH.exe "data.spr" "g:\MES JEUX 6\Lost Horizon2\"  1>log.txt
Exception EAccessViolation in module LH.exe at 00002CF5.
Access violation at address 00402CF5 in module 'LH.exe'. Write of address 012AC00D.

the file video.spr size is 1.33 giga is extracted with 0 errors, i hope you make a fix.
## Post #7
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2010-08-29T18:59:28+00:00
- Post Title: Lost Horizon *.SPR

@bacter: Thanks for publishing the key domain value. As I had already deleted my brute force tool used to get the Secret Files 2 key, you saved me the hassle of doing this all over again. 

I have update my [SPRExt application](http://oezmen.eu/gameresources/) accordingly to support Lost Horizon as well. Also, since Lost Horizon uses the SSHC compression method in its data files, I have added support for this method as well. The Secret Files games use this method in their save games, which means that these should now be decompressable as well.

If you find any bugs in the tool, please let me know.

For those interested, the format news have been roughly documented at the wiki page quoted above.

Best wishes,
Deniz
## Post #8
- Username: ced117
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 06, 2010 2:36 am
- Post datetime: 2010-09-05T19:25:29+00:00
- Post Title: Lost Horizon *.SPR

Thank you Deniz for releasing the SPRExt application with the source code 
I have to say that it's working great under Wine.

And also, thanks bacter for the key domain value
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2010-09-06T20:01:17+00:00
- Post Title: Lost Horizon *.SPR

Thanks for the feedback! Glad to hear the program is accessible despite my platform choice.

Best wishes,
Deniz
## Post #10
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-09-06T23:59:30+00:00
- Post Title: Lost Horizon *.SPR

Now,it can be translate to chinese,very thanks!
[20_5394_236a60e05b2f3f9.jpg](https://xentaxbackup.github.io/file/3411_20_5394_236a60e05b2f3f9.jpg)
## Post #11
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2010-09-08T18:27:06+00:00
- Post Title: Lost Horizon *.SPR

Interesting. How do you get the modified files back into the game? Do you have a repack tool or does it suffice to simply place the files outside of the SPR archives into the correct directory?
## Post #12
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-09-09T12:53:12+00:00
- Post Title: Lost Horizon *.SPR

> Reply from Deniz Oezmen
>
> Interesting. How do you get the modified files back into the game? Do you have a repack tool or does it suffice to simply place the files outside of the SPR archives into the correct directory?

Yes,simply place the files outside of the SPR archives into the correct directory.
Extract the loca.spr and copy data folder to game root,and remove  loca.spr  from archives.ini like this:

[Archives]
ArchiveFileCount=5
ArchiveFile0=data.spr
ArchiveFile1=music.spr
ArchiveFile2=music.spr
ArchiveFile3=video.spr
ArchiveFile4=data_patch.spr
ArchiveFile5=loca_patch.spr
ArchiveFile6=video_patch.spr
ArchiveFile7=music_patch.spr
ArchiveFile8=data_patch2.spr
ArchiveFile9=loca_patch2.spr
ArchiveFile10=music_patch2.spr
## Post #13
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-09T19:27:45+00:00
- Post Title: Lost Horizon *.SPR

There's another way. You can make your own .SPR file and put it to the end of the list in the "archives.ini".
Example:

```
ArchiveFileCount=7
ArchiveFile0=data.spr
ArchiveFile1=loca.spr
ArchiveFile2=music.spr
ArchiveFile3=video.spr
ArchiveFile4=data_patch.spr
ArchiveFile5=MY_MODIFIED_FILES.SPR
ArchiveFile6=THESE_ARE_MY_FILES_TOO.spr
```

This is my very primitive .spr maker (originally I created to the Secret Files : Tunguska)
It's a work-in-progress version, there's no SLZX, SSHC or any other kind of data compression,
but it works. (At least it worked with the Tunguska games)
