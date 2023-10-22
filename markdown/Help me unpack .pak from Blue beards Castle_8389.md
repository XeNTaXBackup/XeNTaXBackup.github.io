## Post #1
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-02-23T07:17:14+00:00
- Post Title: Help me unpack .pak from "Blue beards Castle"

Hi, Guys
This is Fairy tale. I very like this story.
Please help me unpack. Thanks. 

game link:
1.[http://zmafia.com/games/113621-bluebear ... loads.html](http://zmafia.com/games/113621-bluebeard-s-castle-downloads.html)
or 
2.[http://www.bigfishgames.com/download-ga ... index.html](http://www.bigfishgames.com/download-games/15032/bluebeards-castle/index.html)
## Post #2
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-03-18T02:09:31+00:00
- Post Title: Help me unpack .pak from "Blue beards Castle"

This is the data.pak 16Hex screenshot.
How can I　analyse this pack file？Can anyone teach me where to start?
It seems to be very disorder.
[cutmap.jpg](https://xentaxbackup.github.io/file/5201_cutmap.jpg)
## Post #3
- Username: gambit37
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 05, 2010 11:27 am
- Post datetime: 2012-03-22T21:47:20+00:00
- Post Title: Help me unpack .pak from "Blue beards Castle"

I have this game. I'm no good with understanding file formats, but it looks like data.pak is encrypted. The XML file in the root folder of the game says this:

```
  <File Name="data.pak" ReadMethod="aes.decrypt" WriteMethod="aes.encrypt" KeyFile="funner{SharedLibrarySuffix}" /> 
</Crypto>
```

There are a bunch of DLLs at the root with names starting with "funner...", which is the engine used to create this game. Perhaps someone will be able to help you decrypt this file using this information? I'm sorry but it's not something I can help you with myself.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-22T23:48:34+00:00
- Post Title: Help me unpack .pak from "Blue beards Castle"

the following script for QuickBMS will decrypt the file in a zip one that you can open with any desired zip program:

```
encryption "aes" "\x86\x87\x03\xA9\x94\x3D\x73\xEF\x6B\xDF\x78\xAF\xA3\xEB\xA5\x38"
log "data.zip" 0 SIZE
```
## Post #5
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-03-23T08:59:23+00:00
- Post Title: Help me unpack .pak from "Blue beards Castle"

Thanks guys!
I used aluigi's script and QuickBMS, but data.zip can't open with zip ro rar.
This is the data.zip 16Hex screenshot. It seems to be very disorder too.
[02.jpg](https://xentaxbackup.github.io/file/5221_02.jpg)
## Post #6
- Username: gambit37
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 05, 2010 11:27 am
- Post datetime: 2012-03-30T21:55:04+00:00
- Post Title: Help me unpack .pak from "Blue beards Castle"

Yes, I tried this script too and it doesn't create a zip file. I think the decryption key is wrong.
I tried using Cheat Engine to see if I could get the decryption key during startup, but I couldn't work out how to use it, sorry.
