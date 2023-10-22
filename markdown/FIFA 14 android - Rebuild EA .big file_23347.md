## Post #1
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-20T17:11:57+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

Hello mates,
Hope all is happy and safe now days   
I ask about how to add a new file to a .big file ( EA files from FIFA ) and not just extract and reimport the same file with quichbms ?? I wish I find an answer.
Thankss
## Post #2
- Username: TheSeeker25
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-20T19:26:41+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

These files are supported by Game Extractor, Dragon Unacker, MultiEx etc. Did you try them all?

More info here
[http://wiki.xentax.com/index.php/EA_BIG_BIGF_Archive](http://wiki.xentax.com/index.php/EA_BIG_BIGF_Archive)
[http://wiki.xentax.com/index.php/EA_VIV_BIG4](http://wiki.xentax.com/index.php/EA_VIV_BIG4)
[http://wiki.xentax.com/index.php/EA_BIG_EB](http://wiki.xentax.com/index.php/EA_BIG_EB)


There is also a Final BIG Editor which can add or delete files in the archive.

Edit: Try also big4f program.
## Post #3
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-22T20:36:57+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

I tried finalbig04 but it just crashing or it keeps loading and it ends that's I close the program..
Game extractor tried but doesn't accept the script I don't know why .
I will try your solutions and tell you.
Thanks my friend for replying
## Post #4
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-25T03:14:51+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

> Reply from ikskoks ↑Thu Jan 21, 2021 3:26 am at Thu Jan 21, 2021 3:26 am
>
> 
These files are supported by Game Extractor, Dragon Unacker, MultiEx etc. Did you try them all?

More info here
http://wiki.xentax.com/index.php/EA_BIG_BIGF_Archive
http://wiki.xentax.com/index.php/EA_VIV_BIG4
http://wiki.xentax.com/index.php/EA_BIG_EB


There is also a Final BIG Editor which can add or delete files in the archive.

Edit: Try also big4f program.

I can't I tried every one and I didn't reach anything, if you can explain it to me maybe I used wrong..
Too frustrated with this
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-25T09:41:15+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

So please upload a sample, because there are at least 3 types of BIG archives.
Also tell me full name of the game and a platform (because there are at least 30 FIFA games on several platforms... you need to be more precise)
## Post #6
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-27T06:12:42+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

Files are from FIFA 14 android, i tried to add some files but end with nothing: i tried big file extractor but all files are corrupted , and with game extractor it says i can't modify .. 
i see that this files are moddified and not the original especially the first a whole new logos are added
The files;
[https://www.mediafire.com/file/ev3dbbbv ... e.big/file](https://www.mediafire.com/file/ev3dbbbvlnii1dc/cro_base.big/file)
[https://www.mediafire.com/file/fybsawlu ... y.big/file](https://www.mediafire.com/file/fybsawluus5kik2/cro_feonly.big/file)
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-27T18:20:54+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

Ok, I have checked your sample and it is standard BIGF archive.

You can use big4f to unpack, repack and add new files as you wish.
[https://github.com/withmorten/big4f](https://github.com/withmorten/big4f)

So you need to extract files first with command

```
big4f e/x <big file> <directory>
```


add your files and then pack it with command

```
big4f f/4 <directory> <big file>
```


Check this link if you will encounter any issues
[https://www.google.com/search?client=fi ... mmand+line](https://www.google.com/search?client=firefox-b-d&q=how+to+use+command+line)
## Post #8
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-27T21:11:51+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

it keeps show me " was unexpected at this time. ' i dont know why
## Post #9
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-27T21:26:15+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

Show me screenshot.
## Post #10
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-27T22:00:29+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

sorry but i write something wrong and i fixed it but this whati get now
[2021-01-27-.png](https://xentaxbackup.github.io/file/19404_2021-01-27-.png)
## Post #11
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-27T22:14:16+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

To make it work you should put all files (BIGF archive, big4f etc.) in some directory on your desktop,
use "cd" command to go to that directory and execute something like this

```
big4f.exe e cro_base.big out_directory
```


Remember to check tutorials on cmd usage!
## Post #12
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-27T22:34:50+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

the 2 folder are in one directory on desktop;
FIFA\big4f
FiFA\Patch...
you want to put in same folder
## Post #13
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-27T23:21:39+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

What i miss here? i don't understand 
should i use windows 7 instead of 10 
my mind will blow up 
[2021-01-27-.png](https://xentaxbackup.github.io/file/19408_2021-01-27-.png)
## Post #14
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-27T23:56:12+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

If your BIG file is in some other directory you have to specify full path for this file.
Also all paths with spaces should be conatined inside double quotes like

```
"C:\Users\User\Desktop\some file.big"
```
## Post #15
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-28T01:02:26+00:00
- Post Title: FIFA 14 android - Rebuild EA .big file

try a cmd line and if it works send it to me to try, i jump from line to line like a monkey without get anything

" I'm sorry you are tired with me  "
[2021-01-27-.png](https://xentaxbackup.github.io/file/19410_2021-01-27-.png)
## Post #16
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-28T09:57:52+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

Maybe I'll just show you how it looks on my side

Folder structure - [https://i.imgur.com/pd74FBF.png](https://i.imgur.com/pd74FBF.png)
My command - [https://i.imgur.com/fyQlwF1.png](https://i.imgur.com/fyQlwF1.png)

And result - [https://i.imgur.com/gmvHYC1.png](https://i.imgur.com/gmvHYC1.png)
## Post #17
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-28T19:57:30+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

this worked with first sample i give you (cro_base) but not the second (cro_feonly)
i will try now repacking ..
[2021-01-27-.png](https://xentaxbackup.github.io/file/19415_2021-01-27-.png)
## Post #18
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-28T21:06:28+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

Yeah, for second sample just use BIG File Extractor [https://app.box.com/s/6g2lpct0trk1ylg11j4udcjso4bg4q9h](https://app.box.com/s/6g2lpct0trk1ylg11j4udcjso4bg4q9h)
It has a rebuild option.

[https://i.imgur.com/KmJfWOI.png](https://i.imgur.com/KmJfWOI.png)
## Post #19
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-28T21:37:52+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

rebuilded succuesfully or not as i tried before and i get all files corrupted ..
is it for all BIG EB files ?
## Post #20
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-28T21:48:07+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

Rebuild was completed and archive size is the same as the original, but there are
some changes in the offsets on the beginning of the archive.

So maybe it is just some bug in the tool. If that's the case,
you should report it to the author of this version in this topic 
[https://www.zenhax.com/viewtopic.php?f=17&t=11568](https://www.zenhax.com/viewtopic.php?f=17&t=11568)
If you're lucky, he will fix it.
## Post #21
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-28T21:58:54+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

did you try it mr. ikskoks ?
## Post #22
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-28T22:42:18+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

Yes, I have tried it and I was able to rebuild BIG archive,
but I didn't test it in game.
## Post #23
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-28T22:52:42+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

i did i built but it have warning me that new file is bigger, i reimported it anyway ( not forcing ) and i manage it..
but ingame it doesn't work all of it.. all of the teams logos disappeared

"fe_base is team logos file "
## Post #24
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-28T23:05:27+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

2nd thing: about cro_feonly if i tried to open extracted fsh files  a message appear " not a valid EA SHP file " is this what it supposed to be !!
this i can mange to extract it with Quick BMS !!
## Post #25
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-28T23:13:22+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

> Reply from TheSeeker25 ↑Fri Jan 29, 2021 7:05 am at Fri Jan 29, 2021 7:05 am
>
> 
2nd thing: about cro_feonly if i tried to open extracted fsh files  a message appear " not a valid EA SHP file " is this what it supposed to be !!
this i can mange to extract it with Quick BMS !!
i manage it : i have to extract fsh file extracted with BIG Extractor again !!!!  
chunckzip.bms solved it but my question 
how to reverse the operation? reimporting will do it or not
## Post #26
- Username: Emiliooff
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 25, 2022 3:22 am
- Post datetime: 2022-01-27T19:06:42+00:00
- Post Title: Re: FIFA 14 android - Rebuild EA .big file

hi friends.hope to find everyone.well,how can i add.a new .big kit in fifa14 android.kits kits.etc.big file does anyone know any tools i can.use,?  not just to reimport but to add a new code, that goes for the cro_fenoly.big too, please.for a long time.I've been looking
