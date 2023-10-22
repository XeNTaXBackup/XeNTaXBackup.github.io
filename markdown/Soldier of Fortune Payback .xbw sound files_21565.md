## Post #1
- Username: Hunter01
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 04, 2020 10:10 am
- Post datetime: 2020-01-04T03:08:55+00:00
- Post Title: Soldier of Fortune Payback .xbw sound files?

Hello everyone! I'm having an issue I was hoping I could get some help with since I can't figure out how to access these sound files. I've already looked through the forum and on the other game modding website xenhax and I was only able to find a single thread on how to access these [https://zenhax.com/viewtopic.php?t=10965](https://zenhax.com/viewtopic.php?t=10965)  In this thread someone mentions to use vgmstream and add a txth header to the vgstream folder and then run test.exe. I figured out how the program works, but I have no idea how to get or make this txth file. I've looked around again on the internet and couldn't find any specific instructions on how to do this. Any help would be appreciated! I've included an example of these sound files. 

[http://www.mediafire.com/file/n4hben138 ... B.zip/file](http://www.mediafire.com/file/n4hben13803fezx/SOFPB.zip/file)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-01-04T11:47:34+00:00
- Post Title: Soldier of Fortune Payback .xbw sound files?

Save this into a text file called ".vgmstream.txth" (don't forget initial dot) and put it in the same folder as the .xbw files:

codec = XBOX
codec_mode = 0
sample_rate = @0x18:LE$4
channels = @0x16:LE$2
start_offset = 0x48
num_samples = data_size

Rename your *.xbw files to *.vgmstream and they should play in Foobar with the vgmstream plugin installed, and y ou can convert them with that too.  Some of the audio files in your zip have additional header info so they won't play with the above method until you remove that extra header, so that the files start with "RIFF".
## Post #3
- Username: Hunter01
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 04, 2020 10:10 am
- Post datetime: 2020-01-05T19:23:59+00:00
- Post Title: Soldier of Fortune Payback .xbw sound files?

Hello again and thank you for you reply! So I followed your instructions just as you specified, but I'm still running into issues. I installed Foobar and installed the vgmstream plugin just as you said as shown here [http://www.wduwant.com/index_uploads/up ... 371d48.PNG](http://www.wduwant.com/index_uploads/uploads/860216371d48.PNG)  but when I attempt to run the file in the program I get this error [http://www.wduwant.com/index_uploads/up ... 215b49.PNG](http://www.wduwant.com/index_uploads/uploads/c9c215b49.PNG)  also I did both methods for the file name as well where I renamed both the extension and the file name itself to .vgmstream and it doesn't work in either way. I know that you mentioned some of the audio files wont play until I remove a extra header on certain audio files but how do I go about doing that?
## Post #4
- Username: lvs42
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 30, 2011 9:45 pm
- Post datetime: 2021-02-21T11:16:24+00:00
- Post Title: Soldier of Fortune Payback .xbw sound files?

Hey Hunter01, so did you ever manage to get those sound files working? I just did, thanks to the thread you linked in your first comment. So thanks for that . I didn't even have to use foobar, vgmstream did the entire job itself. If you're still having trouble, I can explain in more detail.
