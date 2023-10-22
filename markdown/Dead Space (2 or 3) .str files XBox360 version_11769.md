## Post #1
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2014-08-11T18:37:21+00:00
- Post Title: Dead Space (2 or 3) .str files XBox360 version

Hi mates,

As you can know, Rick released a program to convert Dead Space 2  PC .str files (working like a charm with Dead Space 3 PC .str files as well): [here](http://svn.gib.me/public/visceral/trunk/)

but the problem is that this program won't work with .str files from XBox360 and gives this kind of message:

```
at StreamSetFile.Deserialize(Stream input)
at Program.Main(String[] args)
```


So, I tried to compare files from PC and files from XBox360 and, as far as I can tell, I think those archives have a difference about endianness (sould be the problem with the tool?). 

Here some pictures:

[Dead Space 3 PC]



[Dead Space 3 XBox360]



Now, I'm in search of someone that could help me to convert Rick's program to work with XBox360 .str files because I'm not very good in programing.

I'll not ask for more. I just want the converted "StrUnpack.exe" to decompress those XBox360 archives (as it's doing for PC ones). Next, I'll deal with the result by myself. Plus, I will not distribute the converted program because it's Rick's belonging at the first place.

PS: I can't post any original files (even a piece of it) on the forum because it could be against the rules (that changed recently). So, if you need anything, contact me via PM please.

I look forward to your early response.

Vosvoy
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2014-08-12T19:13:01+00:00
- Post Title: Dead Space (2 or 3) .str files XBox360 version

As far as I can remember (it was 3 years ago), we don't have X360 and PS3 bigfile.dat tool. Rick's tool wasn't worked well with console version (at least the game didn't start with repacked .dat file). Since than I don't know the tool was updated or not. So, if you cannot repack the .dat files, the repacked .str file cannot be bigger than the original was, but the original is compressed, and Rick's tool cannot create compressed file.
But the first chunk not compressed in your .str file, than this is not problem, but who knows what is after that.
## Post #3
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2014-08-13T11:34:42+00:00
- Post Title: Dead Space (2 or 3) .str files XBox360 version

> Reply from evin
>
> As far as I can remember (it was 3 years ago), we don't have X360 and PS3 bigfile.dat tool. Rick's tool wasn't worked well with console version (at least the game didn't start with repacked .dat file). Since than I don't know the tool was updated or not.

Oh yeah, silly me, Dead Space 2 main archives were .dat extension. But I could still be able to extract them with Rick's tool (Gibbed.Visceral.BigViewer). Same here with Dead Space 3, I've got the VivUnpacker tool from Ekey. But now I've got no idea what's the problem with those XBox360 .str files since it's only working on PC files (with Gibbed.Visceral.StrUnpack tool from Rick).

> Reply from evin
>
> So, if you cannot repack the .dat files, the repacked .str file cannot be bigger than the original was, but the original is compressed, and Rick's tool cannot create compressed file.

I don't want to repack those files afterwards, I just want these .sbk files which are inside .str archives and deal with their content by myself. I should have mentioned this before.

> Reply from evin
>
> But the first chunk not compressed in your .str file, than this is not problem, but who knows what is after that.

Maybe you don't see the problem on the picture but maybe you could see it on the original file? Could it be the difference of endianness in the XBox360 file that disturb the tool?  

So, if any kind soul would help me I can provide one of these files but not on the forum (send me a PM in this case). 
But I think the bigger part of the problem comes from the tool that wasn't made for XBox360 files and that's why I'm asking for somebody (or Rick himself?) that could edit it for me with the sources ([here](http://svn.gib.me/public/visceral/trunk/Gibbed.Visceral.StrUnpack)).

Many thank's for taking the time to answer evin, though.

PS: By the way, I think that I'm in the wrong section of the forum now... No?
## Post #4
- Username: Mo15
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 13, 2018 8:48 am
- Post datetime: 2018-01-19T18:26:54+00:00
- Post Title: Dead Space (2 or 3) .str files XBox360 version

Judging on how old the most recent message is on here i don't think i'm gonna get a response...

But i have managed to get the before mentioned str unpacker but there are no .exe or .bat files...so i'm at a bit of a loss on what to do. Does anyone still know what to do with these files?

I'll also attach the zip of the folder.
[Gibbed.zip](https://xentaxbackup.github.io/file/13819_Gibbed.zip)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-19T23:39:16+00:00
- Post Title: Dead Space (2 or 3) .str files XBox360 version

> Reply from Mo15
>
> But i have managed to get the before mentioned str unpacker but there are no .exe or .bat files...
binaries attached to this post   
[viewtopic.php?p=51768#p51768](http://forum.xentax.com/viewtopic.php?p=51768#p51768)
## Post #6
- Username: Mo15
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 13, 2018 8:48 am
- Post datetime: 2018-01-19T23:56:56+00:00
- Post Title: Dead Space (2 or 3) .str files XBox360 version

> Reply from AceWell
>
> Mo15 wrote:But i have managed to get the before mentioned str unpacker but there are no .exe or .bat files...
binaries attached to this post   
viewtopic.php?p=51768#p51768

Yay i can finally go through the str files 

Thank you very much for helping me
