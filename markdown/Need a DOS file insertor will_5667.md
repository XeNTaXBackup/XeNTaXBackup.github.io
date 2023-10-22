## Post #1
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2010-12-29T20:19:24+00:00
- Post Title: Need a DOS file insertor will

I`ll start from the begining,i`ve been ripping psp games for about 5 years now,and i know alot about all psp format files and how most of them work,I use alot of other peoples tools to open big files to get at the files needed to rip( i do give credit to the people who make the tools),to make games smaller to fit onto the psp memory cards,to make ripkits so others can make the game iso`s smaller.
But if i can make a ripkit that rips files out of big file and put them back in,other people can start to make there own ripkits!
So i have a tool that can tell me the offset of a file and the size and give it a name,abit like Dragon UnPACKer.which  gives me a text file with all the files,then i use a DOS tool by Hp called Crusher2 which rips out the files from a Big file using a txt file , this DOS command:-

BAT file for crusher 2:-

crusher2.exe e test.bin LBA.TXT

This tells crusher 2 to extract the files from the test.bin file using the info from the LBA.TXT into a folder.

The LBA.TXT file is:-

0000020864|0000020864|TEST-File0001.at3
0000044340|0000003278|TEST-File0001.png

The test.bin file is 285 KB but the 2 files it extracted is 142 KB the two files are a .png(picture)and a .at3(psp audio file)
crusher 2 extracts the 2 files into a folder called after the big file it ripped it from see picture below:-



But when i rebuild the files with crusher 2 it only rebuilds the 2 files it riped so the new test.bin file is only made up from the .png file and .at3 file  

Bat file for crusher 2 is :-

crusher2.exe r test.bin LBA.TXT

Why Don`t i just extract all the files from the test.bin?????(or any other big file i want to extract)and then rebuild it!
I cannot extract all files as i don`t know the full table of whats in the big files,just the psp audio and picture and movie files,as some big files i don`t know the format off!!!!
Thats why i need a Dos tool to inject the files back into the big file from info from the Text file!and the folder that the files where extracted, see picture above,and i uderstand that the files need to be the same size or padded out using a HEx editor or a padding tool!

So i need your help for a DOS tool so i can make a extractor tool and a rebuilder tool for people to use to rip PSP big files
and i`ll pay for such a tool via paypal

The rebuilder tool will place the files from the extarcted folder to the original big file using the lba table from the text file.

Hope someone can help me 

many thanks for reading this post

Cozy

see me @ pspripkits.com

Hers a demo of all files or test run the bat file this will rip the 2 files from the test.bin:-


 demo test files.rar
(185.98 KiB) Downloaded 33 times
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-30T21:43:48+00:00
- Post Title: Need a DOS file insertor will

Hm, maybe it's possible with a self-written plugin for the console rip creator (CRC.exe from pspripkits.com). But I don't know for sure.
## Post #3
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2010-12-31T16:14:17+00:00
- Post Title: Need a DOS file insertor will

> Reply from AlphaTwentyThree
>
> Hm, maybe it's possible with a self-written plugin for the console rip creator (CRC.exe from pspripkits.com). But I don't know for sure.

Yes i`m a member of that site and have loads of tools for psp file formats,but i need a tool like Itze tool, called " Infuser - Fileinjector "very nice but i need a tool like that to inject files back it a big file but under DOS.So i can create extract/rebuild kits for people who want to rip big files.but will extract only the files needed to rip.I have pm Itze.

Infuser - Fileinjector post :-

[viewtopic.php?f=13&t=3363&p=28381&hilit ... ser#p28381](http://forum.xentax.com/viewtopic.php?f=13&t=3363&p=28381&hilit=Infuser+Infuser#p28381)
## Post #4
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-01-08T18:35:14+00:00
- Post Title: Need a DOS file insertor will

OK, here is the thing, I have had a look at you example files and I can tell that your LBA text is indeed correct, the difference between the original package, and the rebuit one, is the padding, that makes the original bigger. But test.bin only incudes those two files (plus the padding counting as "free space"). Then, when rebuilding, crusher2.exe uses the standar PSP 0x800 padding, making the result file smaller (but having packaged files in different positions, so it might not work in-game, as "test.new" would then need an updated LBA).

I dont know what did you use to get the LBA.txt but it´s ok (maybe you got it from another file, using that "like Dragon UnPACKer tool"?).
Anyway, I could code a proper extractor/reinsertor but now that you know the LBA is correct, IDK if you still need it XD.

If you still interested, do not hesitate to contact me ([skybladecloud@hotmail.com](mailto:skybladecloud@hotmail.com)).

King regards

Sky
## Post #5
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-01-09T21:41:43+00:00
- Post Title: Need a DOS file insertor will

Thanx SKY,but i need a DOS tool to extract & reinsert the files from a file using the LBA.TXT file,so i can use it on all types of files,like if i had a data.pak file which was 546 mb in size and it has 100mb of at3 files (psp audio files)the LBA.TXT file shows the offset and size and name,it extracts the files to a @folder, then after i made the files smaller and padded them to the original size,insert them back in!and then i had another file called pop.ea which was 321mb and the LBA.TXT file found 30mb of pmf(psp movie files)i could do the same as the DOS tool would read the info from the LBA.TXT file?
Just need a DOS tool to read the LBA.TXT file, extract the files into a folder then reinsert them back in,all from reading the info from the LBA.TXT file?It sounds simple but i don`t have the programming skills do do it!!!

Cozy
## Post #6
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-01-10T00:24:12+00:00
- Post Title: Need a DOS file insertor will

Alright i think I got it, and works with your example files. Will test it deeper and upload it tomorrow.

Kind regards

Sky.
## Post #7
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-01-10T18:05:49+00:00
- Post Title: Need a DOS file insertor will

> Reply from SkyBladeCloud
>
> Alright i think I got it, and works with your example files. Will test it deeper and upload it tomorrow.

Kind regards

Sky.

This is a true data file and a better example,this has .gim files and .vag files in it.The download has the data file and the txt file with the off set and size and name of files.

Cheers for having a look!!

cozy

3.2 mb  multi upload links

[http://www.multiupload.com/RY70E4992W](http://www.multiupload.com/RY70E4992W)
## Post #8
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-01-10T20:41:54+00:00
- Post Title: Need a DOS file insertor will

Good, I´ve sent you a PM.
## Post #9
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-01-11T20:12:44+00:00
- Post Title: Need a DOS file insertor will

Thanx for the reply
