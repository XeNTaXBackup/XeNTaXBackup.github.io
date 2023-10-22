## Post #1
- Username: Revgol
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 08, 2023 8:06 pm
- Post datetime: 2023-07-08T13:00:27+00:00
- Post Title: Music Generator DAT/IND File Unpacking Via Wadtool?

Firstly, I'm a musician, and I have absolutely zero programming experience. I am attempting to extract the audio files (with directory/sub folders and file names/extensions intact) from the Music series by Jester Interactive for PS2/PC, and am stuck on two titles, namely; MTV Music Generator 2 and Music 3000. They both have the audio data stored in a file called .DAT, and index data in .IND. I've tried Universal Extractor 2, the original UE, and Dragon UnPACKer, all to no avail. So, I'm guessing that similar programs will not work either.

Wadtool can unpack the wad files in Music Generator, Music 2000, and Music 2002, but is not compatible with the two titles mentioned above. If anyone can help me to do this, that would be awesome (see post 2).


PS: please note that Wadtool has an issue whereby it misses the .vag extension of several of the files that it extracts. And, up to about 70 of the files from these titles are corrupt with bogus sample rates and/or headers. However, Awave Audio can account for this last issue duing conversion.
## Post #2
- Username: Revgol
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 08, 2023 8:06 pm
- Post datetime: 2023-07-08T13:38:13+00:00
- Post Title: Music Generator DAT/IND File Unpacking Via Wadtool?

I'm not sure, but I think the source code to Wadtool is available here: [https://github.com/juju2143/wadtool](https://github.com/juju2143/wadtool)

If anyone has the time, desire, and ability to update it so that it's compatible with the above mentioned titles DAT files...

Also, here's a link to wadtool.exe as the download links on github are not working for some reason: [https://tinyurl.com/Wadtool-1](https://tinyurl.com/Wadtool-1)


EDIT: I've attached what I suspect to be Wadtool's source code below.
[wadtool-master.zip](https://xentaxbackup.github.io/file/24035_wadtool-master.zip)
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2023-07-09T21:39:59+00:00
- Post Title: Music Generator DAT/IND File Unpacking Via Wadtool?

> Reply from Revgol ↑Sat Jul 08, 2023 9:38 pm at Sat Jul 08, 2023 9:38 pm
>
> 
I'm not sure, but I think the source code to Wadtool is available here: https://github.com/juju2143/wadtool

If anyone has the time, desire, and ability to update it so that it's compatible with the above mentioned titles DAT files...

Also, here's a link to wadtool.exe as the download links on github are not working for some reason: https://tinyurl.com/Wadtool-1


EDIT: I've attached what I suspect to be Wadtool's source code below.

My QuickBMS script here should work with MTV MG2 at least: [https://github.com/DKDave/Scripts/blob/ ... 2)_WAD.bms](https://github.com/DKDave/Scripts/blob/master/QuickBMS/PS2/MTV_Music_Generator_2_%28PS2%29_WAD.bms)

If Music 3000 uses the same format it may work on that too ...
## Post #4
- Username: Revgol
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 08, 2023 8:06 pm
- Post datetime: 2023-07-10T19:01:26+00:00
- Post Title: Music Generator DAT/IND File Unpacking Via Wadtool?

> Reply from DKDave ↑Mon Jul 10, 2023 5:39 am at Mon Jul 10, 2023 5:39 am
>
> 
My QuickBMS script here should work with MTV MG2 at least: https://github.com/DKDave/Scripts/blob/ ... 2)_WAD.bms

If Music 3000 uses the same format it may work on that too ...

That's great thanks, it worked. However, is there anyway to modify the script so as to prerve the names of the .vag files like Wadtool does?

Reason is, I wanna use these samples in recreating my MTV Music Generator 2 tracks on Cubase, and having to rename nigh on 3,000 samples manually would be a hell of a task!
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2023-07-10T19:32:16+00:00
- Post Title: Music Generator DAT/IND File Unpacking Via Wadtool?

> Reply from Revgol ↑Tue Jul 11, 2023 3:01 am at Tue Jul 11, 2023 3:01 am
>
> 
DKDave wrote: ↑Mon Jul 10, 2023 5:39 am
My QuickBMS script here should work with MTV MG2 at least: https://github.com/DKDave/Scripts/blob/ ... 2)_WAD.bms

If Music 3000 uses the same format it may work on that too ...


That's great thanks, it worked. However, is there anyway to modify the script so as to prerve the names of the .vag files like Wadtool does?

Reason is, I wanna use these samples in recreating my MTV Music Generator 2 tracks on Cubase, and having to rename nigh on 3,000 samples manually would be a hell of a task!

The filenames work fine with the script.  However, I think the most recent version of QuickBMS has some issues with filenames, so try the previous version.
## Post #6
- Username: Revgol
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 08, 2023 8:06 pm
- Post datetime: 2023-07-10T21:03:56+00:00
- Post Title: Music Generator DAT/IND File Unpacking Via Wadtool?

> Reply from DKDave ↑Tue Jul 11, 2023 3:32 am at Tue Jul 11, 2023 3:32 am
>
> 
The filenames work fine with the script.  However, I think the most recent version of QuickBMS has some issues with filenames, so try the previous version.

I tried the previous version and it worked brilliantly. It also worked on Music 3000 after changing the file name in the script to DATA.DAT. Thank you so much!

However, I tried it on Music 2002 Club Edition for PC, and it did not work. Would you be willing to modify the script to work on that title? I can provide the two files data.wad and data.ind from my original disc if need be.
