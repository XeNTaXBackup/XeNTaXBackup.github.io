## Post #1
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-03-24T15:54:44+00:00
- Post Title: My Hero Academia: Strongest Hero assets

Apparently the game is using simple xor on file headers, key is derived from keys table based on file type and probably something else, while some file types are not obfuscated. I've attached test script, which can extract most asset types - just use it on the whole folder. pkm are ETC2 RGBA compressed textures, they can be converted with PVRTexTool, Mali Texture Compression Tool or any other compatible tool. bank are fsb audio, should be playable with vgmstream. Not sure about the rest though.

Update: Script is updated with support for more asset types. Currently supported: png, jpg, etc2, lua, xml, bank, flv, conf, anim, mat and mesh files.



 mha_strongest_extract_v2_fix.zip
(811 Bytes) Downloaded 93 times
## Post #2
- Username: Ichicka1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 18, 2021 7:07 am
- Post datetime: 2022-04-24T01:18:16+00:00
- Post Title: My Hero Academia: Strongest Hero assets

Hello, how can i use the script plz ?
## Post #3
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-24T15:42:27+00:00
- Post Title: My Hero Academia: Strongest Hero assets

@Ichicka1: It's script for [quickbms](http://aluigi.altervista.org/quickbms.htm).

Script is updated with support for more asset types. It also includes fix for previously covered types, such as lua and axmd (first byte in those files was incorrect).
## Post #4
- Username: Ichicka1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 18, 2021 7:07 am
- Post datetime: 2022-05-13T18:26:53+00:00
- Post Title: My Hero Academia: Strongest Hero assets

Oh thanks, i have another question, how do i convert mesh and animations files ?
## Post #5
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2022-05-14T21:53:03+00:00
- Post Title: My Hero Academia: Strongest Hero assets

Where are all of the files stored? I'm only showing two .obb files in /obb totaling ~3.5gb, but system settings shows that the game has 9gb or so stored somewhere. The game also has a folder in /data, but there's only a single folder inside called /files and it appears to be empty even after showing hidden files. Is there some kind of encryption that I need a different file explorer for?
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-05-15T14:57:34+00:00
- Post Title: My Hero Academia: Strongest Hero assets

@Ichicka1 : I suppose you can create separate topic with samples for models in respective section of the forum. AXMD format looks pretty straightforward, the main problem would be in linking materials (btw materials properties are stored in xml), as all assets in the game are using id -> hash -> real name mapping, while I didn't reverse that part. 

@jflieger: If it doesn't download additional assets on the first launch or during the game, 3.5GB is probably the whole game, and system may count sources twice as cache and as installed files.
## Post #7
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2022-05-15T15:56:00+00:00
- Post Title: My Hero Academia: Strongest Hero assets

> Reply from Spiritovod ↑Sun May 15, 2022 10:57 pm at Sun May 15, 2022 10:57 pm
>
> 
@jflieger: If it doesn't download additional assets on the first launch or during the game, 3.5GB is probably the whole game, and system may count sources twice as cache and as installed files.

It does indeed download additional assets on launch, and the app storage breakdown shows a total of 8.67GB, of which 3.54GB shows as "app" (which makes sense to be the two .obb files) and 5.13GB of "data" that I can't seem to find anywhere. Cache is a miniscule 4MB or so. Another thing I had noticed after digging through the files a bit is that nothing past roughly last November seems to be in the game's files - we got Nejire Hado added as a character in February and I can't find character profile pictures, textures, banner images, card art, anything related to Hado at all. It makes me feel like there's extra data hiding somewhere that I'm missing.
## Post #8
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-05-15T17:13:10+00:00
- Post Title: My Hero Academia: Strongest Hero assets

@jflieger : Assets can be stored in system folder as well, in /data/data/. It's not accessible directly and not visible if device is not rooted. Some games are also using non-standard folders for downloaded cache.
## Post #9
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2022-05-16T23:46:46+00:00
- Post Title: My Hero Academia: Strongest Hero assets

> Reply from Spiritovod ↑Mon May 16, 2022 1:13 am at Mon May 16, 2022 1:13 am
>
> 
@jflieger : Assets can be stored in system folder as well, in /data/data/. It's not accessible directly and not visible if device is not rooted. Some games are also using non-standard folders for downloaded cache.
Found it, I rooted Bluestacks and it was indeed in data/data. Currently transferring all of it over to Windows now, it was about 5GB worth, so it's gotta be the right stuff.
## Post #10
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2022-05-17T12:10:23+00:00
- Post Title: My Hero Academia: Strongest Hero assets

> Reply from Spiritovod ↑Mon May 16, 2022 1:13 am at Mon May 16, 2022 1:13 am
>
> 
@jflieger : Assets can be stored in system folder as well, in /data/data/. It's not accessible directly and not visible if device is not rooted. Some games are also using non-standard folders for downloaded cache.

That was indeed everything, thanks a bunch for all your work on this script and the extra help. Any plans to reverse the file structure as well in the future?
## Post #11
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-05-17T16:46:56+00:00
- Post Title: My Hero Academia: Strongest Hero assets

@jflieger: No, it's too bothersome. But for reference, files are handled starting in Axon::FileManager::GetFileData function and down to Axon::FileManager::ToEncryptPath. Basically, original full paths are somehow hashed (derived from MD5) and then loaded through comparison against md5.txt manifest shipped with the game.
## Post #12
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2022-05-17T18:30:06+00:00
- Post Title: My Hero Academia: Strongest Hero assets

@Spiritovod Gotcha. To be honest with you, that's pretty far beyond my skill level, but if I could manage to, say, find the true name/path of a texture file inside of one of the material files and match it up to the hashed file name, would it be possible to use the manifest to get all the other file names or is it strictly one-way?
## Post #13
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-05-17T20:56:28+00:00
- Post Title: My Hero Academia: Strongest Hero assets

@jflieger: Usually such things are done through fully reversing hashing function, then grabbing unwrapped (original) paths from memory with hook or debugging and then restoring original paths by comparing result of hashing function for every original path with hashed filename - all other approaches doesn't make much sense or very limited in terms of usage. Those things are rarely done for mobile games though.
## Post #14
- Username: Takato Matsukj
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Jul 26, 2019 2:39 am
- Post datetime: 2022-09-09T18:25:35+00:00
- Post Title: My Hero Academia: Strongest Hero assets

idk if anyone still interested in TSH but here in my MHA discord we've been datamining it for a while

[https://discord.gg/uahigh](https://discord.gg/uahigh)
