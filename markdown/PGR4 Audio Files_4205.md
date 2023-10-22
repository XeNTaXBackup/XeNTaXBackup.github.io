## Post #1
- Username: Mobius
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 12, 2010 8:07 pm
- Post datetime: 2010-03-12T13:28:58+00:00
- Post Title: PGR4 Audio Files

Hey guys.

PGR4 seems to store its music files as lossy .wma  

But, what I'm after is the menu music which seems to be layered. It isn't a single track that is played in the background but depending on which menu you're in and whether you go forward or back throught the menus, you get a new layer of the music playing or a layer less. These layers must be stored somewhere. I'm hoping to get these layers so I can produce a custom version of the music for personal use which I've done with many games that use layering.

All I could find were 3 files called:

UI.dat (11KB)
UIMusic.dat (23KB)
UIMusicBank.baf (16MB)

[>>Download<<](http://hotfile.com/dl/32415446/a713c6f/Audiorip.rar.html)


I was hoping that the layers were stored somewhere in one of these but I've failed to open any of them. I've tried quite a few extractors but to no avail and I'm useless with Hex.

Any help would be much appreciated
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-12T21:14:02+00:00
- Post Title: PGR4 Audio Files

This type of bank file uses XMA 48hz, you can find the headerless tracks after DATA in hex, cut the start of the xma stream at 08000 till the next DATA segment, add xma header and decode with towav.
## Post #3
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-05-16T17:44:37+00:00
- Post Title: PGR4 Audio Files

I've extracted these from the banks and here they are:
[http://bxaimc.hcs64.com/Project%20Gotha ... 20(XMA).7z](http://bxaimc.hcs64.com/Project%20Gotham%20Racing%204%20Menu%20BGM%20Bank%20%28XMA%29.7z)

If you want to play these, you're gonna need to ToWav. But before you can use that, you need to change the headers so that ToWav would recognize them since these have some custom header. The original header is 100 bytes long (0x64) so cut that out and paste this header onto each of them and run ToWav on them.
[http://bxaimc.hcs64.com/genericxmaheader.hed](http://bxaimc.hcs64.com/genericxmaheader.hed)
## Post #4
- Username: Mobius
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 12, 2010 8:07 pm
- Post datetime: 2010-05-16T19:26:42+00:00
- Post Title: PGR4 Audio Files

I have no idea how to do that
## Post #5
- Username: V12POWER
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 11, 2021 4:35 am
- Post datetime: 2021-08-11T00:57:58+00:00
- Post Title: PGR4 Audio Files

> Reply from bxaimc ↑Mon May 17, 2010 1:44 am at Mon May 17, 2010 1:44 am
>
> 
I've extracted these from the banks and here they are:
http://bxaimc.hcs64.com/Project%20Gotha ... 20(XMA).7z

If you want to play these, you're gonna need to ToWav. But before you can use that, you need to change the headers so that ToWav would recognize them since these have some custom header. The original header is 100 bytes long (0x64) so cut that out and paste this header onto each of them and run ToWav on them.
http://bxaimc.hcs64.com/genericxmaheader.hed

your link doesnt work, im trying to decode the files inside the .baf container too but without the header it's impossible. I couldnt come across any "generic" xma header on the web, and xma transform gives me weird errors with these files. so yours is the only option left I think, can you paste it somewhere else?
