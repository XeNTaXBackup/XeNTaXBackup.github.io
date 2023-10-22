## Post #1
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-06T09:25:17+00:00
- Post Title: Ultimate baseball Online *.dat

I am really desprate to modify a file in this archive. will some one please help me out.

.dat file type

its a free game u can get here [http://www.ultimatebaseballonline.com/](http://www.ultimatebaseballonline.com/)
[pak008.zip](https://xentaxbackup.github.io/file/842_pak008.zip)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-06T14:35:51+00:00
- Post Title: Ultimate baseball Online *.dat

The data is not compressed (In the example) you can extract it with a file ripper, anyway i searched NKZIP and i found it, but it's a PKZIP 2.04g
## Post #3
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-06T15:37:19+00:00
- Post Title: Ultimate baseball Online *.dat

could somone write a script for this? would be much appreciated, i have the game exe if you also need it. thanks
## Post #4
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-07T05:08:18+00:00
- Post Title: Ultimate baseball Online *.dat

Anyone?
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T07:00:05+00:00
- Post Title: Ultimate baseball Online *.dat

which of the graphic files you wish to modify in this archive?

(could possibly be done with my little injector)
## Post #6
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-07T07:02:20+00:00
- Post Title: Ultimate baseball Online *.dat

i think its a png, but not for sure.

I tried to inject a png but it didnt seem to work, the file name came out like this when i ripped it png_ 3284228_xxxx.png.
## Post #7
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-07T07:42:36+00:00
- Post Title: Ultimate baseball Online *.dat

so is there no luck for this archive?
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T08:27:30+00:00
- Post Title: Ultimate baseball Online *.dat

Arrgghhh..... the "xxxx" in the filename that has been ripped means the ripper
failed to detect the length of the PNG picture, and therefore cannot be reinjected. im working on a fix for this. as the PNG extractor can now
really detect the real length of them. ill just have to fix the naming 
parameters for the PNG extractor. ill get back to this
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T08:54:59+00:00
- Post Title: Ultimate baseball Online *.dat

[http://jaedernaub.ath.cx/jn191r.zip](http://jaedernaub.ath.cx/jn191r.zip)

New test version. this one should rip PNGs and save the length header
in the name also now.  (possibly with +-10 bytes accuracy, but should work for injecting anyway).

i hope
## Post #10
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-07T11:26:11+00:00
- Post Title: Ultimate baseball Online *.dat

wow thanks alot man!
## Post #11
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-07T12:10:23+00:00
- Post Title: Ultimate baseball Online *.dat

I tryed it out and it crupts the dat file, thanks for help though.
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T12:36:22+00:00
- Post Title: Ultimate baseball Online *.dat

There must be a way to bypass this corruption.
*really*. send me the file you are trying to inject and i can try to see whats wrong with it.......=o..

*upload here, or send to [vital_@hotmail.com](mailto:vital_@hotmail.com) *

im not giving up yet :X
## Post #13
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-07T12:45:22+00:00
- Post Title: Ultimate baseball Online *.dat

cool thanks alot man, ok here is the file im trying to inject.

Its a different dat file im trying to inject it into.
heres the link to it.
[http://www.megaupload.com/?d=FLXZT7TH](http://www.megaupload.com/?d=FLXZT7TH)
[png_ 3284228_ 1568.zip](https://xentaxbackup.github.io/file/844_png_ 3284228_ 1568.zip)
## Post #14
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T14:25:27+00:00
- Post Title: Ultimate baseball Online *.dat

Okay. the obvious reason on why it fails is because the original file is 1.5kb
big, and the file you are trying to inject is 5kb. 

however, i dont understand how that small picture can become 5kb, what encoder do you use?

the characteristics of the image you are trying to inject would be much smaller than it is. im gonna try to do some encoding tests. =o  *brb*

i tried encoding it without transparency, and it went 900 bytes big.
so, the question is, do you really need the transparency layer? =D
## Post #15
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-07T14:58:43+00:00
- Post Title: Ultimate baseball Online *.dat

No i dont need it as a transparency layer, i just need the circle to be red, 

I thought that was the problem too, so i tried injecting the original picture back in it and it still curupted it.
## Post #16
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T15:13:37+00:00
- Post Title: Hey.

I have the archive now. i will run some tests
and see if its the injector that fails to inject at the correct offset.
*brb* =X
## Post #17
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T15:32:16+00:00
- Post Title: Hey.

Try this image.

The injector made no errors. it injects as it should do.
if this image doesnt work , the game is just very piccy with the
archive and does not support what i call "lethal injections", the way to
inject files without actually rebuilding the archive.

but hopefully...this does.....
[vng_ 3284228_ 1568.png](https://xentaxbackup.github.io/file/845_vng_ 3284228_ 1568.png)
## Post #18
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-07T16:09:02+00:00
- Post Title: Hey.

game still crashes, guess ill have to wait for some one to write a script for it. thanks for the help.
## Post #19
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T16:13:34+00:00
- Post Title: Hey.

Stupid game! 
*bangs the head against the wall*
## Post #20
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-09-18T21:45:01+00:00
- Post Title: Hey.

could somone give this archive a try plz, thank you
## Post #21
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-10-26T09:30:25+00:00
- Post Title: Hey.

Finally got your injecter working, great work man. wish somone would help me out with this archive.
## Post #22
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-26T12:18:55+00:00
- Post Title: Hey.

Allright, I heard your plee, my son. 

I have found the time to take a brief look at your .dat format. And you are going to love this. The way to unpack or create the .dat archives has been right under your nose all the time! 

But let's keep you in suspence just a little while longer.  The format of the .dat archives (or NKZIP files) is as follows:

```
// Header

byte{16}    Magic Word (NKZIP)
byte{16}    Version or Name of the current .dat file
uint32{4}   Total size of actual filedata 
uint32{4}   Number of files in the archive

// For each file

untin32{4}   Size of file in bytes
byte{260}  Name of file (260 bytes reserved)

```


And this MexScript will open them and let you replace all files with your own (not changing names or anything, as the game will expect them to be in order right?). 

```
GetDString MW 16 0 ;
GetDString AN 16 0 ;
Get AllData Long 0 ;
Get FileNum Long 0 ;
For T = 1 To FileNum ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos PO 0 ;
Math PO += 1 ;
GoTo PO 0 ;
GetDString FileName 259 0 ;
SavePos FO 0 ;
Log FileName FO FS 0 FSO ;
Math FO += FS ;
GoTo FO 0 ;
Next T ;

```


See the attached example of a PNG and DDS file I could extract with MexCom from PAK008.dat and pak001.dat. 

Now here comes the funny bit. 


All of these .dat archives carry the way to pack and unpack .dat archives (or NKZIP files as I prefer calling them)!  Cryptic? Not in the least, what they all contain is the program that created them in the first place! 

CRDat.exe is the packer/unpacker the authors used to create the .dat archives. I assume it's short for CreateDat. 

I extracted the executable immediately with a hex editor when I saw it (and that's easy, as executables usually start with "MZ"). I tried to run it from command line and got a help response. 

```
CRDat d in-file
```


At that time I thought it a little strange, but tried to run it anyway.

This I then figured out :

The d stands for "decode". I tried it on the pak008.dat file and it neatly extracted all the files. 

```
CRDat d pak008.dat
```
 

To pack all the files in a directory, copy the CRDat.exe to that directory and start this from command line:

```
CRDat e YourPakFile.dat ThePakFileTitle
```


Brilliant isn't it! Well, the authors call it encode/decode, but there's nothing encoded or whatever, it's just a packer that does not even compress or anything. 

The CRDat.exe also packs itself in the new archive, along with stuff like a Windows link/short-cut to the CRDat.exe file and the Thumbs.dat system file. Sloppy! Sloppy! Sloppy!

When I looked at the properties of the CRDat.lnk file I saw the original paths of the authors as well as the syntax to use the CRDat file:

```
D:\BUILD\UBO_2006_ìˆ˜ë
```

[CRDat.zip](https://xentaxbackup.github.io/file/949_CRDat.zip)

[dat.zip](https://xentaxbackup.github.io/file/948_dat.zip)

[mm_01.png](https://xentaxbackup.github.io/file/947_mm_01.png)

[audience_00_lod copy.jpg](https://xentaxbackup.github.io/file/946_audience_00_lod copy.jpg)
## Post #23
- Username: wvsneek
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 06, 2006 5:19 pm
- Post datetime: 2006-10-28T14:58:59+00:00
- Post Title: Hey.

omg that is so sweet!! you just dont understand how much you have helped me man, i owe you big time, thanks alot man, great work!
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-28T15:04:26+00:00
- Post Title: Hey.

> Reply from wvsneek
>
> omg that is so sweet!! you just dont understand how much you have helped me man, i owe you big time, thanks alot man, great work!

If you've version 4.3 of MexCom you can also select the WIKI resources (in Load archive, or Options) and then you can also open these files. I've added the script to the WIKI database.
