## Post #1
- Username: DrPawsworth
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 28, 2016 5:09 pm
- Post datetime: 2022-03-06T03:40:06+00:00
- Post Title: Nioh/Nioh 2 Sound Files

Hey folks. I'm having a real issue with trying to locate the various sound effects for the Nioh games, things like the weapon swing/impact sounds, the item sounds, the sting when your guardian spirit returns, etc.

I dug into the various .ktsl2stbin files in the sound/bgm folders and the sound/En/bgm folders, but none of them seem to have the sound effects in them. All I can find there are things like NPC voice clips, cutscene audio, and music, not sound effects. The main sound folders aren't much help either, as outside of the aforementioned bgm and En folders, there is only a single .ktsl2gcbin file in each of them, and not much else.

My only guess is that the sound effect files are somewhere in the archive files, and while I did look into said archives, they're flooded with files that I don't recognize, or files that I know are not sound files. Things like .g1m, .kts, .tmg, .eff, and so forth. If the sound effects are in there somewhere, I certainly don't know where, or what format they would be in.

This is for the PC version of the game by the way, though I don't know if the console versions of the game have a different file structure at all. I'm also not sure if other Koei Tecmo games are like this, at the very least I wasn't able to dig up much on it. 

If anyone could help point me in the right direction as to where these sound effect files are being stored, I'd be greatly appreciative. Thanks!
## Post #2
- Username: 15221281395
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 20, 2022 4:30 pm
- Post datetime: 2022-03-20T08:51:45+00:00
- Post Title: Nioh/Nioh 2 Sound Files

Ah,I also have this trouble.I think effect sounds are from bgm/atsl_cmn.g1l,atsl_abs.g1l,atsl_rtm_se.g1l,but I can’t extract them.When I convert them to .kvs，they can‘t be played by vgmstream either.My nioh game is from PC EPIC.If you have some ways to get these sounds as you say above,please tell me,thank you!
## Post #3
- Username: Controller
- Rank: n00b
- Number of posts: 11
- Joined date: Mon May 25, 2009 8:44 am
- Post datetime: 2022-08-22T16:19:03+00:00
- Post Title: Nioh/Nioh 2 Sound Files

This worked for me for atsl_abs.g1l, atsl_cmn.g1l and atsl_rtm_se.g1l:
I use Cletch for the conversions. The convertion info for Cletch is already included but the required scripts or tools are ommited due copyright issues, so you have to download them yourself.
To download Cletch "Download snapshot" on this sourceforge project: [https://sourceforge.net/p/cletch/code/HEAD/tree/](https://sourceforge.net/p/cletch/code/HEAD/tree/)
But you can use the scripts / tools without Cletch

1) Split the g1l files on each occurance of "KOVS" into a new file

For Cletch: Choose "HexSplit KOVS". No additional files are needed. However, you have to rename the generated .bin files afterwards, as the tool required in the next step has issues with the DOT in the filename and will clip the filename here, meaning it will overwrite/skip the output files.. Ignore the .not file(s))

If you don't use Clech, you can directly use HexSplit in the helpers folder within Cletch: HexSplit.exe 4B4F5653 <file>

2) Extract (convert) those new files with CethleannStandalone\Cethleann.Unbundler.exe" -R  <file>
https://github.com/yretenai/Cethleann/r ... dalone.zip

For Cletch: extract CethleannStandalone into the helpers\CethleannStandalone folder within Cletch and choose the proper conversion (Cethleann - The Koei Swiss Army Knife --- INDIR --- Dot net 5+ SAVE SINGLE FILE
In my case a few files were not converted. Cathleann does not set a proper exit code on failure, but the Cletch conversion will check if the output file exists. You can easily check which files were converted in the list, and delete input files of successfull conversions (State > Select successfull files, Queue > Recycle and remove selected)

If you don't use Cletch: In my case a few files were not converted. Cathleann does not set a proper exit code on failure. Check if the output file exists before deleting input file. Some batching should do the trick, like (untested):
ren *.bin *.ogg.bin
for %1 in (*.ogg) do del %1.bin

3. Check if the generated files are playable (e.g. VLC)
## Post #4
- Username: DrPawsworth
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 28, 2016 5:09 pm
- Post datetime: 2022-10-27T16:52:40+00:00
- Post Title: Nioh/Nioh 2 Sound Files

I've dug into the .g1l files, but unfortunately, none of them have what I'm after, they only seem to contain cutscene audio or music.
As of now I'm still trying to figure out where the sound effects and character voices are located. None of the files in the bgm directory seem to have them, so I have no idea where they are, let alone why they seem to be so difficult to locate.

My only guess would be that they're stored in one of the Archive files, but I have no idea which one they'd be in, or what format they'd be stored in. If anyone can figure out where these enigmatic files are located, do let me know.
## Post #5
- Username: EcosEstudio
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 31, 2022 1:32 pm
- Post datetime: 2023-02-04T10:45:20+00:00
- Post Title: Nioh/Nioh 2 Sound Files

Hello, can you help me?
I want to find the audio of the voices of the game Samurai Warriors 4 II PC (Sengoku Musou 4 II). I found these files and I think there are voices in it.
Usei o script sengoku_musou do Aluigi e apareceu várias extensões que não conheço:
DAT, GT1, _A2, _DV, _M1, KSH, LHS, ME1, VAP, TOD...

samples:
[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1bwgTvNpF2Z2lYmTYCZSlh9owNfKj8ibB?usp=share_link)

sengoku_musou scripts here:
[https://aluigi.altervista.org/bms/sengoku_musou.bms](https://aluigi.altervista.org/bms/sengoku_musou.bms)
## Post #6
- Username: halo1573
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 31, 2022 2:41 pm
- Post datetime: 2023-02-08T06:29:57+00:00
- Post Title: Nioh/Nioh 2 Sound Files

When ripping sound files, you know that foobar2000 + vgmstream plugin and HEX editors are essential.

I'll say it assuming you're extracting the PC version.
You will get everything you want by extracting ARCHIVE_16.lnk.

There are about 400 files with KTSL2STBIN extension in ARCHIVE_16\MISC\FORMATS\KTSL2STBIN path
Just change their extension to KTSL2ASBIN and they can be played and converted on Foobar2000.
## Post #7
- Username: EcosEstudio
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 31, 2022 1:32 pm
- Post datetime: 2023-02-08T11:35:04+00:00
- Post Title: Nioh/Nioh 2 Sound Files

> Reply from halo1573 ↑Wed Feb 08, 2023 2:29 pm at Wed Feb 08, 2023 2:29 pm
>
> 
When ripping sound files, you know that foobar2000 + vgmstream plugin and HEX editors are essential.

I'll say it assuming you're extracting the PC version.
You will get everything you want by extracting ARCHIVE_16.lnk.

There are about 400 files with KTSL2STBIN extension in ARCHIVE_16\MISC\FORMATS\KTSL2STBIN path
Just change their extension to KTSL2ASBIN and they can be played and converted on Foobar2000.

Yes, it's the PC version.
I have knowledge of foobar2000, but I don't know vgmstream plugin. How do I use it?
Is there any tutorial to guide me?
Is the ARCHIVE_16.lnk file inside VOICE.BIN? LINKDATA_1ST_ENG.BIN?
I don't understand programming, but having a tutorial, I can do it.
my discord MENIZIS#3983

Thx
## Post #8
- Username: halo1573
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 31, 2022 2:41 pm
- Post datetime: 2023-02-08T15:48:06+00:00
- Post Title: Nioh/Nioh 2 Sound Files

> Reply from EcosEstudio ↑Wed Feb 08, 2023 7:35 pm at Wed Feb 08, 2023 7:35 pm
>
> 

Yes, it's the PC version.
I have knowledge of foobar2000, but I don't know vgmstream plugin. How do I use it?
Is there any tutorial to guide me?
Is the ARCHIVE_16.lnk file inside VOICE.BIN? LINKDATA_1ST_ENG.BIN?
I don't understand programming, but having a tutorial, I can do it.
my discord MENIZIS#3983

Thx

No, the subject of this thread is Nioh 2.
I made a comment related to Nioh 2.

When ripping Koei Tecmo games, the voice files are divided into cutscenes, battles, and other voices.
And each voice files exist in different folder paths, and the file formats are also different.

You haven't made it clear what type of voice file you want to get, so I'll use the Voice.bin file as an example.

The voice.bin file contains 11000 kovs files

[https://imgur.com/AZ8WPmS](https://imgur.com/AZ8WPmS)


First, install foobar2000 + vgmstream plugin
Just by installing vgmstream plugin in foobar2000, you can play many sound formats.

Search vgmstream on Google and download foo_input_vgmstream.fb2k-component.
Open foobar2000, click File - Preferences - Components, then install the fb2k plugin you downloaded.
Now you are ready to play sound files from KT games including samurai warriors4 and nioh2.

You just need to spilt the Voice.bin file.

There are several ways, but given that you are new, using vgmtoolbox seems better.

Find and install vgmtoolbox on the Internet, set as shown in the Advanced cutter/Offset finder, then drag and drop the Voice.bin file to vgmtoolbox.

[https://imgur.com/aUkDPc9](https://imgur.com/aUkDPc9)

and play them on foobar2000.

P.s
If you open the files obtained by extracting the linkdata archive with a hex editor and find files with headers of _DBW0000 and _HBW0000, they are highly likely to be SE or battle voice files
## Post #9
- Username: EcosEstudio
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 31, 2022 1:32 pm
- Post datetime: 2023-02-08T22:51:46+00:00
- Post Title: Nioh/Nioh 2 Sound Files

> Reply from halo1573 ↑Wed Feb 08, 2023 11:48 pm at Wed Feb 08, 2023 11:48 pm
>
> 
First, install foobar2000 + vgmstream plugin
Just by installing vgmstream plugin in foobar2000, you can play many sound formats.
Search vgmstream on Google and download foo_input_vgmstream.fb2k-component.
Open foobar2000, click File - Preferences - Components, then install the fb2k plugin you downloaded.
Now you are ready to play sound files from KT games including samurai warriors4 and nioh2.
You just need to spilt the Voice.bin file.
There are several ways, but given that you are new, using vgmtoolbox seems better.
Find and install vgmtoolbox on the Internet, set as shown in the Advanced cutter/Offset finder, then drag and drop the Voice.bin file to vgmtoolbox.
https://imgur.com/aUkDPc9
and play them on foobar2000.
P.s
If you open the files obtained by extracting the linkdata archive with a hex editor and find files with headers of _DBW0000 and _HBW0000, they are highly likely to be SE or battle voice files

Sorry for my lack of information.
I want to find game voices to replace. I will do a dubbing in Brazilian Portuguese.

Following your tutorial I was able to extract the files! Thanks!   

Now I need to know how I convert .ogg audio to .kovs, any idea what program to use??
And after the new audio is in .kovs, how do I put it inside the .bin file?

a sample of the original .kovs file with the files to replace the .ogg:
[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1kxgrCT36spDexz1B4bkj83Xzf4ndYx_3?usp=share_link)

Thanks so much for your help, halo1573. I will put your name in the credits for helping me.
## Post #10
- Username: halo1573
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 31, 2022 2:41 pm
- Post datetime: 2023-02-22T10:39:22+00:00
- Post Title: Nioh/Nioh 2 Sound Files

> Reply from EcosEstudio ↑Thu Feb 09, 2023 6:51 am at Thu Feb 09, 2023 6:51 am
>
> 

Sorry for my lack of information.
I want to find game voices to replace. I will do a dubbing in Brazilian Portuguese.

Following your tutorial I was able to extract the files! Thanks!   

Now I need to know how I convert .ogg audio to .kovs, any idea what program to use??
And after the new audio is in .kovs, how do I put it inside the .bin file?

a sample of the original .kovs file with the files to replace the .ogg:
https://drive.google.com/drive/folders/ ... share_link

Thanks so much for your help, halo1573. I will put your name in the credits for helping me.

It's trivial to simply convert .ogg to .kvs.
There are also many ways to do this, but there are already tools that someone has released, so please refer to them.

kvs2ogg tool
[https://mega.nz/file/n3BRCLQa#kG8Uh1hjo ... aLY-PLiEn8](https://mega.nz/file/n3BRCLQa#kG8Uh1hjodicLiVCwJI17UgK8Vx4U4u2qaLY-PLiEn8)

But if you want to compress ogg or kvs files into .bin files. I can't help you.

I remember that the sound replacement mode for containers or archives made up of .kvs files was used in DOA5.
It might be helpful to refer to Doa5's sound swap mode and build your own tool or get advice from there.
[http://modderbase.com/showthread.php?tid=276](http://modderbase.com/showthread.php?tid=276)

Of course the doa5 sound tool won't work with the voice.bin file.
## Post #11
- Username: EcosEstudio
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 31, 2022 1:32 pm
- Post datetime: 2023-02-24T07:11:59+00:00
- Post Title: Nioh/Nioh 2 Sound Files

> Reply from halo1573 ↑Wed Feb 22, 2023 6:39 pm at Wed Feb 22, 2023 6:39 pm
>
> 
It's trivial to simply convert .ogg to .kvs.
There are also many ways to do this, but there are already tools that someone has released, so please refer to them.

kvs2ogg tool
https://mega.nz/file/n3BRCLQa#kG8Uh1hjo ... aLY-PLiEn8

But if you want to compress ogg or kvs files into .bin files. I can't help you.

I remember that the sound replacement mode for containers or archives made up of .kvs files was used in DOA5.
It might be helpful to refer to Doa5's sound swap mode and build your own tool or get advice from there.
http://modderbase.com/showthread.php?tid=276

Of course the doa5 sound tool won't work with the voice.bin file.

After converting the files to .KOVS, I locate where the audio I want to replace is in the .BIN file and replace it with the same code, since it has the same size.
Thanks for your help!    
Take a look at the test video I made:
[https://drive.google.com/file/d/1t74q55 ... share_link](https://drive.google.com/file/d/1t74q55Wxr97fVbIYAeRTilnRn04jxL65/view?usp=share_link)
## Post #12
- Username: DrPawsworth
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 28, 2016 5:09 pm
- Post datetime: 2023-03-09T19:50:24+00:00
- Post Title: Nioh/Nioh 2 Sound Files

> Reply from halo1573 ↑Wed Feb 08, 2023 2:29 pm at Wed Feb 08, 2023 2:29 pm
>
> 
When ripping sound files, you know that foobar2000 + vgmstream plugin and HEX editors are essential.

I'll say it assuming you're extracting the PC version.
You will get everything you want by extracting ARCHIVE_16.lnk.

There are about 400 files with KTSL2STBIN extension in ARCHIVE_16\MISC\FORMATS\KTSL2STBIN path
Just change their extension to KTSL2ASBIN and they can be played and converted on Foobar2000.

Sweet jesus, I really need to pay more attention to these threads. Yes indeed, archive 16 was where the sound files were stored (for both Nioh 1 and Nioh 2, interestingly), and I feel like a total imbecile for not checking that one sooner. Thank you so much!
