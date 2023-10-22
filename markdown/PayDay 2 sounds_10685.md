## Post #1
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-08-13T09:07:27+00:00
- Post Title: PayDay 2 sounds

Hey mates,

So, to be brief, I found a way to convert IMA ADPCM sounds from " PayDay: The Heist " with [this topic](http://forum.xentax.com/viewtopic.php?f=17&t=10586&p=86992&hilit=payday#p86992) and tried to redo that technique on " PayDay 2 Beta " but, as you can guess, if I'm here it's because it's not working.
Indeed, when I drag the processed sound ( with ima_rejigger2 ) in Audacity ( with FFmpeg plugin installed ) nothing's happening and when I load it as a raw sound, the file is messed ( static ).
So, I give you a lil' sample if you think that can help you to understand what's the problem.

EDIT: Ok, it odly seems that Audacity don't support those sounds but no problem with VLC. But now, how can I convert them to propper .wav files?

EDIT2: Alright, never mind, I found my solution: I've got to convert it manually by VLC ( I've never did this before ). I'm a freaking idiot.

Well, I summarizes: 

Step1: You got to download the PaydayBundleTool [here](http://www.mediafire.com/download/0kkr9z50550uljj/payday_tool_v1_2.zip) and the ima_rejigger2 tool [here](http://hcs64.com/files/ima_rejigger2.zip).
Step2: Once you've extracted the files from .bundle archives, drag one by one each sounds you want into the ima_rejigger2 tool.
Step3: Next, import the processed sounds into VLC and convert them into propper .wav files ( lil' tutorial [here](http://www.google.fr/url?sa=t&rct=j&q=using+VLC+to+convert+audio&source=web&cd=2&cad=rja&ved=0CEQQFjAB&url=http%3A%2F%2Fwww.medill.northwestern.edu%2FWorkArea%2Flinkit.aspx%3FLinkIdentifier%3Did%26ItemID%3D206545&ei=e5IMUvm1CIyT0AXK_4CgBQ&usg=AFQjCNEH7o45aeA083vDZzkcgEvmruaD7A) ).

Now, if somebody have an idea to convert faster the sounds with ima_rejigger2 and VLC, I'm interested because draging one by one all the files is pretty long.

EDIT3: Well, I found it myself again ( at least for ima_rejigger2 processing ):

```
pause
```


Got an idea for VLC step?

EDIT4: Found it... Here's the command line for the VLC step:

```
for %%a in (*.wav) do cmd /c "C:\Program Files (x86)\VideoLAN\VLC\vlc.exe" -I dummy -vvv %%a --sout=#transcode{acodec=s16l}:standard{access=file,mux=wav,dst=%%a.wav} vlc://quit
```

Hem... Consider this a lil' tutorial...

Cordialy.

Vosvoy
## Post #2
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-08-18T10:33:14+00:00
- Post Title: PayDay 2 sounds

Hey mates I'm back for one last thing:

I just discover that the PaydayBundleFile tool was interpreting some .wav riff files as other extensions during extraction ( like .bin and .dds ).



So, I have an idea but I don't know if it's possible: 

Extract all the files without any extension ( possible with the PaydayBundleTool ) and thanks to a lil' batch file or a succinct tool, give them the RIGHT extension relative to their header/offset.

like that stuff:

```
ren *.wav
del *.unknown
```


Note: The .wav riff files have the same offset ( 52 49 46 46 -> 0x03(?) )

Can you give me a clue?

PS: I've found something like that but I don't know how to do it ( I'm new on line commands and stuffs like that )... You will find a file in the attachment ( if you need it ).

Thanks in advance mates.

Vosvoy
[CanYouGiveAClue.zip](https://xentaxbackup.github.io/file/6558_CanYouGiveAClue.zip)
## Post #3
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-08-19T06:31:50+00:00
- Post Title: PayDay 2 sounds

Files inside the bundles are found by two hashes each: one for the extension, another for path + name. So if you get filenames containing the extension hash after extracting, you can just batch rename them.
## Post #4
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-08-19T08:10:42+00:00
- Post Title: PayDay 2 sounds

> Reply from Sir Kane
>
> Files inside the bundles are found by two hashes each: one for the extension, another for path + name. So if you get filenames containing the extension hash after extracting, you can just batch rename them.

That's exactly what I want to do but I don't know how to do it. Can you give me a hand ( for the command line )? I would only rename .wav files that the tool wrongly extracted as .bin files ( as I said above, there is .dds files as .bin files too ).
## Post #5
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-08-20T06:19:06+00:00
- Post Title: PayDay 2 sounds

09E2DB206ACBCB09 is the hash for "stream", which is their sound file extension.

Here's a fixed ext_info.txt: [http://sktest.aruarose.com/ext_info.txt](http://sktest.aruarose.com/ext_info.txt).
## Post #6
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-08-20T08:29:33+00:00
- Post Title: PayDay 2 sounds

So, if I understood it right, I have to create a batch file that check the hash " 09E2DB206ACBCB09 " in extracted files. Subsequently, matched files will be renamed as .wav files. I am right?

Well, I'll got to do some research about hash checking with the command line, in that case, because I didn't know that was possible to do that.

EDIT: I don't get any help on internet for that... Please, do you know what is it ( command line )? 
( I would to do a lil' video tutorial after this ( yeah, I have a lot of time to spare for the moment ) because, as a noob, I'd like to find a person to help me out when I need it. But I can't do it if I haven't all what I need for it ).
## Post #7
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-08-28T20:16:41+00:00
- Post Title: PayDay 2 sounds

What's the format of your filenames? Are they similar to 3ad1623850608243.0.bd007e20bc2b61af?

The audioformat for the files I checked is ADPCM with 64 samples per block (they use wwise for audio), so it would be pretty simple to write a tool to convert them to PCM.
## Post #8
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-08-29T20:12:52+00:00
- Post Title: PayDay 2 sounds

> Reply from Sir Kane
>
> What's the format of your filenames? Are they similar to 3ad1623850608243.0.bd007e20bc2b61af?

Yes, they are.

> Reply from Sir Kane
>
> The audioformat for the files I checked is ADPCM with 64 samples per block (they use wwise for audio), so it would be pretty simple to write a tool to convert them to PCM.

Oh really? Well, I'll not be able to create a tool for that because I suck about this.
