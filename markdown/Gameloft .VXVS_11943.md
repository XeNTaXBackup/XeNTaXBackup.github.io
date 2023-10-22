## Post #1
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-09-12T11:44:30+00:00
- Post Title: Gameloft .VXVS

Hello everyone  

I need sounds from Asphalt 8 game  
Some sounds are in .wav (playable) condition,but engine sounds are in .VXVS format.
I beleive It's an archive with .wav sounds

Please,help me,or tell me,what should i do to decrypt .VXVS format  

Here's an example
[http://www.mediafire.com/download/aub3c ... SOUNDS.rar](http://www.mediafire.com/download/aub3c2o2di0217m/ASPHALT8_ENGINE_SOUNDS.rar)
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-12T13:42:34+00:00
- Post Title: Gameloft .VXVS

Hmm, Vox? It's not the same Vox Native format used in previous games that uses Vox. However, it seems this version is easier to get the audio out of than the previous versions. Read tags in RIFF format (4-byte tag ID, 32-bit little endian length of contents, contents), and find the Data tag. Dump the contents of that tag and you should get a .wav file. Note this tag doesn't seem to have a length, and it is the last tag in the file, so dump the remainder of the file from that point.
## Post #3
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-09-12T17:30:59+00:00
- Post Title: Gameloft .VXVS

> Reply from GMMan
>
> Hmm, Vox? It's not the same Vox Native format used in previous games that uses Vox. However, it seems this version is easier to get the audio out of than the previous versions. Read tags in RIFF format (4-byte tag ID, 32-bit little endian length of contents, contents), and find the Data tag. Dump the contents of that tag and you should get a .wav file. Note this tag doesn't seem to have a length, and it is the last tag in the file, so dump the remainder of the file from that point.

Whoah...thanks for info!  
but i really have no idea how to work with such data,dump it and everything else,mabye because I am a 3D modeller and never worked with decryption\encryption before...
If it's not hard,could you help me to understand it? Like which software and how I should use...
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-09-13T16:58:08+00:00
- Post Title: Gameloft .VXVS

For extracting wav files, you can use Dragon Unpacker [https://www.elberethzone.net](https://www.elberethzone.net). It has function called HyperRipper. You will not get the right filenames, but it's better and faster then manually extracting them.

[](http://2i.sk/fcd385af7c)
## Post #5
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-09-13T17:55:21+00:00
- Post Title: Gameloft .VXVS

> Reply from merlinsvk
>
> For extracting wav files, you can use Dragon Unpacker https://www.elberethzone.net. It has function called HyperRipper. You will not get the right filenames, but it's better and faster then manually extracting them.

Thank you,man!You rock!
## Post #6
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-14T16:22:29+00:00
- Post Title: Gameloft .VXVS

Huh, I thought all the wave files were packed into one big wave file. Apparently they're still doing the "join the data together" thing they were doing previously. Names are in the segments chunk, I believe.
## Post #7
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-09-15T13:56:29+00:00
- Post Title: Gameloft .VXVS

> Reply from GMMan
>
> Huh, I thought all the wave files were packed into one big wave file. Apparently they're still doing the "join the data together" thing they were doing previously. Names are in the segments chunk, I believe.

If it's not hard,could you please look at this too...?  
Dragon unpacker gave me nothing here...
[viewtopic.php?f=17&t=11898](http://forum.xentax.com/viewtopic.php?f=17&t=11898)
