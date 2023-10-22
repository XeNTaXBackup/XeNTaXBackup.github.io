## Post #1
- Username: skyassasin16
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 30, 2011 12:42 pm
- Post datetime: 2011-07-30T05:28:28+00:00
- Post Title: DOAX2 - Noesis to 3ds Max Help

I am trying to extract doax2 files using a tool called 'noesis'. Everything works fine but I can get it to 3ds Max properly, 
I am using 3ds Max 2010 32-bit
I tried a couple of things:

1. I try to export from noesis with output file type as wavefront obj, i don't change the preset settings. Then, it seems that 3ds max has a default obj importer so i try it out, again i don't change the preset settings. Then it will show an error "matlib not found" and then it got imported without the textures.

2. Next md5mesh, I downloaded an importer from here: [http://www.katsbits.com/tools/](http://www.katsbits.com/tools/)for 3ds Max, but it say that there is an error in some line of the script, then nothing gets imported

3. i tried collada - dae file,. it says  -Warning: The transform of node "VisualSceneNode1" is not compatible with FBX, so it is baked into TRS. It seems that it gets the texture but when I try to render it out, the hair of any character is blocking most of its face content, as like in this image: [http://www.imagebam.com/image/d832c6142745427](http://www.imagebam.com/image/d832c6142745427)

Also, I noticed that the model was not really smooth out even if i try to modify their smoothing groups. I'm not really a pro at Max, maybe I am doing something wrong so please help. All I need is the model that I am actually seeing in the Noesis to be in Max. Thanks in advance
## Post #2
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-07-30T07:47:37+00:00
- Post Title: DOAX2 - Noesis to 3ds Max Help

> Reply from skyassasin16
>
> I am trying to extract doax2 files using a tool called 'noesis'. Everything works fine but I can get it to 3ds Max properly, 
I am using 3ds Max 2010 32-bit
I tried a couple of things:

1. I try to export from noesis with output file type as wavefront obj, i don't change the preset settings. Then, it seems that 3ds max has a default obj importer so i try it out, again i don't change the preset settings. Then it will show an error "matlib not found" and then it got imported without the textures.

2. Next md5mesh, I downloaded an importer from here: http://www.katsbits.com/tools/for 3ds Max, but it say that there is an error in some line of the script, then nothing gets imported

3. i tried collada - dae file,. it says  -Warning: The transform of node "VisualSceneNode1" is not compatible with FBX, so it is baked into TRS. It seems that it gets the texture but when I try to render it out, the hair of any character is blocking most of its face content, as like in this image: http://www.imagebam.com/image/d832c6142745427

Also, I noticed that the model was not really smooth out even if i try to modify their smoothing groups. I'm not really a pro at Max, maybe I am doing something wrong so please help. All I need is the model that I am actually seeing in the Noesis to be in Max. Thanks in advance

Download opencollada and your problem is solved,
## Post #3
- Username: skyassasin16
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 30, 2011 12:42 pm
- Post datetime: 2011-07-31T07:18:53+00:00
- Post Title: DOAX2 - Noesis to 3ds Max Help

OpenCollada works great,. thanks man!   Though there are still some minor texture which I guess I can do it on my own. Like for for example the image used by the texture of hair was not interlaced (don't know the exact term),  So it appears that its just a flat mesh without hair strand's tips. Anyways, thanks man!!
