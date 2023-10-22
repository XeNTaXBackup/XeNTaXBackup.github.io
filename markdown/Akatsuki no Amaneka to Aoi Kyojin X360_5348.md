## Post #1
- Username: maryjane
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 05, 2010 7:13 am
- Post datetime: 2010-11-03T23:04:46+00:00
- Post Title: Akatsuki no Amaneka to Aoi Kyojin X360

Well I'm working on a translation for this game, I've been able to translate the images and all, but I don't know how to put them back in the data.bin file.

Also the I'm not able to even extract a single thing from the scripts.bin file, and I would really like to.  Any help on this would be welcomed.

Heres the files:

Data.bin
[http://www.mediafire.com/file/0uznkp0qkdv3050/data.bin](http://www.mediafire.com/file/0uznkp0qkdv3050/data.bin)
Script.bin
[http://www.mediafire.com/file/clqfn55pn ... script.bin](http://www.mediafire.com/file/clqfn55pnton5v5/script.bin)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-03T23:48:04+00:00
- Post Title: Akatsuki no Amaneka to Aoi Kyojin X360

quickbms script i tested it on the script file.


```
get idstring long
endian big
get filestart long
get files long
get null long
savepos filetable
for i = 0 < files
goto filetable
get null long
get size long
get offset long
get nameoff long
savepos filetable
goto nameoff
get name string
log name offset size
next i


```
## Post #3
- Username: maryjane
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 05, 2010 7:13 am
- Post datetime: 2011-02-23T00:47:27+00:00
- Post Title: Akatsuki no Amaneka to Aoi Kyojin X360

Big thanks, and sorry on the very late reply back.  Had to install firefox again, and ended up losing my bookmarks.
## Post #4
- Username: maryjane
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 05, 2010 7:13 am
- Post datetime: 2011-03-09T18:19:13+00:00
- Post Title: Akatsuki no Amaneka to Aoi Kyojin X360

Ok I just finished translating it(pictures, and scripts).  Is there a way to inject it back into the .bin? sorry im a complete noob in this way

=============================

Note to chrrox much thanks for the extraction script XD
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-09T21:28:34+00:00
- Post Title: Akatsuki no Amaneka to Aoi Kyojin X360

well this seems just something for the new feature of quickbms 0.4.10 :)
create a file.bat containing the following line:
quickbms.exe -r -w

now make a backup copy of the archive and double-click on that file.bat and use it as you did for the extraction.
all the files will be automatically injected back in the archive.

I suggest you to delete the files that you didn't modify so that the process will be faster.
note that you cannot inject files bigger than the originals!
and note also that you need the latest version of quickbms!
## Post #6
- Username: maryjane
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 05, 2010 7:13 am
- Post datetime: 2011-03-09T22:54:51+00:00
- Post Title: Akatsuki no Amaneka to Aoi Kyojin X360

> Reply from aluigi
>
> well this seems just something for the new feature of quickbms 0.4.10 
create a file.bat containing the following line:
quickbms.exe -r -w

now make a backup copy of the archive and double-click on that file.bat and use it as you did for the extraction.
all the files will be automatically injected back in the archive.

I suggest you to delete the files that you didn't modify so that the process will be faster.
note that you cannot inject files bigger than the originals!
and note also that you need the latest version of quickbms!

Thanks for the info man you rock XD
## Post #7
- Username: maryjane
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 05, 2010 7:13 am
- Post datetime: 2011-03-12T22:57:40+00:00
- Post Title: Akatsuki no Amaneka to Aoi Kyojin X360

Ok it worked thanks man.  Only issue I'm having now is the scripts get bigger after translation.

They in the following format, and I'll upload one of each for you to look at.
*.WPB (Supposed to be a word perfect file, but word perfect won't open it)
*.WNL(What I found said it was a wireless markup language so I thought it would be set up like .xml documents, but sadly I couldn't open it w/ any .xml editor I have now)
*.WPH(Agian what I found wasn't much. Said it was a system file. Specifically a bios dealing w/ the EEPROM<-Way something I do know XD.  Also said to try and open it w/ a program caled "Phlash16.exe" didn't get it to open)

So here's the files below, and again sorry that I'm a noob. I'm looking into learning file layouts now so I don't have to bug some1 else w/ my problems. 

[http://www.mediafire.com/?34cq0dgrdlexrfz](http://www.mediafire.com/?34cq0dgrdlexrfz)

Here is a virus total scan b/c it is a pretty small batch of files and it would look suspicious to me as well. So with this let the suspicions be gone XD

[http://www.virustotal.com/file-scan/rep ... 1299970533](http://www.virustotal.com/file-scan/report.html?id=cba2b0b2c8f61ec3044982e2ebb8d8c9c8d6a2db70772915ed3f9fc0c4fb1096-1299970533)
## Post #8
- Username: maryjane
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 05, 2010 7:13 am
- Post datetime: 2011-04-07T21:03:35+00:00
- Post Title: Akatsuki no Amaneka to Aoi Kyojin X360

Can no1 tell me what exactly I can use to open and edit the files w/?
