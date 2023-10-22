## Post #1
- Username: xanzen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 19, 2006 11:47 am
- Post datetime: 2006-04-19T03:52:50+00:00
- Post Title: game client vfs extractor

hi,
can someone help make the .vfs extractor
I want to be able to view the .vfs file and edit the scripts contained inside.

regards.

ps.(as the data.vfs is very big ~1.2GB, i dont have anything to attached here  )

edited:grr the zip file is bigger than 256kb, cant upload here, ill try to email them
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-19T05:48:17+00:00
- Post Title: game client vfs extractor

ive been able to rip textures out of the VFS file, but not yet
seen any scripts =o

(the main textures ive been able to rip out is in PNG format)

Edit: there are lots of 1024x1024 PNG images in this archive,
im starting to belive this is their main use of texture format.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-19T05:53:02+00:00
- Post Title: game client vfs extractor

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-19T06:01:48+00:00
- Post Title: game client vfs extractor

I was desperate and downloaded the demo instead =X
(too bad it was a 500 mb download, so it may be to much for slower connections)

the information so far on the format is that it does not use binary
for the file inputs, its stored like ascii in the header,
like 10231 4000000

where the first value is offset and next is file length. should be
no big deal in coding an archive reader for this. nothing is
encrypted or packed. (As far as i can see).
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-19T06:07:05+00:00
- Post Title: game client vfs extractor

hi there. ive cutted the VFS header. here it is, and some junk data at
the end of file which is a file, but i dont know the format of it yet.

you can see its structured with ascii values instead of binary,
but i dont really know the purpose of all these values yet, after
a closer look it might not just be so simple as Offset+Length,
they seem to have more than that.

Edit: hmms....the same structure of the header is found straight after a TGA
file in the archive, im not sure if this is a archive structure anymore,
maybe its a fileformat itself?

but where is the archive index stored then .....=o ....im still investigating.


Edit again: the archive DOES NOT contain index. the whole index
of the archive is stored in data.inf file located in the root of the game.
[data.rar](https://xentaxbackup.github.io/file/706_data.rar)
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-19T06:54:38+00:00
- Post Title: game client vfs extractor

i think its solved....

there are alot of junkdata in the index, but i think i have distinguished the correct values. and this follows for all entries in the archive.
[hithere.gif](https://xentaxbackup.github.io/file/707_hithere.gif)
## Post #7
- Username: xanzen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 19, 2006 11:47 am
- Post datetime: 2006-04-20T00:31:54+00:00
- Post Title: game client vfs extractor

wow thanks guys for trying to solve this, especialy Strobe, and yes there is a data.inf file in root directory but it is ard 2.6 mb.

edited:err sry Strobe i just realize u already know abt the data.inf lol, my bad, just woke up and reaidn gur post so im kinda slow haha
[data.inf.zip](https://xentaxbackup.github.io/file/709_data.inf.zip)
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-20T01:28:21+00:00
- Post Title: game client vfs extractor

Hehe, now just someone has to make a script for it. or you could use Jaeder Naub to rip out all textures.
(but it was the scripts you wanted, but i have not yet found any scripts
in this archive. hmmms.)
## Post #9
- Username: xanzen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 19, 2006 11:47 am
- Post datetime: 2006-04-20T03:48:44+00:00
- Post Title: game client vfs extractor

err i thought u gonna make the script for me? hehehe,
btw yea im pretty sure the script is in there, heres the screenshot from PE explorer, hopefully this helps. Look at the highlighted area.

ps. im using ur Jaeder Naub now gonna take a while to rip 1.2gb Zzzzz
nice stuff btw:)
[script.jpg](https://xentaxbackup.github.io/file/711_script.jpg)
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-21T10:20:14+00:00
- Post Title: game client vfs extractor

;DDDD Yes....jaeder will probably take a HELL of a long time on that archive. i really hope you disabled all other stuff than whats in the archive.

if i remember correctly, only leave on Ogg, BMP, JPEG, PNG , DDS and Targa. thats what you will find.

(atleast thats what i found), still takes some time though :X

and, there is a bug in the DDS saver (STILL!!!!) that will save some textures as 5mb or so, when it really is 1kb.(sigh), nothing you can do about it
more than wait until the next version :/, or wait for the mex-script.

im still looking on this script file you say they have. maybe its easy to add
a ripper for that one too. =o
## Post #11
- Username: xanzen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 19, 2006 11:47 am
- Post datetime: 2006-04-21T14:10:59+00:00
- Post Title: game client vfs extractor

hehe i got only dds and png so far, i stopped halfway because i need to restart computer lol.
anyway i got a chance to look at the some of the new monsters' texture tht are on the game's new map.i cant go to new map because i must pay for it:(
but oh well thts another story....
oh btw b4 u make the script ripper of it, is it possible to edit the script and put it back into the data.vfs file because if its not possible or to complicated then
it will be useless to rip it :/

oh well for the meantime, ill just enjoy the textures hehe, and how to open a .dds file??

edited:hehe i look at others thread and found abt the .dds viewer thx anyway :p
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-21T16:27:09+00:00
- Post Title: game client vfs extractor

if the script file will be rippable they would be injectable as well,
but would be a little more complicated through jaeder naub.
and im gonna add the script ripper anyway, just for the compability reasons   , but maybe someone has a better way too reinject the scripts
when they are modified. ill get back to this.
