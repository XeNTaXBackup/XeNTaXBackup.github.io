## Post #1
- Username: sephoroid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 16, 2014 8:42 pm
- Post datetime: 2014-07-16T16:35:23+00:00
- Post Title: I need help with Blacklist UMD file.

Hi
I want to make modification for splinter cell blacklist spy vs merc.
In order to finish my modification, I need to unpack and modify the dynamicwin.umd file.
I need to edit loadout.xml file, which is inside this dynamic umd.
Is there any way to edit dynamicwin.umd file?
If not, so is there a way to force the game, to use my custom loadoutconfig.xml instead of the one inside the UMD file?

Please, I need help with this alot.
Thank You for any response.
## Post #2
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2014-07-16T21:31:45+00:00
- Post Title: I need help with Blacklist UMD file.

I had a look at this game a while back, if I remember correctly the file you specified is just zlib compressed so offzip should give you something. If not you're probably out of luck, the newer splinter cell games use a heavily modified unreal engine 3 and the file formats are anything but straight forward, I believe one guy did make a bit of progress with conviction here [http://www.gildor.org/smf/index.php/topic,458.0.html](http://www.gildor.org/smf/index.php/topic,458.0.html) but never released anything.
## Post #3
- Username: sephoroid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 16, 2014 8:42 pm
- Post datetime: 2014-07-18T10:57:13+00:00
- Post Title: I need help with Blacklist UMD file.

I tried to use offzip.
File is being decompressed, but the game crashes when I try to run it. : \
Then I used packzip to compress it again but the packed file size is smaller than the original one.
So this means that durring decompression some data is being lost?
I don't know what to think about this : \
It seems that file is compressed with more than one type of compression.
Maybe someone knows if it is possible to force this game to use the file extracted from umd archive?
I rly need help with this : \
If someone is able to solve this, maybe I will be able to repay his effort ^_^
My modification would be rly improved if I could modify this single umd file : (
BTW, thx for Your reply ; )
## Post #4
- Username: superfruit86
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 29, 2022 8:38 am
- Post datetime: 2022-05-29T00:41:16+00:00
- Post Title: I need help with Blacklist UMD file.

Hey not sure if this is still being monitored six years later but HxD editor worked for me (just edit the blacklist.umd file directly) I wouldn't recommend changing file size though, I haven't tested, so keep the same number of bytes.
