## Post #1
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-07-25T14:18:10+00:00
- Post Title: Help on *.rdp File with ELF header

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-27T18:44:03+00:00
- Post Title: Help on *.rdp File with ELF header

that file is only a container, the index file is another one.
the index is a file that contains all the names of the archived files plus their offsets and sizes so should be enough small and easy to find (it should contain some ".wav" strings in it).

if you can't find it post here the full list of files of the game
## Post #3
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-07-30T12:10:32+00:00
- Post Title: Help on *.rdp File with ELF header

i dont get it..what should i post? full list of the game? you mean the files?
so there is no luck for extraction the files inside?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-04T21:16:29+00:00
- Post Title: Help on *.rdp File with ELF header

He's saying the cut you posted is missing the lookup table, so things can't be extracted from it until that file is uploaded too - so what other files did you manage to rip (other than package.rdp)?
## Post #5
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-07T14:21:39+00:00
- Post Title: Help on *.rdp File with ELF header

Kenni, kenni, kenma 
Did not know you were here as well~

EDIT: I asked a buddy about it and he explained to me very well why and that this file cannot be unpacked.
It is just a binary file dump. The game has saved the offsets, names and length of the files in its code. When the game is started, it uses the PSP Firmware to check the LBA of the package.rdp and afterwards it just adds the relative offset of the file it wants to obtain. Woo~
He also told me there won't be any header or anything we can use to unpack this file as it is (as said) just a file dump.
