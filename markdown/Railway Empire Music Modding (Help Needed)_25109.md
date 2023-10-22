## Post #1
- Username: Shamasaurus
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 07, 2020 3:15 am
- Post datetime: 2022-03-04T18:50:45+00:00
- Post Title: Railway Empire Music Modding (Help Needed)

Trying to mod the main menu music for a start. 

Process:
Recreate the .fsb file where the games music files are held, "trainiac_music" .fsb file

- Open FMOD Designer, make new project, add new event group, call it "Music", make a sub-group, call it the name of the .fsb file, "trainiac_music"
- Add all the songs from the OG .fsb file in MP3 format with the one, NEW EDITED SONG for the main menu replaced and renamed the exact same as the original. 
- Build project

Now, 2 annoying things happen. One, the file size went from 83.9 mb (original fsb) to 712 mb (my new edited fsb file). Two, when I test the fsb in foobar, all the files are out of order and not listed exactly the same as in the original. I don't get it cause there all in order in FMOD designer...

But anyway, to wrap up I take the new .fsb and put it in the folder path made when I unpacked the huge "Data0" file the .fsb was contained in, so "data0\__fukroot__\sound"... REPLACED the original trainiac_music fsb with my new one, back up, click pack.fuk this time instead of unpack.fuk, boom. Makes me my new Data0 file and here's the last thing. 

First I literally kept all other folders in the Data0 file there so when repacking only the new song should reappear and then second time I just tried keeping only exactly what was being changed. So the folders pathed all the way to trainiac_music, where that was the only thing left inside. Repacked both times. 

The former, game crashes doesn't even start. The latter one the game boots up but the main menu is muted... and all other music. So I don't know what i'm doing wrong. Please help!

Edit: So even after rechanging file names and compressing til the music was actually below the original fsb size and practically sounded like gameboy color music at 4000 hz I repacked and game still says music error in lobby. I literally have no idea what else to try differently. I dont know if its cause I now changed the fsb file original names or what. Since when using FMOD Designer it apparently keeps changing around the ORDER of the music files. Apparently 2 comes after 19 and 3 after 29 etc etc.
[photo_optimized.png](https://xentaxbackup.github.io/file/21880_photo_optimized.png)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-08T16:03:56+00:00
- Post Title: Railway Empire Music Modding (Help Needed)

Can you upload original FSB file?
## Post #3
- Username: Shamasaurus
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 07, 2020 3:15 am
- Post datetime: 2022-03-15T04:29:02+00:00
- Post Title: Railway Empire Music Modding (Help Needed)

> Reply from ikskoks ↑Wed Mar 09, 2022 12:03 am at Wed Mar 09, 2022 12:03 am
>
> 
Can you upload original FSB file?

Sure:

[https://mega.nz/file/Z0EiFQLA](https://mega.nz/file/Z0EiFQLA)

Key: MOsgP-o5POszDtc-Yi0lcTua4HMQtrVuJWeRUip9ZHA
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-15T22:13:15+00:00
- Post Title: Railway Empire Music Modding (Help Needed)

So I've checked it and it seems your sample is FSB5 file using "Custom CELT" codec
and FMOD designer creates FSB4 files with PCM codec.
More info here [http://wiki.xentax.com/index.php/FMOD_Audio_FSB](http://wiki.xentax.com/index.php/FMOD_Audio_FSB)

So in my opinion it's not possible to replace FSB5 file with FSB4 file right now (game will crash like you said).
Maybe FMOD Studio will work? But I'm not sure, I've never used it.

If you'll find any solution to this, let me know and I will add it to the wiki.


Edit: Sorry, it seems FMOD Studio can create only BANK files...
[http://wiki.xentax.com/index.php/FMOD_Audio_BANK](http://wiki.xentax.com/index.php/FMOD_Audio_BANK)

Edit2: Try with FMOD SoundBank Generator (fsbank.exe)
[https://www.fmod.com/download/fmodstudi ... fmodengine](https://www.fmod.com/download/fmodstudio/api/Win/fmodstudioapi10211win-installer.exe#fmodengine)
## Post #5
- Username: Shamasaurus
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 07, 2020 3:15 am
- Post datetime: 2022-03-15T22:54:09+00:00
- Post Title: Railway Empire Music Modding (Help Needed)

> Reply from ikskoks ↑Wed Mar 16, 2022 6:13 am at Wed Mar 16, 2022 6:13 am
>
> 
So I've checked it and it seems your sample is FSB5 file using "Custom CELT" codec
and FMOD designer creates FSB4 files with PCM codec.
More info here http://wiki.xentax.com/index.php/FMOD_Audio_FSB

So in my opinion it's not possible to replace FSB5 file with FSB4 file right now (game will crash like you said).
Maybe FMOD Studio will work? But I'm not sure, I've never used it.

If you'll find any solution to this, let me know and I will add it to the wiki.


Edit: Sorry, it seems FMOD Studio can create only BANK files...
http://wiki.xentax.com/index.php/FMOD_Audio_BANK

Edit2: Try with FMOD SoundBank Generator (fsbank.exe)
https://www.fmod.com/download/fmodstudi ... fmodengine

Okay, if I make any further developments I'll let you know. I was doing it properly though right? It seems too simple to mess up. Music in the main menu was just mute, but the game was running fine.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-15T23:05:55+00:00
- Post Title: Railway Empire Music Modding (Help Needed)

That depends what you mean by "properly". If your goal is to replace music in some older game using FSB4 file format, then it's fine. It will work on some older titles like "The Silent Age" (Unity game with support for FSB4 files). 

But if you want to mod some more recent games, then FMOD Designer won't work for you.
My suggestion for now is to try FMOD SoundBank Generator, but I don't know how the game will handle other codecs.
You can search through vgmstream source code and see how this "custom CELT" is handled, because I have no idea rigt now.
Code is here [https://github.com/vgmstream/vgmstream](https://github.com/vgmstream/vgmstream)
## Post #7
- Username: Shamasaurus
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 07, 2020 3:15 am
- Post datetime: 2022-03-16T04:53:18+00:00
- Post Title: Railway Empire Music Modding (Help Needed)

> Reply from ikskoks ↑Wed Mar 16, 2022 7:05 am at Wed Mar 16, 2022 7:05 am
>
> 
That depends what you mean by "properly". If your goal is to replace music in some older game using FSB4 file format, then it's fine. It will work on some older titles like "The Silent Age" (Unity game with support for FSB4 files). 

But if you want to mod some more recent games, then FMOD Designer won't work for you.
My suggestion for now is to try FMOD SoundBank Generator, but I don't know how the game will handle other codecs.
You can search through vgmstream source code and see how this "custom CELT" is handled, because I have no idea rigt now.
Code is here https://github.com/vgmstream/vgmstream

Think that was my first attempt if im not mistaken. Using the soundbank. So it's just doesnt seem possible then. Oh well. In need of bms script on a new project anyway. If you can help with that, I posted a new article on the matter.
## Post #8
- Username: Shamasaurus
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 07, 2020 3:15 am
- Post datetime: 2022-08-08T22:35:55+00:00
- Post Title: Railway Empire Music Modding (Help Needed)

> Reply from ikskoks ↑Wed Mar 16, 2022 7:05 am at Wed Mar 16, 2022 7:05 am
>
> 
That depends what you mean by "properly". If your goal is to replace music in some older game using FSB4 file format, then it's fine. It will work on some older titles like "The Silent Age" (Unity game with support for FSB4 files). 

But if you want to mod some more recent games, then FMOD Designer won't work for you.
My suggestion for now is to try FMOD SoundBank Generator, but I don't know how the game will handle other codecs.
You can search through vgmstream source code and see how this "custom CELT" is handled, because I have no idea rigt now.
Code is here https://github.com/vgmstream/vgmstream

I'm gonna make another attempt I think. Observe the pic below to see. Im using an fsb extractor and it showed the unknown code of the fsb if that helps. So frustrating man I wanna crack this case! Someone on Xentax said they found a workaround to mod properly and it was like 4 years ago. Way before we discussed on here. Unfortunately he hasnt been around since that time frame. So I cant even ask him for any tips...

And yes, still no tool that helps you recreate FSB5 files properly. fsbank.exe can make it but like I said it might not ever read it cause the file blows up in size in the Data.0 fuk file. Im not even sure if im repacking it properly either. Never have any clue what to repack it as. PCM, Opus... no idea what any of the stuff means.
[Screenshot (1341).png](https://xentaxbackup.github.io/file/22617_Screenshot (1341).png)
