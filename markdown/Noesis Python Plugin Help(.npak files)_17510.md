## Post #1
- Username: Charles01
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 06, 2018 5:26 am
- Post datetime: 2018-01-07T22:45:53+00:00
- Post Title: Noesis Python Plugin Help(.npak files)

Hello XeNTaX members,
I've recently got into creating GMOD PMs and I wanted to create some player models of characters from One Piece Burning Blood. So I searched for some extracted 3D models from the game. I found some, but they weren't the ones I was looking for. I believe there is a person who knows how to view the models in Noesis and export them to .fbx files, but I think he's inactive as he didn't reply to my PM. So I decided to try learning how to extract 3D models this week to get them myself. I was able to extract .scz files from the .cpk file in the steam folder from some script I found online and found .npak, .npkv, and .npki files from the .scz files using a different script I found online. From what I found online, ".npk(.npak) is model information,.npki is raw model vertex and face data, and .npkv is raw texture buffer." I have no idea what .npki and .npkv are for, but .npak seems like the most important from what I've seen in a hex editor and in a picture on another forum showing the .npak file opened in Noesis with the model. In the .npak file, there were the file names that ended with .bmp and .tga, which I assumed were the textures. Also, the person who uploaded several models from the game kept the same names of the bones, textures, and materials as they appear in the .npak files. I was following Chrrox's tutorial on viewing a basic model in Noesis, but I got lost. I had no idea what to do at the vertex step. For some reason, I can't attach anything to this post. So here's a link with the .npak, .npkv, .npki, and Noesis Python script. 
[https://mega.nz/#!Lkt2UTRI!4x2ETn9hjRQr ... gikczBceAc](https://mega.nz/#!Lkt2UTRI!4x2ETn9hjRQrKGV8RVL6mPd9NsUvPYK7ugikczBceAc)
Any help is greatly appreciated. Thanks in advance.

Edit:
If you want to know where I got some of my information, just Google search, "one piece burning blood 3d models." The first two links that show up are what I am referencing.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-01-14T11:12:54+00:00
- Post Title: Noesis Python Plugin Help(.npak files)

> Reply from Charles01
>
> I had no idea what to do at the vertex step.before creating scripts I'd suggest to get some understanding of the npki model's 3D format:



char_071-npki.jpg (161.07 KiB) Viewed 346 times

(using hex2obj, view link in my sig)
## Post #3
- Username: Charles01
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 06, 2018 5:26 am
- Post datetime: 2018-01-19T17:24:26+00:00
- Post Title: Noesis Python Plugin Help(.npak files)

> Reply from shakotay2
>
> Charles01 wrote:I had no idea what to do at the vertex step.before creating scripts I'd suggest to get some understanding of the npki model's 3D format:
The attachment char_071-npki.jpg is no longer available(using hex2obj, view link in my sig)
Sorry for the late reply. After a couple of days of no response, I assumed no one was interested. I took your advice and was successfully able to export the model as an .obj file. Your program's tutorial helped me understand what values I should be looking for, such as the "scrambled alphabet" for face indices. Thank you so much!  
[Screenshot (1).png](https://xentaxbackup.github.io/file/13818_Screenshot (1).png)
## Post #4
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2018-08-24T04:33:03+00:00
- Post Title: Noesis Python Plugin Help(.npak files)

> Reply from Charles01
>
> shakotay2 wrote:Charles01 wrote:I had no idea what to do at the vertex step.before creating scripts I'd suggest to get some understanding of the npki model's 3D format:
char_071-npki.jpg(using hex2obj, view link in my sig)
Sorry for the late reply. After a couple of days of no response, I assumed no one was interested. I took your advice and was successfully able to export the model as an .obj file. Your program's tutorial helped me understand what values I should be looking for, such as the "scrambled alphabet" for face indices. Thank you so much!

this is awesome! could i possibly ask for a screenshot of what the start of the faces and vertices look like in a hex editor? id like to give this a shot myself but i really dont know where to start
