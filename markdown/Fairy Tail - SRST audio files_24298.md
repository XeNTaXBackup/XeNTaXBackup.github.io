## Post #1
- Username: BragonGod
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 21, 2021 6:39 am
- Post datetime: 2021-07-29T13:40:11+00:00
- Post Title: Fairy Tail - SRST audio files

So i'm trying to extract audio from a game called Fairy Tail
the audio format from the game made by koei tecmo btw are "SRSA" and "SRST"
Through googling i was able to extract SRSA just fine but i had a contradicting issue with SRST
Everyone says "just delete everything before KTSS" in the hex editor and then change the extension to "kns", but the problem is my files don't have KTSS, except for 1 and the KTSS is at the bottom and obviously deleting a big portion of it doesn't make sense (tried it, didn't work regardless)
I would appreciate any help...
ty   


Files in question: [https://www.mediafire.com/file/dmk6j81o ... t.rar/file](https://www.mediafire.com/file/dmk6j81oa92h31j/srst.rar/file)
## Post #2
- Username: BragonGod
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 21, 2021 6:39 am
- Post datetime: 2021-08-01T02:21:12+00:00
- Post Title: Fairy Tail - SRST audio files

Anyone?
## Post #3
- Username: Patrick Hasselbank
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 28, 2021 12:09 am
- Post datetime: 2021-08-02T11:50:20+00:00
- Post Title: Fairy Tail - SRST audio files

Maybe you can rename srst file into srsa and to extract it usual way?
## Post #4
- Username: BragonGod
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 21, 2021 6:39 am
- Post datetime: 2021-08-03T18:53:12+00:00
- Post Title: Fairy Tail - SRST audio files

tried that... didn't work
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-08-04T13:42:48+00:00
- Post Title: Fairy Tail - SRST audio files

I couldn't get the archive to load directly into Foobar, but you can use the attached QuickBMS script to extract all of the individual audio files, which will play in Foobar/vgmstream.


 kovs.zip
(425 Bytes) Downloaded 167 times
## Post #6
- Username: BragonGod
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 21, 2021 6:39 am
- Post datetime: 2021-08-04T17:26:45+00:00
- Post Title: Fairy Tail - SRST audio files

DUDE
Literally a hero!!
Thank you so much there's literally 0 information about this on the internet! you saved my life
## Post #7
- Username: Patrick Hasselbank
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 28, 2021 12:09 am
- Post datetime: 2021-08-06T14:02:59+00:00
- Post Title: Fairy Tail - SRST audio files

> Reply from DKDave ↑Wed Aug 04, 2021 9:42 pm at Wed Aug 04, 2021 9:42 pm
>
> 
I couldn't get the archive to load directly into Foobar, but you can use the attached QuickBMS script to extract all of the individual audio files, which will play in Foobar/vgmstream.

kovs.zip

Unbelievable!
## Post #8
- Username: personman123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 06, 2022 11:30 pm
- Post datetime: 2022-04-06T16:08:58+00:00
- Post Title: Fairy Tail - SRST audio files

> Reply from DKDave ↑Wed Aug 04, 2021 9:42 pm at Wed Aug 04, 2021 9:42 pm
>
> 
I couldn't get the archive to load directly into Foobar, but you can use the attached QuickBMS script to extract all of the individual audio files, which will play in Foobar/vgmstream.

kovs.zip

How would I use the script? I've extracted the zip folder and it's just a .txt file. Is there something I'm missing?
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-04-06T16:38:37+00:00
- Post Title: Fairy Tail - SRST audio files

It's a script for QuickBMS: [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
## Post #10
- Username: Dante013
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 13, 2023 11:45 pm
- Post datetime: 2023-04-13T16:23:46+00:00
- Post Title: Fairy Tail - SRST audio files

Thank you to everyone who posted here. I also tried to open the srst files, I tried the method explained here and it does work! Here is he full process in case someone else runs on the same issue :

Download quickbms.
Download kovs.zip and extract it.
Download Foobar2000 ([https://www.foobar2000.org/download](https://www.foobar2000.org/download)).
Go on vgmstream website ([https://vgmstream.org](https://vgmstream.org)) and download the foobar2000 component.
Prepare the srst file.

EXTRACTION
Run quickbms. It's asking you a script. Choose the txt file that is in the kovs folder.
Then it's asking you for an archive (the file you want to extract). Select the srst file.
Then select an output folder. The script will extract all the audio files that are in this archive. You now have extracted all the audio files... in kvos format. A sound format so rare that even Google can barely explain what it is.

PLAYING THE FILES
Now open Foobar2000. Open the Library tab, and click on Configure. It opens the settings.
Click on the very first line, called Components. There's a button "Install" at the bottom of that page. Click on it and select the vgmstream component. Restart the software.
Now, put a kvos file in the window of Foobar. You can play the sound to see what it is!

CONVERT
Yes, that's not all : you can also CONVERT the files thanks to Foobar! Once you've found a sound you want in a more basic format, right-click on it, then click on Convert, and Quick Convert. Follow the steps, it will quickly give you the sound in wav format (or any other format that you require).


In the case of Fairy Tail, there are 3 srst files : the second biggest one (120MB or so) has the OST (in great quality). The smallest one has the characters' basic sounds (very interesting if you want the characters' voices for a game). The biggest one has some dialogue lines.

EDIT : After listening to a lot of those files, I'd like to warn everyone that many files are incomplete. Looking through the game folders, I noticed a "data" folder where there are files identical to the srst ones, except the have the extension ".file".
Could these files be storing the complete audio files? Or is the butchering due to a bug in the script? Does anybody have a solution to ensure we get the full audio files?
## Post #11
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2023-09-01T22:28:30+00:00
- Post Title: Fairy Tail - SRST audio files

> Reply from BragonGod ↑Thu Jul 29, 2021 9:40 pm at Thu Jul 29, 2021 9:40 pm
>
> 
So i'm trying to extract audio from a game called Fairy Tail
the audio format from the game made by koei tecmo btw are "SRSA" and "SRST"
Through googling i was able to extract SRSA just fine but i had a contradicting issue with SRST
Everyone says "just delete everything before KTSS" in the hex editor and then change the extension to "kns", but the problem is my files don't have KTSS, except for 1 and the KTSS is at the bottom and obviously deleting a big portion of it doesn't make sense (tried it, didn't work regardless)
I would appreciate any help...
ty   


Files in question: https://www.mediafire.com/file/dmk6j81o ... t.rar/file

I'm looking at Stranger of Paradise right now. What did you find re: the SRSA files? Another thread (I think covering Cethleann) had a short QBMS script, but the extracted files did not play in Foobar.
