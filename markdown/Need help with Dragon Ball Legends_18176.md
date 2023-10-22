## Post #1
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2018-06-03T02:50:23+00:00
- Post Title: Need help with Dragon Ball Legends

Hey all, I've been trying to extract models from DB Legends on Android, pulled data from Bluestacks and now I'm stuck at streamingassetbundles. Unity/Asset Studio can't seem to read these bundles. I thought I solved it by digging into the cache, as I pulled every _data bundle from their nearly 1,000 individual folders and extracted all of them, only to find two or three models of Broly's face and that's it. So I've been back to the asset bundles folder seeing what I can do, and I can't seem to find any Unity tools that'll read the bundles in there. I can upload an asset bundle if it helps at all, any suggestions would be appreciated.
## Post #2
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-06-04T00:37:48+00:00
- Post Title: Need help with Dragon Ball Legends

Could you please upload some assets so people in here can check if they can do something?
Also, did you try Unity Studio or AssetStudio? iirc they have an option to import bundles, but seeing how you already used a bunch of Unity tools I'm guessing you probably have tried with these.
## Post #3
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2018-06-04T03:25:40+00:00
- Post Title: Need help with Dragon Ball Legends

Yeah, here's the largest file in the /streamingassetbundles/ folder.

[https://www.dropbox.com/s/m5zrpkk28m7sq ... b88c7?dl=0](https://www.dropbox.com/s/m5zrpkk28m7sqlu/53d072c5e6b51285b2f39c45134a6d854deb88c7?dl=0)

And yeah, I did try the latest versions of Unity/Asset Studios, along with Unity Asset Bundle Extractor and Disunity. I'm a little worried that all of the assets are cached as needed, but there's a "download all/download minimal" option at installation, and I selected "download all" and haven't gotten any pre-battle download bars - so the data has to be saved somewhere I would assume. Like I said, there were some unpackable _data bundles in the cache, but out of the 928 bundles I unpacked, they only contained the models and textures for Broly's face - just his face. Seems really strange. I also haven't done much with mobile Unity games though, so just the fact that I can't just open a "resources" file in the /streamingassets/ folder already had me scratching my head.  

Also I forgot to mention, I did see two DBXV2 modders on Twitter that posted pictures of Legends models and have released character mods already, so it's certainly possible. They weren't taking PMs though, so I couldn't reach them for help.
## Post #4
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-06-04T11:35:26+00:00
- Post Title: Need help with Dragon Ball Legends

Hmm... for what you're telling me, it may be not your fault but Bluestack's. 
Since I didn't use that emulator in my life, I don't know how the extraction method 
works on it, but maybe the method you use in Bluestacks to extract files 
in other games doesn't work with Legends' files at all. 

Again, since I don't use Bluestacks I don't have many solutions for you, so I apologize.
Maybe if you use the Nox method posted by Chrrox in here that will work?
If the method is similar or it doesn't work either then all we have left is to wait for 
someone more experienced to help us. Hopefully we can get the files from Legends soon.
## Post #5
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2018-06-08T15:38:56+00:00
- Post Title: Need help with Dragon Ball Legends

Happy to report I got it working! Turns out I was doing the right thing by looking into the cache, it just took some trial and error to get everything to ACTUALLY download. I ended up having to re-click Download All a few times, dick around in the battles a few times, etc., and all of the files showed up in the cache. 1,063 extracted data files later, and it looks like I've got a horribly unorganized, but COMPLETE, mess of models and textures ripe for the picking.
## Post #6
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-06-08T21:42:33+00:00
- Post Title: Need help with Dragon Ball Legends

> Reply from jflieger
>
> Happy to report I got it working! Turns out I was doing the right thing by looking into the cache, it just took some trial and error to get everything to ACTUALLY download. I ended up having to re-click Download All a few times, dick around in the battles a few times, etc., and all of the files showed up in the cache. 1,063 extracted data files later, and it looks like I've got a horribly unorganized, but COMPLETE, mess of models and textures ripe for the picking.
Oh my god I'm so happy to hear that! Would it be too much to ask to please post some images when you have the models 100% extracted and working?
## Post #7
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2018-06-10T02:29:41+00:00
- Post Title: Need help with Dragon Ball Legends

> Reply from shingenseiji
>
> Oh my god I'm so happy to hear that! Would it be too much to ask to please post some images when you have the models 100% extracted and working?
[https://imgur.com/NRo89Br](https://imgur.com/NRo89Br)

Well here's Shallot, all of the bones work but the skin is a little wonky. I also need to figure out what's going on with the textures, because there's an "ID" texture and a "Mask" texture, and the mask works and everything but I'm thinking I'm doing something wrong because I'm just getting the cel-shading lines over a gray texture. I'm assuming the ID texture somehow has color ID's embedded in it but I've never used anything like that in 3DS Max, so I have no clue what to do with it.

Edit: Apparently this site does NOT like embedding images with imgur. Or am I doing something wrong?
## Post #8
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-06-10T03:05:52+00:00
- Post Title: Need help with Dragon Ball Legends

Hmm. So the game actually uses mesh coloring instead of actual colored textures. The same happens with Xenoverse models, so funny to see Bamco doing this for every actual Dragon Ball game they make lol. The easiest way to color the model would probably be to just color the actual textures in Photoshop or any other photo editor. Since I don't really use 3DS Max either, I don't really know other method.

Anyways, hope you can find a solution soon and maybe share the game files or do a quick tutorial on how to extract the game's data!
## Post #9
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2018-06-10T04:01:24+00:00
- Post Title: Need help with Dragon Ball Legends

> Reply from shingenseiji
>
> Hmm. So the game actually uses mesh coloring instead of actual colored textures. The same happens with Xenoverse models, so funny to see Bamco doing this for every actual Dragon Ball game they make lol. The easiest way to color the model would probably be to just color the actual textures in Photoshop or any other photo editor. Since I don't really use 3DS Max either, I don't really know other method.

Anyways, hope you can find a solution soon and maybe share the game files or do a quick tutorial on how to extract the game's data!
I guess mesh coloring makes sense due to character outfits pallet swapping when you have two of the same in a battle. I have ZERO experience with Xenoverse models and textures, so this is all new to me. I'm used to standard diffuse textures and bumpmaps. lol

Actually, extracting is quite easy, all of the pain in the ass work is just navigating your way through folders and extracting all of the bundles.

First, open BlueStacks, install the game in high-res mode (download all). I transfered my mobile save to BlueStacks just in case it only saves assets based on what you've unlocked/played. Go to the options menu and select "Download All" again, to get anything it may have missed. Then, open your file manager in BlueStacks, navigate to Android/data/com.bandainamcoent.../files/UnityCache, then take the "shared" folder inside and copy it to the windows/bstsharedfolder in your root. 

Now you can close BlueStacks, open up file explorer, and go to C:\ProgramData\bluestacks\engine\userdata\sharedfolder. The "shared" folder you copied over will be in there, feel free to move it to somewhere more accessible. Now go in there, there will be almost a thousand folders, each with a _data and a _info file inside.

Type _data in the search bar, and take all 1000 of those files and move them into a single directory. You can then delete all of the empty folders and _info files. NOW, go into AssetStudio, extract folder, and point it to the directory with all of the _data files. After that finishes, go to your directory, delete all of the _data files, and type * in the search bar. Sort results by file type and move all of the asset files to the base directory. Then you can delete the empty folders, pop open AssetStudio, open the entire folder and you've got everything there. The heirarchy view is impossible to navigate due to all of the separate files only having one or two meshes inside, but the asset view is semi-organized.
## Post #10
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2018-06-11T17:37:55+00:00
- Post Title: Need help with Dragon Ball Legends

The BLueStacks method doesn't work for me. I downloaded everything, and i transfered my data. Is there anything I'm doin wrong?
## Post #11
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2018-06-13T03:19:18+00:00
- Post Title: Need help with Dragon Ball Legends

> Reply from MarioSonicU
>
> The BLueStacks method doesn't work for me. I downloaded everything, and i transfered my data. Is there anything I'm doin wrong?

What step in particular is going wrong for you? I'll see if I can help.
## Post #12
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-06-13T14:24:58+00:00
- Post Title: Need help with Dragon Ball Legends

> Reply from jflieger
>
> shingenseiji wrote:Hmm. So the game actually uses mesh coloring instead of actual colored textures. The same happens with Xenoverse models, so funny to see Bamco doing this for every actual Dragon Ball game they make lol. The easiest way to color the model would probably be to just color the actual textures in Photoshop or any other photo editor. Since I don't really use 3DS Max either, I don't really know other method.

Anyways, hope you can find a solution soon and maybe share the game files or do a quick tutorial on how to extract the game's data!
I guess mesh coloring makes sense due to character outfits pallet swapping when you have two of the same in a battle. I have ZERO experience with Xenoverse models and textures, so this is all new to me. I'm used to standard diffuse textures and bumpmaps. lol

Actually, extracting is quite easy, all of the pain in the ass work is just navigating your way through folders and extracting all of the bundles.

First, open BlueStacks, install the game in high-res mode (download all). I transfered my mobile save to BlueStacks just in case it only saves assets based on what you've unlocked/played. Go to the options menu and select "Download All" again, to get anything it may have missed. Then, open your file manager in BlueStacks, navigate to Android/data/com.bandainamcoent.../files/UnityCache, then take the "shared" folder inside and copy it to the windows/bstsharedfolder in your root. 

Now you can close BlueStacks, open up file explorer, and go to C:\ProgramData\bluestacks\engine\userdata\sharedfolder. The "shared" folder you copied over will be in there, feel free to move it to somewhere more accessible. Now go in there, there will be almost a thousand folders, each with a _data and a _info file inside.

Type _data in the search bar, and take all 1000 of those files and move them into a single directory. You can then delete all of the empty folders and _info files. NOW, go into AssetStudio, extract folder, and point it to the directory with all of the _data files. After that finishes, go to your directory, delete all of the _data files, and type * in the search bar. Sort results by file type and move all of the asset files to the base directory. Then you can delete the empty folders, pop open AssetStudio, open the entire folder and you've got everything there. The heirarchy view is impossible to navigate due to all of the separate files only having one or two meshes inside, but the asset view is semi-organized.
Ok, thanks for the detailed explanation! By the way, what file manager are you using in Bluestacks? I thought Bluestacks came with a preinstalled file manager like Nox does, but it seems like it doesn't (or if it does, I couldn't find it)
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-06-14T00:55:32+00:00
- Post Title: Need help with Dragon Ball Legends

Just use bluestacks tweaker
## Post #14
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-10-30T02:39:21+00:00
- Post Title: Need help with Dragon Ball Legends

> Reply from jflieger
>
> shingenseiji wrote:Oh my god I'm so happy to hear that! Would it be too much to ask to please post some images when you have the models 100% extracted and working?
https://imgur.com/NRo89Br

Well here's Shallot, all of the bones work but the skin is a little wonky. I also need to figure out what's going on with the textures, because there's an "ID" texture and a "Mask" texture, and the mask works and everything but I'm thinking I'm doing something wrong because I'm just getting the cel-shading lines over a gray texture. I'm assuming the ID texture somehow has color ID's embedded in it but I've never used anything like that in 3DS Max, so I have no clue what to do with it.

Edit: Apparently this site does NOT like embedding images with imgur. Or am I doing something wrong?

Could you explain how the extraction of these models works?
## Post #15
- Username: ubroly
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 21, 2020 10:13 am
- Post datetime: 2020-05-21T02:15:30+00:00
- Post Title: Need help with Dragon Ball Legends

Has anyone managed a way to extract textures correctly?
## Post #16
- Username: Arkaedus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 05, 2021 9:17 am
- Post datetime: 2021-06-05T14:18:09+00:00
- Post Title: Re: Need help with Dragon Ball Legends

Hello

I am trying to do it.

I am using bluestacks 4 and bluestacks tweaker but i dont get models. i don't find the UnityCache folder. I found unity folder and streamingassetbundles folder.

Any help is welcome. Thanks
## Post #17
- Username: asdzx34
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 16, 2019 6:52 pm
- Post datetime: 2022-02-28T14:52:59+00:00
- Post Title: Re: Need help with Dragon Ball Legends

> Reply from jflieger ↑Sun Jun 03, 2018 10:50 am at Sun Jun 03, 2018 10:50 am
>
> 
Hey all, I've been trying to extract models from DB Legends on Android, pulled data from Bluestacks and now I'm stuck at streamingassetbundles. Unity/Asset Studio can't seem to read these bundles. I thought I solved it by digging into the cache, as I pulled every _data bundle from their nearly 1,000 individual folders and extracted all of them, only to find two or three models of Broly's face and that's it. So I've been back to the asset bundles folder seeing what I can do, and I can't seem to find any Unity tools that'll read the bundles in there. I can upload an asset bundle if it helps at all, any suggestions would be appreciated.
When I extract the textures are all red. How did you extract the normal color?
[https://drive.google.com/file/d/1f7pDF8 ... p=drivesdk](https://drive.google.com/file/d/1f7pDF87G-7d3VbX3ZbS5uFcuixZmAl5g/view?usp=drivesdk)
## Post #18
- Username: Galinho
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 03, 2023 2:39 am
- Post datetime: 2023-01-02T18:47:51+00:00
- Post Title: Re: Need help with Dragon Ball Legends

Did anyone figured out how to rip these models on the current day? The UnityCache folder doesn't seem to show up anymore
## Post #19
- Username: Galinho
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 03, 2023 2:39 am
- Post datetime: 2023-01-02T21:04:13+00:00
- Post Title: Re: Need help with Dragon Ball Legends

> Reply from Galinho ↑Tue Jan 03, 2023 2:47 am at Tue Jan 03, 2023 2:47 am
>
> 
Did anyone figured out how to rip these models on the current day? The UnityCache folder doesn't seem to show up anymore

I've got the UnityCache folder to show up now, but it remains empty
