## Post #1
- Username: Maron19
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Nov 05, 2017 10:22 pm
- Post datetime: 2021-09-24T23:40:52+00:00
- Post Title: wavescan.bms file names

I wanted to extract the pck files from Life is Strange and I have a problem with the names of the extracted files.  Wavescan.bms gives the name of the first tag it encounters at the specified location.  Unfortunately, some files have the marker_silence tag. 
File fragment:
[LIST�...adtllabl......DNE_WAV_MARKER_SILENCE..labl......DNE_WAV_MARKER_SPEAK..labl.......Cue_E1_2A_ArtClass_CHKate_Phase01_Max_011.data]
 The file should be named like this:
[...Cue_E1_2A_ArtClass_CHKate_Phase01_Max_011.wav]
and not like this:
[...DNE_WAV_MARKER_SPEAK.wav]
Looking at the wavescan.bms file, I understand the general sense of creating a filename, but can anyone tell me what to do to have the program omit marker_silence when creating the filename?  I include an example file and wavescan.bms
[wav+bms.7z](https://xentaxbackup.github.io/file/20887_wav+bms.7z)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-25T11:04:00+00:00
- Post Title: wavescan.bms file names

It seems that this could be solved with "if" condition in the script.
Something like:

```
   callfunction retrievename2
```


But this should be probably raised in the Wwise Unpacker github repository.
[https://github.com/Vextil/Wwise-Unpacker/](https://github.com/Vextil/Wwise-Unpacker/)
(if anyone is still active there)
or you should ask original author AlphaTwentyThree for update.
## Post #3
- Username: Maron19
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Nov 05, 2017 10:22 pm
- Post datetime: 2021-09-25T15:41:00+00:00
- Post Title: wavescan.bms file names

Thanks for the answer.  I wrote to the repository owner because there is an error when extracting the bnk file and the files only have the extension .wem and most of them are omitted.  Unfortunately, another month passes and there is no answer.  I need proper pck filenames because I want to do dubbing and I need to merge subtitles with wav files.  Unfortunately, the program gives the name of the first marker it finds.  If there is marker_silence it will be the name, not the real name of the file, which is a little further in the file.  You have to somehow omit the silence markers to get the files properly named.  Could I ask you to correct this bms file?  Unfortunately, I don't know anything about quick bms...
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-25T22:19:18+00:00
- Post Title: wavescan.bms file names

Sorry, it's not my script and I don't want to modify it without author's permission.
But I hope you'll find solution for your issue soon.
## Post #5
- Username: Maron19
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Nov 05, 2017 10:22 pm
- Post datetime: 2021-09-26T15:30:09+00:00
- Post Title: wavescan.bms file names

Maybe send me a private message?  People create something and then don't care about it, I'm not going to abandon my plans to create dubbing for this game for that. Nobody asked Square Enix for permission when creating the subtitles ...
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-26T16:25:29+00:00
- Post Title: wavescan.bms file names

Ok, I think I came up with a workaround:

```
		For
			get NULL_BYTE byte
			get DUMMY long 
			get MSIZE long
			math MSIZE -= 4
			get DUMMY long 
			getDstring MNAME MSIZE
			if MNAME != "DNE_WAV_MARKER_SILENCE" and MNAME != "DNE_WAV_MARKER_SPEAK"
				break
			endif
		Next
		
   endif
```


Put my code between those two lines:

```
string NAME += "~"
```


And let me know if it works for you.
## Post #7
- Username: Maron19
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Nov 05, 2017 10:22 pm
- Post datetime: 2021-09-26T17:37:30+00:00
- Post Title: wavescan.bms file names

Cool, it seems that everything works  After Lara Croft, I didn't think that someone here would help us with our hobby of translating games... I will certainly include you in the dubbing authors. I don't want to abuse your courtesy, but could you please give me any more hint on how to repack the files back to .pck? Even where to look for such information. I read that quick bms can also be used to pack files, but at the same time they must have the same sound parameters as the original.
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-26T17:56:59+00:00
- Post Title: wavescan.bms file names

> I will certainly include you in the dubbing authors.
Thank you 

> how to repack the files back to .pck?

> I read that quick bms can also be used to pack files
Yes, quickbms has something called "reimport mode".
You can read more about it in documentation (section 3) [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)

There are also some tutorials about that
[https://www.google.com/search?client=fi ... t+tutorial](https://www.google.com/search?client=firefox-b-d&q=quickbms+reimport+tutorial)
