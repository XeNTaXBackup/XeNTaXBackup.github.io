## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-28T11:43:16+00:00
- Post Title: Skate 3 - *.mus/*.mpf

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-05-28T15:18:32+00:00
- Post Title: Skate 3 - *.mus/*.mpf

This mus file contains the new EA packed XMA variant thats decodable by ea multi xma. However like EA's older codec XA the music is split up into many 1-3 second segments, each segment has to he unpacked from the packed compression to XMA2, then run the segments through XMA parse to rebuild and fix the xma2 for errors and glitches, add header 48hz and decode with towav! 

hard part is many segments to extract. The decoding offset shouldn't be too hard to figure out for you alpha
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-29T02:17:02+00:00
- Post Title: Skate 3 - *.mus/*.mpf

wtf  I didn't know you were into EA's stuff. Well, THANKS for this 
Files are the sample rate of the list btw. Isn't there a way to extract ALL of the files simultaneously? Someone should write a script for this!
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-29T02:26:28+00:00
- Post Title: Skate 3 - *.mus/*.mpf

Wait, I've tried this - leaving the header untouched and starting at the first data block, ea_multi_xma extracts only around 54kb of data - am I doing something wrong?
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-29T04:23:26+00:00
- Post Title: Skate 3 - *.mus/*.mpf

Proceeding seems right, but how do I decode these files now? Sticking an xma header to these produces glitches, while some of the stream seems ok. Do I still need to parse them? A little help would be nice here.
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-05-29T08:19:36+00:00
- Post Title: Skate 3 - *.mus/*.mpf

Yes use xma test to rebuild the file with the rebuild command
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-29T14:31:08+00:00
- Post Title: Skate 3 - *.mus/*.mpf

The command "xma_test Game_Stream.mus_stream1 -r Game_Stream.mus_stream1.xma" gives back a parse error. What's wrong?
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-31T14:51:00+00:00
- Post Title: Skate 3 - *.mus/*.mpf

can anyone else please try this? Thanks.
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-05-31T14:57:58+00:00
- Post Title: Skate 3 - *.mus/*.mpf

Did you try adding an extension to the file input?
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-31T16:05:53+00:00
- Post Title: Skate 3 - *.mus/*.mpf

Same result 
HCS, yould you maybe take a look please? Would be nice.
