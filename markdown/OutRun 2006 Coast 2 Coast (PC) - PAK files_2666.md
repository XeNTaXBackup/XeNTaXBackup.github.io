## Post #1
- Username: crypto
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 20, 2007 10:40 am
- Post datetime: 2007-06-24T03:31:06+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

I'm trying to extract the audio files from the .pak files in Outrun 2006 C2C, and replace them with my own.  Can anyone help with the extraction and re-compression?  I've already tried Eksbox audio extraction tool....file type not supported.
Thanks.  


Poll has been deleted by moderator.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-06-24T06:01:27+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

why a poll?
The audio it's raw audio pcm, you can convert to ogg with "oggenc --raw" switch modify and later reconvert to raw (ogg to raw) with "oggdec -R"
## Post #3
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-06-24T15:27:09+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

> Reply from Savage
>
> why a poll?
The audio it's raw audio pcm, you can convert to ogg with "oggenc --raw" switch modify and later reconvert to raw (ogg to raw) with "oggdec -R"

did you try to do an hex inspection with 12 packs of corona?

you'll post a poll seen 20 fingers on your hand
## Post #4
- Username: crypto
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 20, 2007 10:40 am
- Post datetime: 2007-06-28T01:48:54+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

> Reply from Savage
>
> why a poll?
The audio it's raw audio pcm, you can convert to ogg with "oggenc --raw" switch modify and later reconvert to raw (ogg to raw) with "oggdec -R"

poll? *hiccup*.... what poll??  

pcm...cool...i can work with that.  now how do i extract the files?  will MEX do that for me?  and reencode/compress into .pak?
## Post #5
- Username: crypto
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 20, 2007 10:40 am
- Post datetime: 2007-06-28T01:51:27+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

> Reply from mambox
>
> Savage wrote:why a poll?
The audio it's raw audio pcm, you can convert to ogg with "oggenc --raw" switch modify and later reconvert to raw (ogg to raw) with "oggdec -R"

did you try to do an hex inspection with 12 packs of corona?

you'll post a poll seen 20 fingers on your hand

lol...i knew i was missing something!  no, but seriously....i really wouldn't know how to do a 'hex inspection' if my life depended on it.  i know what a hex editor is, and i know how to inspect a bottle of Corona to make sure it's not carbonated pee, but something tells me that's not what you're suggesting.
## Post #6
- Username: crypto
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 20, 2007 10:40 am
- Post datetime: 2007-07-09T14:35:18+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

I don't mean to be a pain here, but I really need help.  I'm trying to decrypt and extract the audio files from WITHIN THE .PAK FILES...I already know what .ogg files are...those aren't the ones I'm trying to replace.  The .ogg files in the /Sound folder are the music in the game.  I'm trying to extract the engine sounds and replace them.  
I've already tried standard archive extractors like Winzip, WinRAR and 7zip...no luck.
Sega said that the .pak files are probably not standard because the game was basically a conversion from a console game (Xbox).
I need to:
1. decrypt the .pak file and extract the audio files stored in it.
2. replace the sounds with my own.
3. repack and re-encrypt the .pak file.

Basically I need support for these files to be added to MultiEX Commander.
Help! Please!


(i would have attached an example .pak file, but the 'Add an Attachment' feature won't allow .pak files)
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-09T23:06:41+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

Try putting the "pak" archive in a RAR or something like that. At least one of the common compressions that is supported by attachments. Unless they are too big and you might as well try something like "yousendit".
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-10T13:18:11+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

I will try to make a mod myseff with this (pak audios) and if works i explain, but don't expect anything
in 1-2 weeks (busy time)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-10T13:34:24+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

> Reply from crypto
>
> 
Basically I need support for these files to be added to MultiEX Commander.
Help! Please!


(i would have attached an example .pak file, but the 'Add an Attachment' feature won't allow .pak files)

Don't they all.  Anyway, like DarkFox said, why not zip it? Alternatively, if the file is too big, try cutting it with the filecutter. 

[http://www.xentax.com/uploads/author/mr ... cutter.zip](http://www.xentax.com/uploads/author/mrmouse/filecutter.zip)
## Post #10
- Username: crypto
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 20, 2007 10:40 am
- Post datetime: 2007-08-02T06:37:47+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

ugh...for some reason i'm not getting email notifications whenever anyone replies to my posts.  sorry for taking so long to check back.  
I've attached a zip file with a .pak file enclosed from the game.  I have no idea if it contains engine sounds, but it should give a good base from which decryption can begin.
Thank you to all who have responded...I really appreciate the support.
You guys are all invited to my super duper billion-dollar mansion when I strike it rich...(no, i don't have an address yet)

[ENGLISHJ_HAM_MIS_DRIFT.zip](https://xentaxbackup.github.io/file/1298_ENGLISHJ_HAM_MIS_DRIFT.zip)
## Post #11
- Username: skyboxeye
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 17, 2017 7:24 am
- Post datetime: 2022-08-16T05:16:12+00:00
- Post Title: OutRun 2006: Coast 2 Coast (PC) - PAK files

EkszBox can extract the PAKs from the Xbox release
