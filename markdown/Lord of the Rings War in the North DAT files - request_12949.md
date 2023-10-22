## Post #1
- Username: Ditta
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 13, 2015 11:07 pm
- Post datetime: 2015-06-15T01:09:33+00:00
- Post Title: Lord of the Rings War in the North DAT files - request

Hello! Is there anyone who can help me to open .dat files from the game Lord of the Rings War in the North? I posted my question already here - [viewtopic.php?f=10&t=12940](http://forum.xentax.com/viewtopic.php?f=10&t=12940), but it seems I made a mistake with the thread, they look more like models in an unknown format than archives. So I post my request here now.
These files may contain 3D landscapes and props, but I cannot find any DAT extractor, able to open them. The game exploits the Dark Alliance game engine, the same as in Baldur's Gate Dark Alliance and Fallout: Brotherhood of Steel. I haven't played in these games and don't know if they use dat format or any other for 3D. If you have dealt with the Snowblind game engine and know how to open such files and which tool to use, please help me by advice. I want to extract 3D geometry from these files, maybe convert it to OBJ or import to 3D Max etc. Here is one sample of such archives - [http://nekaka.com/d/4gP3vpyrFB](http://nekaka.com/d/4gP3vpyrFB) . It's the content of a location folder Lorien (architecture, props etc). Thank you for any participation, if you are willing to help. I would be very grateful to any helper.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-15T08:46:33+00:00
- Post Title: Lord of the Rings War in the North DAT files - request

using hex2obj (view link in my sig):



lorien_treehouse_01.JPG (46.89 KiB) Viewed 208 times



At offset 8 and 16 of the FVF block there seem to be half float normals.
uvs not found so far. (You may try 8 for uv preview - could be uvs but guess: no.)
## Post #3
- Username: Ditta
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 13, 2015 11:07 pm
- Post datetime: 2015-06-16T00:06:51+00:00
- Post Title: Lord of the Rings War in the North DAT files - request

Wow! I cannot believe it! It seems you solved my problem. I tested it by myself on the same file with the same settings from your screenshot and it seems to work nice, I can see the mesh in the Mesh viewer. But I cannot export OBJ when choosing Save as mesh, and I cannot find test.obj which is overwritten. How to save meshes in your tool? And, what is mor important, how to analyse these files by myself - which HEX editor is better to use and what must be the start point of analyzing? I ve read your tut, but I'm a noob in programming and need a bit of explanation, even though for these particular kind of files.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-16T08:07:36+00:00
- Post Title: Lord of the Rings War in the North DAT files - request

> Reply from Ditta
>
> I can see the mesh in the Mesh viewer. But I cannot export OBJ when choosing Save as mesh,are you trying to write to a folder which you don't have write access rights for?

> and I cannot find test.objdoesn't make sense to me. Seeing the mesh in the Mesh viewer means:
test.obj must exist (in the same folder where your model resides).

> And, what is mor important, how to analyse these files by myself -read, learn, try.

> which HEX editor is better to useany should do - for example Tiny Hexer. But depends on your personal preferences. 

> and what must be the start point of analyzing? I ve read your tut, but I'm a noob in programming and need a bit of explanation, even though for these particular kind of files.read it again, try the example, understand the example. The tutorial "is" the explanation.
If there's any vagueness help me to improve the tutorial.

You don't need programming skills but an understanding of data formats such as floats, words and integers.
## Post #5
- Username: Ditta
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 13, 2015 11:07 pm
- Post datetime: 2015-06-16T16:15:58+00:00
- Post Title: Lord of the Rings War in the North DAT files - request

> Reply from shakotay2
>
> Ditta wrote:I can see the mesh in the Mesh viewer. But I cannot export OBJ when choosing Save as mesh, 
are you trying to write to a folder which you don't have write access rights for?
and I cannot find test.objdoesn't make sense to me. Seeing the mesh in the Mesh viewer means:
test.obj must exist (in the same folder where your model resides).

Thanks, I got it! I found test.obj and the exported mesh at last, I did not even guess the utility exports them to folder with original dat files. Though all this process is a bit trycky, but I'll give it a try, because it seems there's no other way to extract geometry from these files. Although this gaming dat format should not differ so much from other dat formats for hundreds of other games.
