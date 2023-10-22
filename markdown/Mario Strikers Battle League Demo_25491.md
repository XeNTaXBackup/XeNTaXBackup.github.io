## Post #1
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-04T21:02:08+00:00
- Post Title: Mario Strikers Battle League Demo

This Noesis plugin currently supports meshes with normals, uvs, skinning info. Animations are partially supported and auto texturing (normal + diffuse) is available for the main characters and their gears. A small UI util is available to load the latter more easily, details will be given below.
It also supports loading individual textures and UI elements.

Do not expect anything more than fixes for major bugs i.e. I'm not planning to reverse the missing animation semantics (I just grabbed the ones from my previous work on Luigi's Mansion 3) or anything similar.



Read the instructions carefully to get the most of this plugin.

Archive Extraction

-You can extract the dict/data pairs using quickbms and the attached script originally made by DKDave , that I modified slightly. It will create a folder along with a "dict_d" file. The file to be given as input is the one with the .dict extension. The rest happens in Noesis.


 strik_bms.zip
(682 Bytes) Downloaded 110 times



-In Noesis, right-click on the "dict_d" file and click on "extract dict_d". Wait for the extraction to complete, you'll see an "Asset extracted" prompt when it's done. You will have several new folders, the ones with assets you'll be able to open are "Models", "Textures" (which has the textures and the sprites) and "Skeletons".

Gear System

-The characters in this game are split in several parts, the models located in the character folders only have the heads. To make it easier to view the assets, you'll have to use the gear UI.

VIDEO EXAMPLE

-To do that first extract the gear dict/data pair located in your dump's GearSets folder (just apply the "archive extraction" steps). Then open the noesis script in a text editor and put the "Models" folder's adress next to the "gearModelFolder" option, at the top. You only have to do this once (unless you move your extraction folder later obviously).
-That's it, now when you find your character's face model, just right click and click "gear equip" like in the video. The gears adapted to this character will be proposed, then just do like in the video to equip your character and animate him  if you want to. A "load texture" option has been added since it was recorded, make sure to only do that when you're done choosing your complete set or it'll be slower to load due to all the loading/assigning/untiling overhead introduced.

Last notes :
-While I only apply the diffuse/normal maps on the character, all the character related textures will be loaded. You can preview these under "Tools->Data viewer"->textures and they'll be exported too.
-Textures/Sprites can be seen directly by opening whatever file located in the "Textures" folders.
-NLG seems to use a black placeholder for the outfits' parts that are supposed to have the team's color.
-Contrary to LM3, the concept of "animation packs" doesn't exist here. Fortunately anims related to a character seem to always be located in his dict/data pair so it's not a problem.
-Some skeletons won't match some of the little secondary models and some will rarely be misplaced. Some anims will also look wrong. All this would need more research but I don't have the time for that, consider this plugin as final, unless other people contribute.

That's it.

[https://github.com/Joschuka/fmt_strik](https://github.com/Joschuka/fmt_strik)
## Post #2
- Username: MarioBrosNet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 06, 2022 7:25 am
- Post datetime: 2022-06-05T23:49:20+00:00
- Post Title: Mario Strikers Battle League Demo

When I attempt to extract the dict_d files, It gives me a Python error. 
"RuntimeError: Tried to set offset beyond buffer size. (6000 > 64)"
## Post #3
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-06T08:50:50+00:00
- Post Title: Mario Strikers Battle League Demo

> Reply from MarioBrosNet ↑Mon Jun 06, 2022 7:49 am at Mon Jun 06, 2022 7:49 am
>
> 
When I attempt to extract the dict_d files, It gives me a Python error. 
"RuntimeError: Tried to set offset beyond buffer size. (6000 > 64)"

Which dict/data pair gives you this error ?
## Post #4
- Username: MarioBrosNet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 06, 2022 7:25 am
- Post datetime: 2022-06-06T14:39:44+00:00
- Post Title: Mario Strikers Battle League Demo

Every pair I've tried so far gives me this error. I've tried Mario, Luigi, Wario, and Waluigi's. I've also tried the GearSets as well. I checked the 'all known formats' to see if Noesis could read strikers' models once the python script was put in, but they don't appear to be on the list for some reason.
## Post #5
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-06T15:17:28+00:00
- Post Title: Mario Strikers Battle League Demo

Alright please post all the steps you did, you must be doing something wrong at some point.
## Post #6
- Username: MarioBrosNet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 06, 2022 7:25 am
- Post datetime: 2022-06-06T15:33:29+00:00
- Post Title: Mario Strikers Battle League Demo

I used quickbms and the bms script to extract the dict/data from the dump, and I left the dict_d files in a folder on my desktop. Then I placed the python script into the python folder where it's supposed to go. After that, I copied the folder path of the GearSet's models folder location, and I pasted the path into the python script in the quotations after "gearModelFolder". After that, I tried to hop into Noesis to extract the dict_d files, and I  started to get that error.
## Post #7
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-06T15:35:45+00:00
- Post Title: Mario Strikers Battle League Demo

> Reply from MarioBrosNet ↑Mon Jun 06, 2022 11:33 pm at Mon Jun 06, 2022 11:33 pm
>
> 
I used quickbms and the bms script to extract the dict/data from the dump, and I left the dict_d files in a folder on my desktop. Then I placed the python script into the python folder where it's supposed to go. After that, I copied the folder path of the GearSet's models folder location, and I pasted the path into the python script in the quotations after "gearModelFolder". After that, I tried to hop into Noesis to extract the dict_d files, and I  started to get that error.

Yeah the error is probably because you moved the dict_d file, I forgot to mention but you're supposed to let it untouched, next to the original dict/data.
## Post #8
- Username: MarioBrosNet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 06, 2022 7:25 am
- Post datetime: 2022-06-06T15:39:40+00:00
- Post Title: Mario Strikers Battle League Demo

Ooh, I gotcha. Let me give it another try
## Post #9
- Username: MarioBrosNet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 06, 2022 7:25 am
- Post datetime: 2022-06-06T15:57:25+00:00
- Post Title: Mario Strikers Battle League Demo

It still seems to give me that error. I did change the models folder path within the python script after exporting dict_d to the dump, but the extraction process within Noesis won't execute properly. "Runtime Error: Tried to set offset beyond buffer size. (3284 > 64)"
## Post #10
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-06T16:24:54+00:00
- Post Title: Mario Strikers Battle League Demo

Can you screenshot me the whole error message so I can see at which line this happens ? Also make sure that Noesis is up to date (tools -> check for updates).

EDIT : Moved to DMs. It turns out that this error happens when trying to extract the .data file with quickbms while it's supposed to get the .dict as input. The main post has been edited accordingly to avoid confusion.
## Post #11
- Username: xdarkmario
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 01, 2015 5:19 am
- Post datetime: 2022-06-19T03:24:50+00:00
- Post Title: Mario Strikers Battle League Demo

can we use this to mess around with other files not model related? like text and other elements?
## Post #12
- Username: yo711lol
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 23, 2022 10:49 am
- Post datetime: 2022-07-23T03:48:33+00:00
- Post Title: Mario Strikers Battle League Demo

Hi, im trying to export Daisy's model but i think the script isn't updated to the newest version. Do i need to add the charaGearMap for Daisy at the script?
## Post #13
- Username: xdarkmario
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 01, 2015 5:19 am
- Post datetime: 2022-07-23T13:38:37+00:00
- Post Title: Mario Strikers Battle League Demo

> Reply from yo711lol ↑Sat Jul 23, 2022 11:48 am at Sat Jul 23, 2022 11:48 am
>
> 
Hi, im trying to export Daisy's model but i think the script isn't updated to the newest version. Do i need to add the charaGearMap for Daisy at the script?

yea the tool needs updating as of now, i looked into the code a bit but it looks like we need to find out the byte offsets of the new characters. You also (if you haven't already) might have to extract a fresh updated copy of the Persistent file. i got some of her files to extract but the script cant output a model file... 
Got to wait on the devs.
## Post #14
- Username: yo711lol
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 23, 2022 10:49 am
- Post datetime: 2022-07-23T23:37:35+00:00
- Post Title: Mario Strikers Battle League Demo

I have succeeded extracted the model of her face but the gear it's on DLC1.dict and that gave me this error
[imagen_2022-07-23_183441009.png](https://xentaxbackup.github.io/file/22550_imagen_2022-07-23_183441009.png)
## Post #15
- Username: xdarkmario
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 01, 2015 5:19 am
- Post datetime: 2022-07-26T23:23:33+00:00
- Post Title: Mario Strikers Battle League Demo

> Reply from yo711lol ↑Sun Jul 24, 2022 7:37 am at Sun Jul 24, 2022 7:37 am
>
> 
I have succeeded extracted the model of her face but the gear it's on DLC1.dict and that gave me this error

yep, thats what i was talking about, that offset error i believe is because the script is set a kind of way that it references the byte offset and pulls it together
## Post #16
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2022-07-29T13:47:24+00:00
- Post Title: Re: Mario Strikers Battle League Demo

Any idea if this is gonna be updated for the DLC?
## Post #17
- Username: xdarkmario
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 01, 2015 5:19 am
- Post datetime: 2022-08-07T11:06:56+00:00
- Post Title: Re: Mario Strikers Battle League Demo

dont think so, on the first post he said "Do not expect anything more than fixes for major bugs"  so i guess its as is 
im working on bruteforce ripping now, ill report back when i get somewhere with it.
## Post #18
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2022-08-26T15:00:37+00:00
- Post Title: Re: Mario Strikers Battle League Demo

> Reply from xdarkmario ↑Sun Aug 07, 2022 7:06 pm at Sun Aug 07, 2022 7:06 pm
>
> 
dont think so, on the first post he said "Do not expect anything more than fixes for major bugs"  so i guess its as is 
im working on bruteforce ripping now, ill report back when i get somewhere with it.

Did you make any progress?
## Post #19
- Username: xdarkmario
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 01, 2015 5:19 am
- Post datetime: 2022-09-08T10:17:58+00:00
- Post Title: Re: Mario Strikers Battle League Demo

a bit but im stuck again, exports in raw format so i have to find out where the model begins and junk data  ends
## Post #20
- Username: xdarkmario
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 01, 2015 5:19 am
- Post datetime: 2022-09-25T11:14:14+00:00
- Post Title: Re: Mario Strikers Battle League Demo

Daisy ready!

[https://www.deviantart.com/xdarkmario/a ... -930754500](https://www.deviantart.com/xdarkmario/art/Daisy-mario-strikers-battle-league-No-color-b1-930754500)
## Post #21
- Username: Rias444
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 03, 2023 9:54 pm
- Post datetime: 2023-01-03T13:59:14+00:00
- Post Title: Re: Mario Strikers Battle League Demo

hi I have this issue no module named noewin
how fix it 
thanks
## Post #22
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-01-04T00:49:18+00:00
- Post Title: Re: Mario Strikers Battle League Demo

> Reply from Rias444 ↑Tue Jan 03, 2023 9:59 pm at Tue Jan 03, 2023 9:59 pm
>
> 
no module named noewin
he should be. 
download Noesis on a new one. it's in the plugins folder "..\Noesis\plugins\python\noewin.py"
