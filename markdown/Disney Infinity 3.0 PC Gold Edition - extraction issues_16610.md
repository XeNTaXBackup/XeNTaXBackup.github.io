## Post #1
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2017-07-30T13:30:58+00:00
- Post Title: Disney Infinity 3.0 PC Gold Edition - extraction issues

Hi folks... another blasted Disney Infinity fan who wants to rip models from the 3.0 game!!!... Here's my predicament... 
I'm creating an animated short using select characters from DI3... I'm not a coder so that side of ripping is not an option, alternatively I rip my geometry via NinjaRipper. 

Just found out I can no longer rip from the game this way as Disney have discontinued the network which is required to run the game... Researched and stumbled across a later released 'Gold Edition' by Steam that has most characters/playsets.. except for one character I used to have access to and so desperately need.. Marvel's 'Vision' ... 

The funny thing is some select characters have been deliberately left out of the gold release, BUT it seems the models/assets in the installation folder are included along with the rest of the characters!?..
Hooray!!!.. there's still a chance, although I have no idea how to access these models!?... they are in the classic '.zip' extension, though you can't extract them with WinZip/WinRAR!???..

Anyone able to please help me out with this???... I need to know how to get the data out of these zip files???
## Post #2
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2017-07-31T21:19:19+00:00
- Post Title: Disney Infinity 3.0 PC Gold Edition - extraction issues

Anyone please!? In so desperate for this... Id even pay money for someone to do it for me!!!
## Post #3
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2019-05-04T15:49:46+00:00
- Post Title: Disney Infinity 3.0 PC Gold Edition - extraction issues

Excuse me, but do you have access to the sound files to this game? I’m interested in the sounds for “Star Wars,” barring “TFA” and “Rebels” content. I know very little on the format but I have a contact on VG-Resources who would like to rip the sounds from the game too, and maybe he may know a few people who might help you acquire the models for this game, if you haven’t got them already.
## Post #4
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2019-08-27T03:57:49+00:00
- Post Title: Disney Infinity 3.0 PC Gold Edition - extraction issues

There is a script that will rip all DI3.0 geometry except for The Force Awakens content as that release used a different encryption.. There is no tool to extract the audio that I have encountered as of yet.. An alternative I tried that worked well was recording the in-game sound with FRAPS & muting either SFX/MUSIC/VOICES etc (depending on what you want to capture) within the games sound options.
## Post #5
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2020-05-06T17:09:34+00:00
- Post Title: Disney Infinity 3.0 PC Gold Edition - extraction issues

> Reply from wubbaworwee ↑Tue Aug 27, 2019 11:57 am at Tue Aug 27, 2019 11:57 am
>
> 
There is a script that will rip all DI3.0 geometry except for The Force Awakens content as that release used a different encryption.. There is no tool to extract the audio that I have encountered as of yet.. An alternative I tried that worked well was recording the in-game sound with FRAPS & muting either SFX/MUSIC/VOICES etc (depending on what you want to capture) within the games sound options.

Actually, I found a source saying that the game’s audio files use Audiokinetic's Wwise format:

.BNK/.PCK - Container format for WEM files
.WEM - Audiokinetic Wwise audio file

Some recommend using Ravioli Game Tools, though some recommend foobar2000 for WEM, and then TXTH function/BMS script for Wem BNK + PCK as well as vgmstream. Let’s see if it works.
## Post #6
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2022-05-25T01:51:22+00:00
- Post Title: Disney Infinity 3.0 PC Gold Edition - extraction issues

> Reply from ARAJediMaster ↑Thu May 07, 2020 1:09 am at Thu May 07, 2020 1:09 am
>
> 
Actually, I found a source saying that the game’s audio files use Audiokinetic's Wwise format:

.BNK/.PCK - Container format for WEM files
.WEM - Audiokinetic Wwise audio file

Some recommend using Ravioli Game Tools, though some recommend foobar2000 for WEM, and then TXTH function/BMS script for Wem BNK + PCK as well as vgmstream. Let’s see if it works.

I succeeded in converting the 'already .wem files in the game archive to .ogg with the WEM2OGG converter but these files seem to be the majority of the game sounds all randomly bundled so you have to sort through them to identify... I also attempted converting the specific character voices in the .bnk format by extracting them first with QuickBMS, you end up with .bkh.. no idea what that is so i took a hopeful stab in the dark by renaming it to .wem & used WEM2OGG, though unfortunately it spat out an error stating 'Missing RIFF file'!?.. little over my head for now...
