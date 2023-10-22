## Post #1
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2010-12-23T17:40:19+00:00
- Post Title: The 3rd Birthday (*.pkg)

Hi guys i was checking this cool game the other day but i found that all
the files are in a single .pkg file i test a script from aluigi but dont work
this is a PSP game, if you open the big file with Hex you will find this:

[](http://img220.imageshack.us/i/pkgthe3dr.png/)

But besides that i dont know how to open that file =/

So any one want to take a look please ?

Thanks in advance. 

Edit: My Apologies i didnt upload the sample beause its a 1.3 GB file =/ , i will see 
if can upload later.
## Post #2
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-12-24T12:09:29+00:00
- Post Title: The 3rd Birthday (*.pkg)

The pkg doesn't seem to be compressed itself and just a container format, however I don't know how to tell where a file starts and ends. The fsd file has most likely something to do with it.
I've attached the first 7000h bytes of the pkg file (the png) and the fsd file.
[3rd.rar](https://xentaxbackup.github.io/file/3712_3rd.rar)
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-24T14:48:51+00:00
- Post Title: The 3rd Birthday (*.pkg)

Merry Christmas!
*.pkg file is the same format used in psp Evangelion : Jo.
Did you try Noesis?
[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)

 Wish you the best for the holiday seasons!
## Post #4
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-12-24T16:26:25+00:00
- Post Title: The 3rd Birthday (*.pkg)

Although the file extension is the same, the format doesn't seem to be. At least Noesis says that "the file could not be previewed".
Anyway, the pkg file is divided into segments of size 0x800 and the fsd refers to the files not in actual addresses, but in segment numbers.
E.g. there's a PNG file at address 0x7000, in the fsd, that's 0x0E (0x7000/0x800 = 0xE)

The problem now is that there is no file list and you can't easily figure out the file extension of the files. 

I've written a simple extractor which will basically separate the pkg into different files. Make sure the pkg and fsd files are in the same folder as the contents of the rar and start extract.bat to do the job.
The program will use the first four bytes of each file to guess the format, if you want it to recognize more formats, add them to the fileformats.ini (there's examples for png and psmf). Unknown files end up with ".unk"

Maybe there's a better solution for this, but that's all I came up with :/
[3rdExtractor.rar](https://xentaxbackup.github.io/file/3715_3rdExtractor.rar)
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-24T16:54:57+00:00
- Post Title: The 3rd Birthday (*.pkg)

if someone decrypts the eboot on their psp the file table should be in there with names.
## Post #6
- Username: Aerow
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 05, 2010 4:32 pm
- Post datetime: 2010-12-24T23:59:23+00:00
- Post Title: The 3rd Birthday (*.pkg)

> Reply from chrrox
>
> if someone decrypts the eboot on their psp the file table should be in there with names.
The eboot is already decrypted.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-25T00:34:12+00:00
- Post Title: The 3rd Birthday (*.pkg)

then it needs to be decompressed. there are no strings that i can see so its still compressed.
## Post #8
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-12-25T01:14:23+00:00
- Post Title: The 3rd Birthday (*.pkg)

Without going into any detail, whether the eboot is encrypted or not depends on the *ahem* "version" you're using.
In any case, the decrypted eboot does contain many strings, but none of them seem to be related to the file table belonging to the pkg/fsd.
## Post #9
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-12-25T01:37:12+00:00
- Post Title: The 3rd Birthday (*.pkg)

it's normal in PSP games not to have the filenames...don't ask me why   

The only thing you could do is keep investigating the headers and discover as much filetypes you can, maybe dividing them by folders will be easier to browse
## Post #10
- Username: kenshinjeff2
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 22, 2010 9:25 am
- Post datetime: 2010-12-27T00:16:33+00:00
- Post Title: The 3rd Birthday (*.pkg)

It seems that the rest of the files are encrypted. May I know how much of the fsd file was used to break the pkg file into smaller files? Also, why are the total filesizes different after extraction?
## Post #11
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-27T07:47:28+00:00
- Post Title: The 3rd Birthday (*.pkg)

3rd birthday uses a new encryption key, but can be decrypted with this tool
[http://www.psp-hacks.com/file/1931](http://www.psp-hacks.com/file/1931)

as for file listings, its true there doesnt appear to be any in the ELF/EBOOT

the game runs on the PSP Emulator decrypted, and I tried sniffing for file names.. no luck :\
## Post #12
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2010-12-27T20:56:04+00:00
- Post Title: The 3rd Birthday (*.pkg)

> Reply from kenshinjeff2
>
> It seems that the rest of the files are encrypted. May I know how much of the fsd file was used to break the pkg file into smaller files? Also, why are the total filesizes different after extraction?

The file table starts at 0x72C in the fsd, I have no idea what the data before it is.
Each file occupies 8 bytes in the table; the first 4 byte word stores the segment number (lower 20 bits) while the upper 12 bits are for something else. The word after that is always 1.

The total filesize is different because I forgot the last file. I'm not really motivated enough to fix it/continue since, well, there's no filenames and the interesting bits and pieces seem to be compressed files anyway.
