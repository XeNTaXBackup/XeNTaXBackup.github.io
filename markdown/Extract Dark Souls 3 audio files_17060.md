## Post #1
- Username: Swennet
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 22, 2013 4:50 am
- Post datetime: 2017-09-24T16:13:50+00:00
- Post Title: Extract Dark Souls 3 audio files?

Sorry for possibly asking something that has already been mentioned somewhere on this forum, but I haven't found any clear guide on how to do this.

How would I go about extracting only the audio files for Dark Souls 3? Last time I tried this I ended up with unusable FSB/ogg files.

Could anyone please provide or link to a step-by-step guide on how to rip all the audio from Dark Souls 3 in a usable format?
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-09-26T10:27:45+00:00
- Post Title: Extract Dark Souls 3 audio files?

Download these two tools first.

[Dark Souls III FSB Ripping](https://mega.nz/#!BQ8XWaRL!Ca0uxvnQC7wUgiKAO9X1TK4nB4bDpT-D7fzOH2zf1iI)

Copy all of the .fsb files from your Dark Souls III installation folder into the "FSBExt" folder and then run the "Decrypt Dark Souls 3 FSB.bat" file

This will decrypt all the .fsb audio files.

Once this has been completed, copy the newly created decrypted FSB files which have the "_crypt.fsb" in their filename into the FMOD Extractor folder and run the "FMOD Extractor.bat" file.

This will extract and convert all of the individual audio files inside the .fsb into PCM WAV.

Enjoy
## Post #3
- Username: Rozekail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 01, 2017 7:55 am
- Post datetime: 2017-12-08T00:31:45+00:00
- Post Title: Extract Dark Souls 3 audio files?

> Reply from brendan19
>
> 

Copy all of the .fsb files from your Dark Souls III installation folder into the "FSBExt" folder and then run the "Decrypt Dark Souls 3 FSB.bat" file

This will decrypt all the .fsb audio files.

Once this has been completed, copy the newly created decrypted FSB files which have the "_crypt.fsb" in their filename into the FMOD Extractor folder and run the "FMOD Extractor.bat" file.

This will extract and convert all of the individual audio files inside the .fsb into PCM WAV.

Enjoy

I'm pretty new here, but would a similar process work for Bloodborne's audio files? I suppose the only way to know for sure would be to know if their audio files were encrypted/formatted exactly the same or not. But I've got the .fsb files and am trying to convert them into something usable, but absolutely nothing works, so far. I even tried your method, and while they converted to the "_crypt.fsb" easily enough, the FMOD Extractor portion returns an "Unsupported file or audio format."

If you've got any advice, I'd appreciate it!
## Post #4
- Username: Sanadsk
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 20, 2014 5:25 am
- Post datetime: 2017-12-08T00:55:36+00:00
- Post Title: Extract Dark Souls 3 audio files?

> Reply from Rozekail
>
> brendan19 wrote:

Copy all of the .fsb files from your Dark Souls III installation folder into the "FSBExt" folder and then run the "Decrypt Dark Souls 3 FSB.bat" file

This will decrypt all the .fsb audio files.

Once this has been completed, copy the newly created decrypted FSB files which have the "_crypt.fsb" in their filename into the FMOD Extractor folder and run the "FMOD Extractor.bat" file.

This will extract and convert all of the individual audio files inside the .fsb into PCM WAV.

Enjoy 

I'm pretty new here, but would a similar process work for Bloodborne's audio files? I suppose the only way to know for sure would be to know if their audio files were encrypted/formatted exactly the same or not. But I've got the .fsb files and am trying to convert them into something usable, but absolutely nothing works, so far. I even tried your method, and while they converted to the "_crypt.fsb" easily enough, the FMOD Extractor portion returns an "Unsupported file or audio format."

If you've got any advice, I'd appreciate it!

Hi there!
So I have been working for quite a while with the Bloodborne files and got a good understanding of what the problem with its sound files is.
The sound files inside are .at9 which are PS4 ATRAC9 sound files.
Now the thing is with these files is that currently, there isn't a way to extract those .at9 files with their proper headers , as the FSB extractors put a normal .WAV header on them that doesn't have full information, so they can't be converted or played.
Alot of people are trying their hands on extracting them properly but in the time being, there is no way to do so.
I am in contact with lots of people about this so hopefully we will get results soon!
## Post #5
- Username: Rozekail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 01, 2017 7:55 am
- Post datetime: 2017-12-08T01:08:11+00:00
- Post Title: Extract Dark Souls 3 audio files?

> Reply from Sanadsk
>
> Rozekail wrote:brendan19 wrote:

Copy all of the .fsb files from your Dark Souls III installation folder into the "FSBExt" folder and then run the "Decrypt Dark Souls 3 FSB.bat" file

This will decrypt all the .fsb audio files.

Once this has been completed, copy the newly created decrypted FSB files which have the "_crypt.fsb" in their filename into the FMOD Extractor folder and run the "FMOD Extractor.bat" file.

This will extract and convert all of the individual audio files inside the .fsb into PCM WAV.

Enjoy 

I'm pretty new here, but would a similar process work for Bloodborne's audio files? I suppose the only way to know for sure would be to know if their audio files were encrypted/formatted exactly the same or not. But I've got the .fsb files and am trying to convert them into something usable, but absolutely nothing works, so far. I even tried your method, and while they converted to the "_crypt.fsb" easily enough, the FMOD Extractor portion returns an "Unsupported file or audio format."

If you've got any advice, I'd appreciate it!

Hi there!
So I have been working for quite a while with the Bloodborne files and got a good understanding of what the problem with its sound files is.
The sound files inside are .at9 which are PS4 ATRAC9 sound files.
Now the thing is with these files is that currently, there isn't a way to extract those .at9 files with their proper headers , as the FSB extractors put a normal .WAV header on them that doesn't have full information, so they can't be converted or played.
Alot of people are trying their hands on extracting them properly but in the time being, there is no way to do so.
I am in contact with lots of people about this so hopefully we will get results soon!

I'm glad to know I'm not just entirely incompetent. I hope to see some results soon, as well! I know you've got a fairly busy schedule, but is there any chance you were planning on making any sort of tutorial for extracting/viewing the files? The characters/enemies/objects/buildings, that is. Blender (and to a lesser extent, Noesis) give me headaches, haha.

Edit: Sorry, forgot that this was an audio thread. I'll make sure to continue non-audio conversations either in PMs, or in other sections.
## Post #6
- Username: Sanadsk
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 20, 2014 5:25 am
- Post datetime: 2017-12-08T01:15:07+00:00
- Post Title: Extract Dark Souls 3 audio files?

> Reply from Rozekail
>
> 

I'm glad to know I'm not just entirely incompetent. I hope to see some results soon, as well! I know you've got a fairly busy schedule, but is there any chance you were planning on making any sort of tutorial for extracting/viewing the files? The characters/enemies/objects/buildings, that is. Blender (and to a lesser extent, Noesis) give me headaches, haha.

Edit: Sorry, forgot that this was an audio thread. I'll make sure to continue non-audio conversations either in PMs, or in other sections.

Ah sure thing...I sent you a PM
## Post #7
- Username: Butter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 09, 2017 11:32 am
- Post datetime: 2017-12-09T03:39:28+00:00
- Post Title: Extract Dark Souls 3 audio files?

I'm having an issue with extracting the fdp_xm.fsb files. Whenever I decrypt them, then go to extract them, I get the message "The sound created exceeds the allowable input channel count.  This can be increased using the maxinputchannels parameter in System::setSoftwareFormat." in my command prompt. I have no idea how to fix this, and it applies to all 'xm' files. It's just with these, as the music, ambience, and voices all seem to extract perfectly. Someone please help me. Thank you!
## Post #8
- Username: Swennet
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 22, 2013 4:50 am
- Post datetime: 2018-01-21T14:50:26+00:00
- Post Title: Extract Dark Souls 3 audio files?

> Reply from brendan19
>
> Download these two tools first.

Dark Souls III FSB Ripping

Copy all of the .fsb files from your Dark Souls III installation folder into the "FSBExt" folder and then run the "Decrypt Dark Souls 3 FSB.bat" file

This will decrypt all the .fsb audio files.

Once this has been completed, copy the newly created decrypted FSB files which have the "_crypt.fsb" in their filename into the FMOD Extractor folder and run the "FMOD Extractor.bat" file.

This will extract and convert all of the individual audio files inside the .fsb into PCM WAV.

Enjoy

Thank you!  It worked perfectly.

I have a question for people that have also done this. Did anyone manage to extract the "smaller" audio files as well? Following these steps only gave me the soundtrack, dialogue, and cutscene audio. I would like to also have all the atmospheres and weapon hits, monster groans, etc. Is this possible using this method or are they in different archives?
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-01-23T03:23:32+00:00
- Post Title: Extract Dark Souls 3 audio files?

Try using the [latest vgmstream](https://raw.githubusercontent.com/bnnm/vgmstream-builds/master/bin/vgmstream-latest-test-u.zip) as it now supports FSB files.

The test.exe can be used to convert FSBs to WAV.


Here's a batch file to convert multiple FSB files. Save the text into notepad and give it the file extension ".bat" instead of ".txt" and put it in the same folder as the "test.exe"

```
pause
```
## Post #10
- Username: PeeInAShoe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 28, 2019 6:22 am
- Post datetime: 2019-07-27T22:28:27+00:00
- Post Title: Extract Dark Souls 3 audio files?

> Reply from brendan19 ↑Tue Sep 26, 2017 6:27 pm at Tue Sep 26, 2017 6:27 pm
>
> 
Download these two tools first.

Dark Souls III FSB Ripping

Copy all of the .fsb files from your Dark Souls III installation folder into the "FSBExt" folder and then run the "Decrypt Dark Souls 3 FSB.bat" file

This will decrypt all the .fsb audio files.

Once this has been completed, copy the newly created decrypted FSB files which have the "_crypt.fsb" in their filename into the FMOD Extractor folder and run the "FMOD Extractor.bat" file.

This will extract and convert all of the individual audio files inside the .fsb into PCM WAV.

Enjoy

I cant paste any of the files there is no option to.
Can you explain for dum dumb like me?
