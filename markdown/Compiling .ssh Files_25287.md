## Post #1
- Username: jacksonlowry
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 26, 2022 4:14 am
- Post datetime: 2022-04-23T19:24:27+00:00
- Post Title: Compiling .ssh Files

I've managed to open and view some .ssh files using programs here: [http://wiki.xentax.com/index.php/EA_SSH_FSH_Image](http://wiki.xentax.com/index.php/EA_SSH_FSH_Image). The one problem is, some .ssh files give the message in EA Graphics Manager "Preview for this image type is not supported", and those same .ssh files crash EA Graphics Tools with the error "481 Invalid Image". Some however can be viewed and edited. All of these programs just have export features, is there anything that can import and repackage a .ssh file? And what could be different about some particular .ssh files to make them give such errors and crashes in every program?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-23T20:17:18+00:00
- Post Title: Compiling .ssh Files

> The one problem is, some .ssh files give the message in EA Graphics Manager "Preview for this image type is not supported"

I'm the main developer of EA Graphics Manager and I can only tell you that it is still in development and many things needs to be fixed or updated.  

> what could be different about some particular .ssh files to make them give such errors and crashes in every program?

That's because there are many image types to support (see "Entry Types" table on the wiki). 
And most of the listed tools were made for PC games (for FSH files), while SSH files are used only on PS2 console, so they have different signatures, endianess etc.

> is there anything that can import and repackage a .ssh file?
I'm not sure. All the tools and scripts I know are listed on the wiki. If they don't support it, then you are out of luck.
## Post #3
- Username: tetsuro1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2022 3:07 am
- Post datetime: 2022-04-30T20:52:44+00:00
- Post Title: Compiling .ssh Files

Hello, everyone!

I recently started getting interested in modding EA's MVP Baseball 2005 after I recently got back into playing the game.

What I want to do is to make a mod that will turn default controller button icons into PlayStation icons.

So, instead of it looking like [this](https://i.imgur.com/I9asgfv.png), I want it to look like [this](https://i.imgur.com/AZHHWfa.png).

One way to do this is by manually editing the images extracted from the game files, and replacing those button icons with PS icons, however, since I've never done graphics editing before, and I'm pretty sure it's a complicated process, I thought of a simpler method, and that is, I take the same files from the PS2 version of the game and replace them with the PC version, simple right?

Unfortunately, when I try to do this I stumble upon a problem where the files extracted from the PS2 game that contain the images I want, come with a different extension called SSH, which is something I wasn't able to find out how to open or extract them, no matter how much Googling I do.

On the PC port of the game, the same files that I'm looking for come with a FSH file extension, which can be simply extracted with tools like nfshtool, EA Graphics Editor, etc. These tools extract these files, and then give me proper images to work with.

On the other hand, if I try to use the same tools on the PS2 SSH files, I get an error or weird "pixelated"/corrupted rendering.

For example, [here is how the PC FSH file contents look when viewed with EAGE](https://i.imgur.com/34i6r7x.png)

And here is [how they look when I try to do it with SSH files](https://i.imgur.com/ZrnHGUH.png) while at the same time comparing the same file to the PC version.

Notice how as I said before the PS2 image files look "pixelated"/corrupted, whereas the PC file looks normal.

Does anyone know what these SSH files are, and how would someone be able to extract them and have normal looking files which I could use?

I've uploaded these files which I'm working with along with EAGE [to Google Drive](https://drive.google.com/file/d/1YbJGstGfCWDZC_pV_s-GsjXmoD7zT1aV/view?usp=sharing) if anyone is curious, and wants to take a look at it themselves.

You can use EAGE to extract and preview files from the .BIG files provided. The files I'm looking to edit are within the "pitchslc.fsh/ssh" file.

Apologies for the long post, and thank you for reading this far.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-01T10:09:54+00:00
- Post Title: Compiling .ssh Files

@tetsuro1, similar question was asked few days ago, so I've moved your post to this topic.

If you look for specification or some scripts, tools, you can go here [http://wiki.xentax.com/index.php/EA_SSH_FSH_Image](http://wiki.xentax.com/index.php/EA_SSH_FSH_Image)

But currently support for SSH files is limited (some tools are in development, some don't recognize SSH files at all).
## Post #5
- Username: tetsuro1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2022 3:07 am
- Post datetime: 2022-05-01T23:50:15+00:00
- Post Title: Compiling .ssh Files

> Reply from ikskoks ↑Sun May 01, 2022 6:09 pm at Sun May 01, 2022 6:09 pm
>
> 
@tetsuro1, similar question was asked few days ago, so I've moved your post to this topic.

If you look for specification or some scripts, tools, you can go here http://wiki.xentax.com/index.php/EA_SSH_FSH_Image

But currently support for SSH files is limited (some tools are in development, some don't recognize SSH files at all).

Hi, @iksoks ! Thank you for the reply and the information you gave from that link. I also didn't even know you were the one who created EA Graphics Manager 

Unfortunately, all the tools and scripts listed within that link did not work in my case, however, I did find out something while meddling with COOPOV.BIG file, which is the main file I'm working with right now.

So far, most of the programs that I've used to extract files from the BIG archives like FinalBIG, EAGC, etc. all unpack those files as compressed files. But recently, I tried another program called BigGUI, and it first decompresses the files within the BIG archives before extracting them.

The reason I say this is because, when I try to load the compressed SSH with EA Graphics Manager, I receive an error 
```
File not supported!
```
 whereas if I try to load that same file, but only this time it's decompressed (as a result of extracting it via BigGUI), it manages to load the file just fine, the only problem is that there are no image previews for some images within it, and when I try to export the files from that SSH file, I get a BIN file instead of an image file.

I'll post all the files I work with to [this Google Drive link](https://drive.google.com/file/d/10Alw5plq2HTc2IiXaLnTZHkXooAbtXAe/view?usp=sharing) (since I get messages by the forum saying that the file is too large -_-) as I would like it if you can take a look at it yourself, especially the "File Header" and "Entry Header" sections of your program since I don't understand any of that information, it might give you a clue on whether or not it's possible to extract the content from these SSH files or not.

Also, what happened to your NHL_2002_PS2_Tool.py python script that you posted in [this thread](https://forum.xentax.com/viewtopic.php?f=18&t=23145)? At this point, I'd like to try every tool/script I can to see if I'll be able to extract the files that I need, so I'm wondering if you removed that file, or moved it someplace else?

One more thing that I think is worth mentioning is that aside from all of those tools and scripts not working from the link you sent, one more tool that I managed to make somehow work was [EA Graphics Tools](https://forums.nba-live.com/downloads.php?view=detail&df_id=3215), but unfortunately, that tool came with its own problems as well.

When I tried to open the compressed SSH file, I get this error 
```
Run-time error '7': Out of memory
```
 which is also what I get when I use the "Unpack a single SSH" option. When I try to open the decompressed SSH file, I get this error instead 
```
Run-time error '481': Invalid picture
```
 however, if I try to unpack that decompressed file, it does it successfully, but I get corrupted or barely readable image files, which I'll upload within the attachments of this post.


I apologize for the long post again, I hope you'll be able to help me figure out how to extract the images from these files to be able to use them for the PC port of the game.

Also, unlike OP, I would like to mention that I would just like to extract the contents of the SSH file and get the images I need without them being corrupted or unreadable, I don't need to recompile the SSH file or import anything into it, so any tool or script that has an export feature is good enough for me.
[Images.zip](https://xentaxbackup.github.io/file/22181_Images.zip)
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-02T17:45:19+00:00
- Post Title: Compiling .ssh Files

> The reason I say this is because, when I try to load the compressed SSH with EA Graphics Manager, I receive an error
Yeah, compressed files are not supported right now. I need to write custom decompressor in the future or find one that can be integrated into my code.

> and when I try to export the files from that SSH file, I get a BIN file instead of an image file.
This BIN file is raw image data. It can be used for research or for manual conversion.
For example, you can extract BIN file and then try to preview it with TextureFinder or RawTex.
More info here [viewtopic.php?t=15540](https://forum.xentax.com/viewtopic.php?t=15540)

> as I would like it if you can take a look at it yourself, especially the "File Header" and "Entry Header" sections of your program since I don't understand any of that information, it might give you a clue on whether or not it's possible to extract the content from these SSH files or not.

I''ve checked your samples. Thy are using entry types 2 and 14. 
(see this table for reference [http://wiki.xentax.com/index.php/EA_SSH ... ntry_Types](http://wiki.xentax.com/index.php/EA_SSH_FSH_Image#Entry_Types))
So my tool currently supports type 2 from some games, but the preview is buggy and needs to be fixed in the future.
Type 14 is currently a complete mystery for me and I don't know how to process it.   

As for File Header / Entry Header info, it always contains the same fields as described in file format specification on the wiki.
First is the file header section, then entry header, then directory, then data.
I'm using this info in my tool to parse file, but converting image data to normal image file (e.g. raw to bmp) is another story.

> Also, what happened to your NHL_2002_PS2_Tool.py python script that you posted in this thread?
It was completely removed from repository, because I've rewritten the code to create EA Graphics Manager.
You can say that this Python script was very early version of EA Graphics Manager.  

But if you really want to check it, you can still view it in Github commit history:
[https://github.com/bartlomiejduda/Tools ... S2_Tool.py](https://github.com/bartlomiejduda/Tools/blob/9a515df948b25754606bbe697593f27fa934b2e0/NEW%20Tools/NHL%202002%20PS2/NHL_2002_PS2_Tool.py)

> one more tool that I managed to make somehow work was EA Graphics Tools, but unfortunately, that tool came with its own problems as well.

Unfortunately I can't help with any issues with EA Graphics Tools, because I don't have access to the source code.
But I can tell you that it is caused by the same thing - image types for this game (2 and 14) are not correctly supported by the tool.
## Post #7
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2022-05-02T21:29:59+00:00
- Post Title: Compiling .ssh Files

I saw your thread over at zenhax, anyway what I can say about the type 14 textures is they are swizzled, but using a non-standard one (Might be even using Xbox-style swizzle or own EA implementation of the swizzle algorithm I don't know). As an alternative workaround for now, you can try use latest 1.7.0 beta of PCSX2 [(here)](https://github.com/PCSX2/pcsx2/releases) which has the texture dumping feature (Though, you may want to fix the transparency level first as the full transparency on PS2 is different from the PC ones).
## Post #8
- Username: tetsuro1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2022 3:07 am
- Post datetime: 2022-05-03T06:05:51+00:00
- Post Title: Compiling .ssh Files

> Reply from BloodRaynare ↑Tue May 03, 2022 5:29 am at Tue May 03, 2022 5:29 am
>
> 
I saw your thread over at zenhax, anyway what I can say about the type 14 textures is they are swizzled, but using a non-standard one (Might be even using Xbox-style swizzle or own EA implementation of the swizzle algorithm I don't know). As an alternative workaround for now, you can try use latest 1.7.0 beta of PCSX2 (here) which has the texture dumping feature (Though, you may want to fix the transparency level first as the full transparency on PS2 is different from the PC ones).

Honestly, I have no idea what does "swizzle algorithm" mean or anything like, because, as I said, I have zero experience in image editing and all of these things basically fall on deaf ears when someone says it to me 

Anyway, I have PCSX2 1.6.0 so I would prefer not to use a beta version instead of the stable one which I have now, as I still use PCSX2 from time to time.

If there is a way to set up PCSX2 1.7.0 without installing it, and better yet, just for using that texture dumping feature you mentioned, then I might give it a shot, otherwise, I'm going to ignore that as I'm starting to think, dealing with SSH files is too much of a hassle just for creating a simple mod.


> Reply from ikskoks ↑Tue May 03, 2022 1:45 am at Tue May 03, 2022 1:45 am
>
> 
This BIN file is raw image data. It can be used for research or for manual conversion.
For example, you can extract BIN file and then try to preview it with TextureFinder or RawTex.
More info here viewtopic.php?t=15540
as I would like it if you can take a look at it yourself, especially the "File Header" and "Entry Header" sections of your program since I don't understand any of that information, it might give you a clue on whether or not it's possible to extract the content from these SSH files or not.

I''ve checked your samples. Thy are using entry types 2 and 14. 
(see this table for reference http://wiki.xentax.com/index.php/EA_SSH ... ntry_Types)
So my tool currently supports type 2 from some games, but the preview is buggy and needs to be fixed in the future.
Type 14 is currently a complete mystery for me and I don't know how to process it.

Thanks for such an informative reply, but unfortunately, as I said to the previous user, it's pointless to try to explain it to me, as I have never dabbled in image/graphics editing before, so all this information goes over my head because I have no idea what's being talked about here 

I've tried using the TextureFinder and RawTex, but I have no idea what any information within those programs means, nor how would I be able to convert the exported raw image data that your program creates (those BIN files).

I've uploaded a ZIP file containing all of the exported raw image data from that SSH file within the attachments. I hope you can take a look at them yourself and try to convert them with TextureFinder or RawTex because I had no luck so far, and this is the last option I'm willing to try, because as I said in my comment to the previous user, I think meddling with SSH files is too much of a hassle just for trying to create a simple mod.

I hope you have better chances at converting those BIN files to actual image files than I had since you know more about this than me, but other than that, thanks for all the help so far, it was really useful 

Good luck, and if this doesn't work, then I guess I'll have to try to manually edit these files.
[files.zip](https://xentaxbackup.github.io/file/22184_files.zip)
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-03T10:46:14+00:00
- Post Title: Compiling .ssh Files

> what I can say about the type 14 textures is they are swizzled

> I hope you have better chances at converting those BIN files to actual image files than I had since you know more about this than me, but other than that, thanks for all the help so far, it was really useful

If the info that @BloodRaynare told us about swizzling is true, then we won't be able to convert it manually
without unswizzling them first.
Read more here: [https://www.google.com/search?client=fi ... ng+texture](https://www.google.com/search?client=firefox-b-d&q=unswizzling+texture)

(I'm not an expert with swizzling, I have to learn it as well   )
## Post #10
- Username: tetsuro1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2022 3:07 am
- Post datetime: 2022-05-03T18:23:37+00:00
- Post Title: Compiling .ssh Files

> Reply from ikskoks ↑Tue May 03, 2022 6:46 pm at Tue May 03, 2022 6:46 pm
>
> 
what I can say about the type 14 textures is they are swizzled
I hope you have better chances at converting those BIN files to actual image files than I had since you know more about this than me, but other than that, thanks for all the help so far, it was really useful

If the info that @BloodRaynare told us about swizzling is true, then we won't be able to convert it manually
without unswizzling them first.
Read more here: https://www.google.com/search?client=fi ... ng+texture

(I'm not an expert with swizzling, I have to learn it as well   )

Wow, who knew that a 15+ year old image format would be such a pain in the ass to convert nowadays, lol.

Not sure who should gain credit for this, EA or Sony, haha.

Anyway, I contacted @BloodRaynare , hopefully, he'll be able to tell us if there's anything possible to be done with these files, or not.
## Post #11
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2022-05-06T02:16:32+00:00
- Post Title: Compiling .ssh Files

However, swizzling stuff is beyond my abilities as well.
