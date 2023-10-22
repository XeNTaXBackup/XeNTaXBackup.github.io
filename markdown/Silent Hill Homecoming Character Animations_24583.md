## Post #1
- Username: superuser
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 08, 2021 9:16 pm
- Post datetime: 2021-10-08T13:59:01+00:00
- Post Title: Silent Hill Homecoming Character Animations

(Havok-5.1.0 Skeletal Animation)

I extracted the files from the PAK archives and found the animations as MSKL files. How to convert them to FBX?
Here is an example of Smog walking animation:


 M04_SGTOWN2out.objSmog_WalkF1.zip
(42.55 KiB) Downloaded 31 times



Thank you in advance!
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-10-08T14:59:09+00:00
- Post Title: Silent Hill Homecoming Character Animations

Perhaps older Havok types don't support plugins.
but you may be able to play the animation on HavokTool. First, you need the skeleton hkx as well as the anime hkx.
Look for skeleton hkx.
## Post #3
- Username: superuser
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 08, 2021 9:16 pm
- Post datetime: 2021-10-08T16:49:33+00:00
- Post Title: Silent Hill Homecoming Character Animations

There are no HKX files, the models are MDL format. I use Noesis to export the models to FBX and it works, but an error appear when I try to export the MSKL files (The file type could not be determined.)
I downloaded Havok Content Tools, but got an error when try to import the MSKL file.
This is Smog model:


 M04_SGTOWN2out.objSmog.part1.rar
(200 KiB) Downloaded 14 times
## Post #4
- Username: superuser
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 08, 2021 9:16 pm
- Post datetime: 2021-10-08T16:50:05+00:00
- Post Title: Silent Hill Homecoming Character Animations

... and part 2:


 M04_SGTOWN2out.objSmog.part2.rar
(131.31 KiB) Downloaded 16 times
## Post #5
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-10-08T19:07:25+00:00
- Post Title: Silent Hill Homecoming Character Animations

Sh homecomming runs on the slayer engine, right?
## Post #6
- Username: superuser
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 08, 2021 9:16 pm
- Post datetime: 2021-10-08T20:33:44+00:00
- Post Title: Silent Hill Homecoming Character Animations

yes, thank you for mentioning that
## Post #7
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-10-09T00:21:26+00:00
- Post Title: Silent Hill Homecoming Character Animations

hmm, this is mesh file.
Games that utilize havok usually keep the skeleton hkx separate from the mesh.
Even if the mesh itself has unique skeleton data. It is used for collision detection and physical calculation of havok.
Of course, there are exceptions depending on the game.

Since havok animations use special specifications for bone indexes, skeleton hkx should also be present in most cases.
If you look for it and you can't find it, it's completely unavailable.
## Post #8
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-10-09T01:57:18+00:00
- Post Title: Silent Hill Homecoming Character Animations

I used old bms because I didn't know how to decompress pak properly. It requires a lot of manual fixes, but it's not unreadable.

However, I'm not sure if it can output because it uses animation compression (delta), which was only used in older versions.
Also, Wavelet compression is used for lot animation, which is not compatible with the PredatorCZ plugin.
[alex.png](https://xentaxbackup.github.io/file/20979_alex.png)
## Post #9
- Username: superuser
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 08, 2021 9:16 pm
- Post datetime: 2021-10-09T14:10:58+00:00
- Post Title: Silent Hill Homecoming Character Animations

I used Noesis "Batch Process" to decompress the PAK files. All sounds (.ogg), textures (.syt), models (.mdl) are fine...
If Noesis can read and convert MDL to FBX, why not MSKL?
I see that you have achieved something significant so far. Can you play the animation?



smog.jpg (108.34 KiB) Viewed 175 times
## Post #10
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-10-09T15:09:36+00:00
- Post Title: Silent Hill Homecoming Character Animations

oh, PAK can be decompressed with noesis, I'll see tomorrow.
Since the result is not organized in the bms extract, I only saw the Alex file.

Animation can be played on HavokTool, but due to the compression format, it cannot be output to fbx etc.
Some utilize Delta compression, so these may be available in the Predator CZ plugin.

Most of all, tracing is easy if it can be played with HavokTool. Even if you can't output with fbx, if you have the patience,
you can imitate the animation and create it yourself.

----------------------

As is often the case with games that use custom Havok, it seems that indexing is special. Some anime give good results, others don't.
And Delta compression is likely to be used only for small animations such as mouth movements.
Also, this was also a custom format and did not have the track assignments that were originally required.

It is unlikely that you will get good results, but if you are more interested, please give me a PM. I will tell you how to edit hkx
(it depends on the file, so it will take some time to understand. It is not suitable for forums)

*The image is a kind of smog animation, the lower body looks normal, but the upper body is broken. Also, the animation Smog_WalkF1 was acquired completely broken.
[smog.png](https://xentaxbackup.github.io/file/21002_smog.png)
## Post #11
- Username: superuser
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 08, 2021 9:16 pm
- Post datetime: 2021-10-10T22:30:58+00:00
- Post Title: Silent Hill Homecoming Character Animations

How did you get the HKX files and what will be the result if you import them into Noesis and 3ds max with these Havok plugins?

[https://lukascone.wordpress.com/2019/05 ... is-plugin/](https://lukascone.wordpress.com/2019/05/13/havok-noesis-plugin/)

[https://lukascone.wordpress.com/2019/03 ... ax-plugin/](https://lukascone.wordpress.com/2019/03/21/havok-3ds-max-plugin/)

I really appreciate your help, but fixing and recreating animations...    I would like to avoid manual work as much as possible.
