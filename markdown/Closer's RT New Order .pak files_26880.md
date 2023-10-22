## Post #1
- Username: TheMarvelousMrL
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 19, 2023 10:38 pm
- Post datetime: 2023-06-19T16:24:48+00:00
- Post Title: Closer's RT New Order .pak files

Hello. I have been looking for a way to access some models from this game. The game is Closers RT New Order which is a mobile spin off title of the original Closers Online game. I searched trough the game's files using Xplore file manager and I found these large files which I think may include files for most of the assets. Would anyone be willing to take a look into these files and help me find a way to open them and find the character models? Here is a link to them. The .pak files are in the folder ''PakCache''

[https://mega.nz/folder/Z3hhWJKa#A6UuMinugq67Na7__ApJKw](https://mega.nz/folder/Z3hhWJKa#A6UuMinugq67Na7__ApJKw)
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-06-20T00:53:57+00:00
- Post Title: Closer's RT New Order .pak files

@TheMarvelousMrL: It's built with unreal engine (4.26/4.27), so you can use any UE tools for it, like umodel or fmodel.
## Post #3
- Username: TheMarvelousMrL
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 19, 2023 10:38 pm
- Post datetime: 2023-06-20T04:26:22+00:00
- Post Title: Closer's RT New Order .pak files

So I tried Umodel and was able to look through the directory and find the location of the Character models but whenever I tried to export a model I would get an error message like this and it would crash. [https://i.imgur.com/HNxMMKq.png](https://i.imgur.com/HNxMMKq.png) I tried both 4.26 and 4.27 on the override game detection settings and got this same message. Is there a solution to this or any other methods I could try?
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-06-20T13:18:03+00:00
- Post Title: Closer's RT New Order .pak files

@TheMarvelousMrL: I've created topic for this game at [gildor's forum](https://www.gildor.org/smf/index.php/topic,8618.0.html), check it. You can also address your issues with umodel there, but it's highly recommended to view some tutorials on general usage before doing so.
## Post #5
- Username: TheMarvelousMrL
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 19, 2023 10:38 pm
- Post datetime: 2023-06-20T15:23:19+00:00
- Post Title: Closer's RT New Order .pak files

I used the version you linked me to and got it working as intended. [https://i.imgur.com/ZLUDcze.png](https://i.imgur.com/ZLUDcze.png) I can now export them and load them into blender with ease. Thank you so much for everything! you have been a huge help.
## Post #6
- Username: XtraK
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 25, 2023 2:21 pm
- Post datetime: 2023-06-25T06:57:11+00:00
- Post Title: Closer's RT New Order .pak files

> Reply from TheMarvelousMrL ↑Tue Jun 20, 2023 11:23 pm at Tue Jun 20, 2023 11:23 pm
>
> 
I used the version you linked me to and got it working as intended. https://i.imgur.com/ZLUDcze.png I can now export them and load them into blender with ease. Thank you so much for everything! you have been a huge help.

hi, can you also share with me what the method looks like?

Thank you in advance.
## Post #7
- Username: TheMarvelousMrL
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 19, 2023 10:38 pm
- Post datetime: 2023-06-30T00:08:05+00:00
- Post Title: Closer's RT New Order .pak files

First thing your going to need to do is download this version of Umodel right here [https://drive.google.com/file/d/1VN3kJc ... -zyrX/view](https://drive.google.com/file/d/1VN3kJcjv8lTxyXh8zKGQ7urYCZg-zyrX/view) This is the one Spiritovod directed me to so that I could export the assets and it will be the one you will need to use in order to export them for use in Blender. next you will want to download the official version of Umodel here. [https://www.gildor.org/en/projects/umodel#files](https://www.gildor.org/en/projects/umodel#files) once you have everything go to the folder containing the official Umodel which is called ''umodel_win32'' and copy the SDL2.dll and SDL2_64.dll files and then paste them into the folder containing the version you will be using which is in the folder called ''umodel_materials'' once everything is set and is in working order open the program and on the top bar select the folder where you have the game files stored. next on the Overide game detection settings select Unreal engine 4 on the bar on the left and then Unreal engine 4.27 for the bar on the right. Once thats done, click the Ok button and it will load the directory where all the files are stored. The character models are located in ''CM\Content\Art\Animation\Character\Player'' and the textures that go with the models are in ''CM\Content\Art\Model\Character\Player'' Now once you have found everything you want to export. Right Click the folder and select export folder content. Now you will see a couple of different settings. In the Skeletal mesh and static mesh bars select glTF 2.0 for both. for the texture export settings you can ether chose between PNG or TGA. select the texture format of you choice and then once all Thats done click Ok and Everything you exported will be in a folder called ''UmodelExport'' which is located in the same folder as the application you just used. Now open up Blender, go to Import and select glTF 2.0 and go to the location of the character and select the Body, Head and weapon pieces of the character models and import into blender. from there you are free to mess around with the models and assign the textures and export them at your leisure. Hopefully this helps and good luck!
## Post #8
- Username: XtraK
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 25, 2023 2:21 pm
- Post datetime: 2023-06-30T08:41:24+00:00
- Post Title: Closer's RT New Order .pak files

> Reply from TheMarvelousMrL ↑Fri Jun 30, 2023 8:08 am at Fri Jun 30, 2023 8:08 am
>
> 
First thing your going to need to do is download this version of Umodel right here https://drive.google.com/file/d/1VN3kJc ... -zyrX/view This is the one Spiritovod directed me to so that I could export the assets and it will be the one you will need to use in order to export them for use in Blender. next you will want to download the official version of Umodel here. https://www.gildor.org/en/projects/umodel#files once you have everything go to the folder containing the official Umodel which is called ''umodel_win32'' and copy the SDL2.dll and SDL2_64.dll files and then paste them into the folder containing the version you will be using which is in the folder called ''umodel_materials'' once everything is set and is in working order open the program and on the top bar select the folder where you have the game files stored. next on the Overide game detection settings select Unreal engine 4 on the bar on the left and then Unreal engine 4.27 for the bar on the right. Once thats done, click the Ok button and it will load the directory where all the files are stored. The character models are located in ''CM\Content\Art\Animation\Character\Player'' and the textures that go with the models are in ''CM\Content\Art\Model\Character\Player'' Now once you have found everything you want to export. Right Click the folder and select export folder content. Now you will see a couple of different settings. In the Skeletal mesh and static mesh bars select glTF 2.0 for both. for the texture export settings you can ether chose between PNG or TGA. select the texture format of you choice and then once all Thats done click Ok and Everything you exported will be in a folder called ''UmodelExport'' which is located in the same folder as the application you just used. Now open up Blender, go to Import and select glTF 2.0 and go to the location of the character and select the Body, Head and weapon pieces of the character models and import into blender. from there you are free to mess around with the models and assign the textures and export them at your leisure. Hopefully this helps and good luck!

Thanks for the information, I'll try it as soon as I have free time later.


Edit/update :
I've been trying it since yesterday, the result was successful, thank you very much for the complete guide you gave, it really helped me and I really appreciate it
