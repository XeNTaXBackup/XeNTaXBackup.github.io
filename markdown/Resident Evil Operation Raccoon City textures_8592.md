## Post #1
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-03-19T08:54:01+00:00
- Post Title: Resident Evil Operation Raccoon City textures

Hi !

First, I have to say I know nothing with this kind of thing... I thing I've done a lot to be here haha

I'm looking for images/artworks inside the REORC files, on Xbox 360. I extracted the files from the ISO and have several files. Most of the files are in SSG. I used Noesis and the code given by MrAdults and I've been able to open some files... To have more files with no extensions. I'm particularly interested in the "gallery textures" file. It's a SSG, so I extract what's inside with Neosis. I now have 106 elements called "gallery_galleryitem001" to "gallery_galleryitem106". From now, I'm happy to be there and not being crazy yet haha

Since the files have no extension, I tried multiples things. Renaming them as PNG (Why not ? ) and DDS but nothing work. I opened them with Notepad and then, I found a line a the beginning (The only thing we can understand) : Build\data\temp\x360\UI\Textures\gallery\galleryitem001.dds
If there is DDS so there is an image. And hopefully an amazing artwork is waiting for me. The fact is that I don't know where is this file ! When I extracted the files from the ISO, I never had a "Build\data\temp\x360" destination. Nothing like that. I was like "Hum... I missed something ?". And I think the answer is yes. While checking the size of the folder with the extracted files from the ISO I noticed it was only 4,5Gb, while the ISO is 7,5Gb. I miss 3Gb. I used XBOX 360 ISO EXTRACT and another software but I always ended up with 4,5Gb of files. I don't know how nor why. And many unknown files from the ISO have a line with a DDS file in "Build\data\temp\x360\UI\Textures\...".

But maybe I'm looking to far and the answer is right under my eyes. Maybe the "gallery_galleryitem001" file has an image inside ? But I don't know how to open it. So maybe you can help me !

And maybe it already happened to you to have so missing part of an extracted ISO ?

I put some sample of the files in this archive :

```
http://www.mediafire.com/?5jiq2z2szv88g22
```


(PS : I added some XPR files in it but since I made the RAR I found how to open them and found some cool artworks  )

And thank you for your help

(And sorry for my long post)

EDIT
I am so so sorry for having made a useless threat ! I just had the idea to rename the "gallery_galleryitem001" file as a XPR file and it's working ! I have the all the artworks... I think you can delete this topic... So sorry... :/
## Post #2
- Username: Qwertyn
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 18, 2012 8:54 pm
- Post datetime: 2012-03-19T09:09:10+00:00
- Post Title: Resident Evil Operation Raccoon City textures

> Reply from Nemesiscv
>
> I found how to open them and found some cool artworks
so what did you used to extract those .XPR files?I tried few programs,but they didn't  work.

ps I mean how did you managet to open xpr and view textures?
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-19T11:58:49+00:00
- Post Title: Resident Evil Operation Raccoon City textures

why did u open a new thread !!!!! And also in wrong section!
## Post #4
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-03-20T05:55:21+00:00
- Post Title: Resident Evil Operation Raccoon City textures

> Reply from michalss
>
> why did u open a new thread !!!!! And also in wrong section!
Wrong section ? I though I was in "Game Archive Research", because my problem was that I was unable to open archives files from the game to extract images, since I didn't know what were they.

And I opened the threat because I was lost. But the time that the file got uploaded on mediafire and to click on "submit" and a few moment after, I found the answer. I was first lost, I needed help. So I opened this thread. Then, I found the answer by myself.

> Reply from Qwertyn
>
> Nemesiscv wrote:I found how to open them and found some cool artworks
so what did you used to extract those .XPR files?I tried few programs,but they didn't  work.

ps I mean how did you managet to open xpr and view textures?

I used Noesis with two plugins : 

```
http://www.mediafire.com/?4qt5by4k4q72cdj
```

(A code from MrAlduts on another thread)

```
http://www.mediafire.com/?cisf6cyusc3h73c
```


The first is to open the SSG files, archives file. Noesis will extract what's inside of it. You should have some files with no extension. Rename them as ".XPR" (If you think it's textures), and you'll be able to extract and open the DDS file inside with Noesis. Then, export the image.

But. 2 problems.
1 ) Some extracted images has some artifacts on them, while some others are perfect, example :  
One perfect image I uploaded on my website's FB page :

```
https://www.facebook.com/photo.php?fbid=349601611750497&set=a.188365891207404.41832.131236410253686&type=3
```


One image with troubles...

```
http://yfrog.com/mm5nayvj
```


And I don't know how to fix it.

2 ) Sometimes, when you extract the files from a SSG archives, you have directly XPR while usually you have files with no extensions. And surprisingly... These XPR files cannot be opened... So I missed maybe something !

Hope I helped you.
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-20T19:58:46+00:00
- Post Title: Resident Evil Operation Raccoon City textures

In the SSG archives, some extensionless files are raw DXT, some files with .xpr extensions are raw DXT, and some files with .xpr extensions are actual XPR2 files. Hit and miss. The script I posted is just to test/preview raw DXT data. It also looks corrupt on some files because they might not be tiled, might not be endian-swapped, or might use a compressed normals format like noesis.FOURCC_DXT1NORMAL, noesis.FOURCC_ATI1, or noesis.FOURCC_ATI2.
## Post #6
- Username: Jodan
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 02, 2010 11:12 am
- Post datetime: 2012-03-21T16:47:59+00:00
- Post Title: Resident Evil Operation Raccoon City textures

Nemesiscv, I was able to replicate what you did to view XPR files that had no file extension, but was curious why XPR files that had already included the extension are not working? 

I added the "fmt_XBOX_360_XPR.py" plugin to Noesis but was still unable to view the above mentioned XPR files (see error message below) and if I used Noesis default settings (exclude any added plugins) I instead get the error "file could not be previewed" ; but the weird thing is, a friend of mine told me that he uses no added plugins and can preview these type of XPR files without a issue and view the dds image)

ALSO what is the directory where the game's concept art is located? (update: found it "\ui\gallery_textures.ssg" in case anyone is interested)



Using the above python script I get this error...
-------------------------------------------------------------------
Noesis Python Error                                                               [X] 
-------------------------------------------------------------------
Traceback (most recent call last): 
  File 
"W:\noesis\noesisv3851\plugins\python\fmt_XBOX_360_XPR.py", 
line 22, XPRCheckType
 Header = bs.readBytes(4).decode("ASCII") 
UnicodeDecodeError: 'ascii' codec can't decode byte 0x80 in postion 0: 
ordinal not in range(128)
--------------------------------------------------------------------
## Post #7
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-21T21:19:14+00:00
- Post Title: Resident Evil Operation Raccoon City textures

> Reply from Jodan
>
> Nemesiscv, I was able to replicate what you did to view XPR files that had no file extension, but was curious why XPR files that had already included the extension are not working?

> Reply from MrAdults
>
> In the SSG archives, some extensionless files are raw DXT, some files with .xpr extensions are raw DXT, and some files with .xpr extensions are actual XPR2 files.
## Post #8
- Username: Jodan
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 02, 2010 11:12 am
- Post datetime: 2012-03-25T05:49:20+00:00
- Post Title: Resident Evil Operation Raccoon City textures

ok, thanks Adults, I had missed your earlier post about this.. I noticed you wrote another more generic script for reading XPR archive in another thread, but found I had to change the texture size manually to view certain size textures correctly(though some still have a section of the image show up improperly, most of the time with proper dimensions this was fixed).  You had mentioned that this script could be altered to scan for h and w automatically from within the script and was curious as to what would need to be done (or is this mute being that chrrox will include textures along with his mesh script?).
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-05T11:51:45+00:00
- Post Title: Resident Evil Operation Raccoon City textures

So PC version out. Python plugin doesn't work. MrAdults can u look  ?
## Post #10
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2012-05-05T20:01:01+00:00
- Post Title: Resident Evil Operation Raccoon City textures

Uploaded a screenshot/image from the error, which comes up, if I try to export *.ssg files from the PC Version of RE:ORC with the .PY scripts:



Maybe this helps someone to create a script, which works with the PC Version of RE:ORC.
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-05T20:01:45+00:00
- Post Title: Resident Evil Operation Raccoon City textures

the game is not out till the 18th.
please wait till then
## Post #12
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2012-05-05T20:03:53+00:00
- Post Title: Resident Evil Operation Raccoon City textures

> Reply from chrrox
>
> the game is not out till the 18th.
please wait till then

Wait...what?! I bought a copy in my store yesterday, but that might explain, why it got removed from the shelves again a day later (and why there are no MP Lobbies).
## Post #13
- Username: nickru58
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Nov 17, 2011 11:10 am
- Post datetime: 2012-05-09T02:14:57+00:00
- Post Title: Resident Evil Operation Raccoon City textures

nvm i figured it out srry
## Post #14
- Username: nickru58
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Nov 17, 2011 11:10 am
- Post datetime: 2012-05-10T21:40:41+00:00
- Post Title: Resident Evil Operation Raccoon City textures

maxuint i got that same problem when trying to extract the model files and what i did was go into dlc/characters and there is a file called model info file .ssg extract that and it will extract all the models to a separate folder... not sure about the textures though
