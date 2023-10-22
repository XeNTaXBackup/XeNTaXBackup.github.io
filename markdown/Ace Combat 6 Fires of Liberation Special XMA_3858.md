## Post #1
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-11-11T19:12:38+00:00
- Post Title: Ace Combat 6: Fires of Liberation Special XMA

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-28T08:13:35+00:00
- Post Title: Ace Combat 6: Fires of Liberation Special XMA

Just downloaded the file just to see that you're right. Something isn't right with the interleave.

HOWEVER: I've discovered that when using the header from your file, the XMA files from LEGA Indiana Jones 2 for XBox 360 are now perfectly decodable with a little trick (see [http://aluigi.freeforums.org/post8737.html](http://aluigi.freeforums.org/post8737.html))
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-28T15:08:53+00:00
- Post Title: Ace Combat 6: Fires of Liberation Special XMA

I've looked at the file a bit closer and was first confused about the chunk cycle. I don't know if it's actually called that way but that's what I call the repeating sequence of a defined number of chunks that decode the different channels. For example a file with 400 byte interleave has the cycle 400:400 (l:r).
I first thought the cycle from the Ace Combat 6 file was F000:0800:0800 (front:center/LFE:rear) but then I found a placeholder chunk (FF FF FF FF...) in between the F000 chunk. I checked the structure again and now I'm pretty sure that the chunk cycle is E800:0800:0800:0800 (front:center/LFE:middle:rear), which makes the file an 8 channel stream.    That's why my method 'delete the first chunks till the sequence repeats' doesn't work here as toWAV only supports 6 channels. 
I don't know how toWAV decodes a 6ch XMA but apparently it determines the length of the first chunk by searching for the placeholder chunk and then decodes the channels successively with the same interleave. No problem if toWAV detects the chunk correctly as we can successively delete the next chunk until all channels are processed correctly. But in the above file you don't see a placeholder chunk between E800 and 0800 until cycle 3 (check it out for yourself). So toWAV will identify a chunk length of F000, which isn't even included in the cycle. 
So if someone could write a little program that safely detects the cycle length of a multichannel XMA file and then creates 3 files (for 6ch) or 4 files (for 8ch) that would do the following steps:

```
2 . add placeholder chunks for unrecognizable segments
In the above example we could add an placeholder chunk of length 200 after each of the E800 segments, which would then become EA00 segments so that toWAV can  recognize the length correctly (basically that's just 'add 200 bytes of FF each cycle')
3. Create 3 or 4 files, which are 
   a) the corrected file from above
   b) corrected file without first chunk
   c) corrected file without second chunk
   d) corrected file without third chunk (only 8ch)
4. run toWAV
5. automatically delete the errornous decoded files
6. rename the decoded files correctly according to the channels
```


Could anyone write a little program in C that does the above? I don't think it's too difficult, only the identification of the chunks could be a little tricky.
THANKS!
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-28T15:27:45+00:00
- Post Title: Ace Combat 6: Fires of Liberation Special XMA

Im sure aluigi can do a program or you might want to PM zench. Anyways im really excited for a multuichanel xma method or proggie timo, i thank you for the research on this 

Heres the weird thing, why doesn't the original file decode where the header came from? pies file?
## Post #5
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-11-28T16:59:47+00:00
- Post Title: Ace Combat 6: Fires of Liberation Special XMA

I'd be very grateful if someone can make a script for me.

Your explanation makes sense Alpha; I've checked your interleaves and they are correct; also, the audio data starts getting screwed up after a few seconds, which justifies the fact that the placeholder has its first appearance in the third cycle.
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-11-30T12:47:00+00:00
- Post Title: Ace Combat 6: Fires of Liberation Special XMA

To finally get this in the right place, and because I have more news:
There are two types of stream in Ace Combat 6, the ones with fmt at 0xc (original XMA) and the ones with XMA2 there.  These both have trouble decoding in toWav.  I've extended my experimental parser xma_parse ([http://hcs64.com/files/xma_parse05.zip](http://hcs64.com/files/xma_parse05.zip)) to make dealing with these easier.

With the XMA2 ones, the solution I came up with is to rebuild them as XMA.  With xma_parse this is done as follows:
xma_test ace.xma -o 800 -b 10000 -d 1401800 -r ace.bin

-o 800 is the start of the first stream (the front channels, bass is at 1000, and back channels are at 1800)
-b 10000 specifies a block size of 10000 (as specified in the header at 0x2c)
-d 1401800 gives the size of the data chunk (which starts at 0x800, for the other streams at 1000 and 1800 technically we should use -d 1401000 and -d 1400800 since there is less valid data after the start offset)
-r ace.bin says to rebuild to a headerless XMA stream in ace.bin

For the original XMA ones, we can export them to headerless single stream files:
xma_test endtheme.xma -1 -o 800 -b 10000 -d 1b81000 -x ace_ending.bin

Note the -1 to indicate that this is original XMA, XMA1 rather than XMA2. Like the other it also has two other streams at 1000 and 1800. Note also the -x, which indicates an extraction rather than a rebuild. This produces a headerless XMA stream in ace_ending.bin.

Sorry this stuff is so manual, I didn't want to make a particular parser for the AC6 RIFFs just now, was more interested in digging into the stream layout itself.
And sorry for cross-posting this across creation, I've sort of been obsessed with it for several hours now...
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-02T13:06:46+00:00
- Post Title: Ace Combat 6: Fires of Liberation Special XMA

The question is: why doesn't this work with the files from LEGO Indy 2?
Here's an example: [http://www.sendspace.com/file/1lvwx4](http://www.sendspace.com/file/1lvwx4)
