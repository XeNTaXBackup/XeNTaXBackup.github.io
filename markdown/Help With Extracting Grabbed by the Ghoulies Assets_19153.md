## Post #1
- Username: collabvm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 06, 2018 10:52 pm
- Post datetime: 2018-12-07T01:01:24+00:00
- Post Title: Help With Extracting Grabbed by the Ghoulies Assets

Sorry if i'm posting this in the wrong forum but I'm interested in extracting the assets from Grabbed by the Ghoulies. My main focus is to see if there is some cut content still on the game disc, as the game itself changed so much during development. Here are some of my findings about  the compiled files on the disc:

.bnl- Files with this extension contain models and level designs. I believe a script was mode for extracting these files in another thread on here but I don't remember

Files in wavebank folder- Extensionless files that are large in size. Each file in this folder has a "WEND" header. Possibly just contains a bunch of wav files with stripped headers.

Files in movie folder- Extensionless files with a similar filename structure to the ones in wavebank. Each file has a header that begins with "BIKi". 

Files in localext- Same filename convention as the last two. Files appears to be headlerless. Likely contains the game dialog as file 0b24c424 has some debug info about a "Dialog test".

Files in fonts- Same filename convention, also headerless.

Files in demand- Same fileanme convention, headerless, I'm not really sure what these files are used for.

I want some guidance on how to extract the assets as these files do seem interesting. If you want to take a shot at it yourself, I have provided some sample files for all of the files I listed here:
[https://mega.nz/#!MBVCyQjT!-zVAjXstk70Y ... BjHmnB-vmc](https://mega.nz/#!MBVCyQjT!-zVAjXstk70YUv9Bxl0nhwBwZN2_ERc8mBjHmnB-vmc)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2019-06-14T19:59:36+00:00
- Post Title: Help With Extracting Grabbed by the Ghoulies Assets

i have a done a bit of work on this game   

i have resolved few hashes in this gist: [https://gist.github.com/x1nixmzeng/1195c80d2c551fae5b7d](https://gist.github.com/x1nixmzeng/1195c80d2c551fae5b7d)

the blender scripts are in this thread : [https://forum.xentax.com/viewtopic.php?f=16&t=12463](https://forum.xentax.com/viewtopic.php?f=16&t=12463)

it parses the bnls files in the blender scripts - have a look here - bnl files are "bundles" of files

the wavebank files use adpcm which can be converted to wav pretty easily
the video files are bink - download the bink player and these can play on their own

demand files can be any filetype that isn't part of a bundle (.bnl) - the game loads these manually

it contains mostly images
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2019-06-14T20:07:24+00:00
- Post Title: Help With Extracting Grabbed by the Ghoulies Assets

yeah, shout if you're still interested in this

i have a bunch of code just sitting on my pc which would be a good head start for anyone

```
        {
            // aid_objparams are read from "aid_objparams/blah"?

            // aid_objparams_ghoulies_fx_fadeout
            // aid_objparams_ghoulies_actor_cameron
            // aid_objparams_ghoulies_misc_buttonbat
            // aid_objparams_ghoulies_fx_solidredflash

            eResTexture = 1,
            eResAnim = 2,
            eResUnknown3 = 3,
            eResModel = 4,
            eResAnimEvents = 5,

            eResCutscene = 7,
            eResCutsceneEvents = 8,

            eResMisc = 10,
            eResActorGoals = 11,
            eResMarker = 12,
            eResFxCallout = 13,
            eResAidList = 14,

            eResLoctext = 16,

            eResXSoundbank = 18,
            eResXDSP = 19, // may be unused
            eResXCueList = 20, // this is important for audio filenames
            eResFont = 21,
            eResGhoulybox = 22,
            eResGhoulyspawn = 23,
            eResScript = 24,
            eResActorAttribs = 25,
            eResEmitter = 26,
            eResParticle = 27,
            eResRumble = 28,
            eResShakeCam = 29,

            eResCount
        };
        
```
## Post #4
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2021-01-20T06:17:54+00:00
- Post Title: Help With Extracting Grabbed by the Ghoulies Assets

> Reply from WRS ↑Sat Jun 15, 2019 3:59 am at Sat Jun 15, 2019 3:59 am
>
> 
i have a done a bit of work on this game   

i have resolved few hashes in this gist: https://gist.github.com/x1nixmzeng/1195c80d2c551fae5b7d

the blender scripts are in this thread : viewtopic.php?f=16&t=12463

it parses the bnls files in the blender scripts - have a look here - bnl files are "bundles" of files

the wavebank files use adpcm which can be converted to wav pretty easily
the video files are bink - download the bink player and these can play on their own

demand files can be any filetype that isn't part of a bundle (.bnl) - the game loads these manually

it contains mostly images

Blender script does not work
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-10-29T22:14:17+00:00
- Post Title: Help With Extracting Grabbed by the Ghoulies Assets

Huh, sorry for necropost but if anyone is interested, here is the hash algorithm 

```
        {
            m_String = m_String.Replace("aid_", "");

            for (Int32 i = 0; i < m_String.Length; i++)
            {
                dwHash = 16 * dwHash + (Byte)(m_String[i] & 0xDF);

                if ((dwHash & 0xF0000000) != 0)
                {
                    dwHash ^= dwHash & 0xF0000000 | ((dwHash & 0xF0000000) >> 24);
                }
            }

            return dwHash;
        }

```
