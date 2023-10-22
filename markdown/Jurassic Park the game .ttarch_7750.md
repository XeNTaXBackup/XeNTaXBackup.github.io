## Post #1
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-11-25T22:49:39+00:00
- Post Title: Jurassic Park the game .ttarch

Does anyone know how to extract the data files from this .ttarch game archive? I tried using the Telltale Explorer, but couldn't get the archive to be read. I assume this is due to the outdated code and new compression methods Telltale games has instituted. Can anyone offer assistance?

Telltale Explorer can be found here:[http://quick.mixnmojo.com/software/telltale-explorer](http://quick.mixnmojo.com/software/telltale-explorer)

Here's a sample:

[http://www.sendspace.com/file/p19rt4](http://www.sendspace.com/file/p19rt4)
## Post #2
- Username: dezmand07
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 24, 2011 2:22 pm
- Post datetime: 2011-11-26T08:04:32+00:00
- Post Title: Jurassic Park the game .ttarch

ttarchext [http://aluigi.altervista.org/papers.htm#others-file](http://aluigi.altervista.org/papers.htm#others-file)
key for the game - 89DE9F9597DF9CA6C2CDE7CF639583A1DE9C8EEAB0DE99BFC693DA86699CABA9D1A6A5C2CAC689CDE7DFA99C677CC7E1A6D6999CD3C2A0
and TTG Tools for work with *.lang files [http://zalil.ru/32136501](http://zalil.ru/32136501)
## Post #3
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-11-26T19:00:29+00:00
- Post Title: Jurassic Park the game .ttarch

> Reply from dezmand07
>
> ttarchext http://aluigi.altervista.org/papers.htm#others-file
key for the game - 89DE9F9597DF9CA6C2CDE7CF639583A1DE9C8EEAB0DE99BFC693DA86699CABA9D1A6A5C2CAC689CDE7DFA99C677CC7E1A6D6999CD3C2A0
and TTG Tools for work with *.lang files http://zalil.ru/32136501
Thanks for the info, but I'm not sure how to use that extractor. Do I have to run the ttarchtext.exe through a command line with output destinations?
## Post #4
- Username: dezmand07
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 24, 2011 2:22 pm
- Post datetime: 2011-11-26T19:47:45+00:00
- Post Title: Jurassic Park the game .ttarch

ok, try that
- ttarchext.exe throw at the root of drive C (for example)
- create a new folder (with name "new") for extracting the root of drive C
- copy the required *. ttarch the root of drive C, and short in his pereimenovt name 1.ttarch (for convenience)
- open cmd (to throw off the path to the drive C: \>) and enter the following ttarchext.exe 24 "1.ttarch" "new"
- will create a file type *. landb in your "new" and have texts

next *. landb convert to *.txt with help TTG Tools
- first place the TTG Tools folder at the root of drive C
- configure the file config.txt (if it is not yet configured):
C:\TTG Tools\Output
C:\TTG Tools\Input
C:\TTG Tools\temp
C:\TTG Tools\ttarchext.exe
- placed under the Input folder files of type *.landb
- run TTG Tools.exe, press Auto (De) Packer, click Decrypt. Export (in the Output folder will appear *.txt files)
- of Input and Output folders does not remove, translate directly *.txt and not renaming the store
- copy from Input folder translated *.txt files to the Output folder
- run TTG Tools.exe, press Auto (De) Packer, click Encrypt. Pack. Import (in the Output folder will appear translated *.landb)
and ttarchext.exe -b -V 7 24 "1.ttarch" "new" for rebuilding.

but first need to wait when luigi recompiles ttarchext and add to program the key of game, or do it yourself (open source code C)

> - Jurassik Park (when will be released)
## Post #5
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-11-26T20:11:04+00:00
- Post Title: Jurassic Park the game .ttarch

> Reply from dezmand07
>
> ok, try that
- ttarchext.exe throw at the root of drive C (for example)
- create a new folder (with name "new") for extracting the root of drive C
- copy the required *. ttarch the root of drive C, and short in his pereimenovt name 1.ttarch (for convenience)
- open cmd (to throw off the path to the drive C: \>) and enter the following ttarchext.exe 24 "1.ttarch" "new"
- will create a file type *. landb in your "new" and have texts

next *. landb convert to *.txt with help TTG Tools
- first place the TTG Tools folder at the root of drive C
- configure the file config.txt (if it is not yet configured):
C:\TTG Tools\Output
C:\TTG Tools\Input
C:\TTG Tools\temp
C:\TTG Tools\ttarchext.exe
- placed under the Input folder files of type *.landb
- run TTG Tools.exe, press Auto (De) Packer, click Decrypt. Export (in the Output folder will appear *.txt files)
- of Input and Output folders does not remove, translate directly *.txt and not renaming the store
- copy from Input folder translated *.txt files to the Output folder
- run TTG Tools.exe, press Auto (De) Packer, click Encrypt. Pack. Import (in the Output folder will appear translated *.landb)
and ttarchext.exe -b -V 7 24 "1.ttarch" "new" for rebuilding.

but first need to wait when luigi recompiles ttarchext and add to program the key of game, or do it yourself (open source code C)
- Jurassik Park (when will be released)

OK thanks for the instructions I'll give it a try. But first the key will have to be added to the ttarchtext extractor before I try anything right? I'm not exactly sure how to add the key to the program either... Much to learn I still have. Maybe I will have to wait for Luigi to recompile.
## Post #6
- Username: dezmand07
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 24, 2011 2:22 pm
- Post datetime: 2011-11-26T21:19:23+00:00
- Post Title: Jurassic Park the game .ttarch

you can still ask the Russian guys compiled ttarchext, they've opened the game resources [http://www.zoneofgames.ru/forum/index.p ... opic=24236](http://www.zoneofgames.ru/forum/index.php?showtopic=24236)
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-11-29T01:47:58+00:00
- Post Title: Jurassic Park the game .ttarch

Aluigi has updated his TTARCHEXT tool so now it can extract the archives.

[http://aluigi.altervista.org/papers.htm#ttarchext](http://aluigi.altervista.org/papers.htm#ttarchext)
## Post #8
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-11-29T05:19:41+00:00
- Post Title: Jurassic Park the game .ttarch

> Reply from brendan19
>
> Aluigi has updated his TTARCHEXT tool so now it can extract the archives.

http://aluigi.altervista.org/papers.htm#ttarchext
I tried extracting the archive using the updated version and everything seems to work with no error,but the output folder I specify always remains empty after running the command.  Any suggestions?
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-11-29T10:42:33+00:00
- Post Title: Jurassic Park the game .ttarch

Try this batch script I made up:

```
mkdir "Output"
for %%i in (*.ttarch) DO ttarchext.exe -m 48 "%%i" "Output"
```
## Post #10
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-11-29T15:56:30+00:00
- Post Title: Jurassic Park the game .ttarch

> Reply from brendan19
>
> Try this batch script I made up:
Code: Select all@echo off
mkdir "Output"
for %%i in (*.ttarch) DO ttarchext.exe -m 48 "%%i" "Output"
I ran the script and nothing happened, then made a batch file and only an empty output folder was created. Am I doing something wrong or was I supposed to specify paths in the script?
## Post #11
- Username: OneTwo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2011 7:01 pm
- Post datetime: 2011-11-30T11:13:03+00:00
- Post Title: Jurassic Park the game .ttarch

Hi. Help, please, how to pack "*.ttarch" type: "_pc_data.ttarch", "_pc_tx.ttarch" back. I used options "-b -V 7 48" but the archives are of a different size (uncompressed) and playing with them will not start.
## Post #12
- Username: irondragon01
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 11, 2011 1:18 am
- Post datetime: 2011-12-10T18:52:55+00:00
- Post Title: Jurassic Park the game .ttarch

> Reply from OneTwo
>
> Hi. Help, please, how to pack "*.ttarch" type: "_pc_data.ttarch", "_pc_tx.ttarch" back. I used options "-b -V 7 48" but the archives are of a different size (uncompressed) and playing with them will not start.
I have same problem too
original 1_JurassicPark101_english_pc_data.ttarch file is 77.050 KB
and translated 1_JurassicPark101_english_pc_data.ttarch file is 219.577 KB 
how we will compressed this file?
## Post #13
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-12-11T12:45:53+00:00
- Post Title: Jurassic Park the game .ttarch

Extract the TTARCHEXT.zip into a new folder called TTARCHEXT.

Then copy the .ttarch files you want to extract into the TTARCHEXT folder we made.

Save the batch script I made into the TTARCHEXT folder and name it "Batch.bat"

Then run Batch.bat and it should extract everything with no problem.
## Post #14
- Username: irondragon01
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 11, 2011 1:18 am
- Post datetime: 2011-12-11T15:30:38+00:00
- Post Title: Jurassic Park the game .ttarch

> Reply from brendan19
>
> Extract the TTARCHEXT.zip into a new folder called TTARCHEXT.

Then copy the .ttarch files you want to extract into the TTARCHEXT folder we made.

Save the batch script I made into the TTARCHEXT folder and name it "Batch.bat"

Then run Batch.bat and it should extract everything with no problem.
Ok I have done it

now how i rebuild the .ttarch file without game is not crushing.
## Post #15
- Username: onur38
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 13, 2012 3:24 am
- Post datetime: 2012-01-12T20:11:48+00:00
- Post Title: Jurassic Park the game .ttarch

Thanks, but back have installed the game does not turn. Why?
## Post #16
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2020-03-03T19:17:21+00:00
- Post Title: Re: Jurassic Park the game .ttarch

Excuse me, but I’d like to know more about the sound effects for the game, specifically the dinosaur sounds as well as the original elements from the film. I don’t have access to the game, unfortunately, and I’d like some help getting the sounds, if it’s possible.
