## Post #1
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-04-21T21:40:31+00:00
- Post Title: DC Legends

Following the same procedure as this post, [https://forum.xentax.com/viewtopic.php?f=21&t=15325](https://forum.xentax.com/viewtopic.php?f=21&t=15325)
I extracted some models from the DC Legends game, however the textures are in an unknown format, or .tex. Can anyone help me solve this?

Samples: [http://www.mediafire.com/file/1m16etnj4 ... nestro.rar](http://www.mediafire.com/file/1m16etnj465imku/Sinestro.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-22T04:35:49+00:00
- Post Title: DC Legends

export them from UnityEx as source then open the dds with TheCompressonator 
and convert them through "File>Save Original" to a more common format.  



sinestro.png (98.58 KiB) Viewed 221 times
## Post #3
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-04-22T05:16:49+00:00
- Post Title: DC Legends

> Reply from AceWell
>
> export them from UnityEx as source then open the dds with TheCompressonator 
and convert them through "File>Save Original" to a more common format.  
sinestro.png

I got it !!! Sorry, now I get it. I found the program you mentioned. Thanks a lot for the help.
## Post #4
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-22T10:31:13+00:00
- Post Title: DC Legends

Greetings everyone,how i can extract _data files from separate folders (looks at screens below) and move them to a different folder?
this is how my game files folder looks like (every folder contains _data and _info file)
[http://i.imgur.com/PeoyDXb.png](http://i.imgur.com/PeoyDXb.png)

here my samples in case if someone needs them - [https://mega.nz/#!Kx4EzDyK!LIOwFY-_Bhlu ... R0ifizxxkk](https://mega.nz/#!Kx4EzDyK!LIOwFY-_BhluA0RGF3sx6klBqjP3Q8yyIR0ifizxxkk)

Thanks.
## Post #5
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2017-04-23T19:43:41+00:00
- Post Title: DC Legends

Where is the models files? I extracted,but dont found them.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-23T22:47:54+00:00
- Post Title: DC Legends

> Reply from Rutabaga
>
> how i can extract _data files from separate folders (looks at screens below) and move them to a different folder?
use your windows search tools to find all files named "__data" in the directory
select all files in the list
right click on the first one and click rename and just add a 1
windows will rename each file and add a sequence to them in parenthesis
they should all have a unique name afterwards
then you can copy them all out to the same folder for batch decompression.   

> Reply from logansan25
>
> Where is the models files? I extracted,but dont found them.
Type 43 mesh is the models and finale00's .43 Noesis python script can open those.
[viewtopic.php?p=116663#p116663](http://forum.xentax.com/viewtopic.php?p=116663#p116663)
## Post #7
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-24T11:56:26+00:00
- Post Title: DC Legends

> Reply from AceWell
>
> Rutabaga wrote:how i can extract _data files from separate folders (looks at screens below) and move them to a different folder?
use your windows search tools to find all files named "__data" in the directory
select all files in the list
right click on the first one and click rename and just add a 1
windows will rename each file and add a sequence to them in parenthesis
they should all have a unique name afterwards
then you can copy them all out to the same folder for batch decompression.

Sorry but i didn't understand how first step..is there any video tutorial about this or quick bms script?
and what is batch decompression? i mean,what i should to do for this
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-24T19:58:30+00:00
- Post Title: DC Legends

> Reply from Rutabaga
>
> Sorry but i didn't understand how first step..
  Windows, your operating system, it has built-in search tools you can use.

> Reply from Rutabaga
>
> is there any video tutorial about this or quick bms script? 
no

> Reply from Rutabaga
>
> and what is batch decompression? i mean,what i should to do for this
it simply means decompress many at once using unity tools
## Post #9
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-25T10:22:58+00:00
- Post Title: DC Legends

> Reply from AceWell
>
> 
  Windows, your operating system, it has built-in search tools you can use.
Sorry,my english skills isn't the best but i'm trying to improve them,here a Video which showing my steps
[https://streamable.com/7fpms](https://streamable.com/7fpms)
by the way,i'm using Windows 8.1  (maybe this is a problem?)

P.S I couldn't translate interface language into English,i was have some problems with my Windows,so i had to use my native interface language.

P.S.S Please,help,i have a strange problem.. Unity EX can see some meshes inside _data file but UABE can't..
i tried your method which you posted here - [viewtopic.php?p=125969#p125969](http://forum.xentax.com/viewtopic.php?p=125969#p125969)
but it doesn't work.. i tried to extract these mesh files through Unity Ex but they are isn't supported or maybe compressed.
Samples (if you can take a look)
[https://mega.nz/#!P5oCnLLJ!h-Kri4M5dKdO ... VUQavKExi4](https://mega.nz/#!P5oCnLLJ!h-Kri4M5dKdO-erShmJ0gQNG4_tGNgFQEVUQavKExi4)

Thanks in advance.
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-25T21:04:40+00:00
- Post Title: DC Legends

> Reply from Rutabaga
>
> here a Video which showing my steps
https://streamable.com/7fpms
by the way,i'm using Windows 8.1  (maybe this is a problem?)
yeah that isn't right, XP renames them unique where 8.1 doesn't at that step.   
the only thing i did different was not use that first space when i renamed the first one, like
"__data1" instead of "__data 1" like you did

afterwards all those __data files were named like this
__data1 (1)
__data1 (2)
__data1 (3)
etc


> Reply from Rutabaga
>
> Unity EX can see some meshes inside _data file but UABE can't..
that is something you have to discuss with the tool developers, nothing i can do about that   
i can tell you though that UnityEx will say some meshes are compressed when they really aren't,
sometimes you can "Export selected" and change the .mesh extension to .43 and open them with
finalle00's .43 Noesis script.

edit
i just checked the __data sample you uploaded in both UnityEx and UABE and both list 162 mesh files,
they are just listed with different names.  
but the same compressed mesh conversion method involving UABE and Unity Studio still applies here.  

edit2
if you extract all the meshes from your __data sample with UABE as "Export Raw" the files are given a generic name,
this bms script will attempt to give the extracted dat files a proper name  

```
get NAMESZ long
getdstring NAME NAMESZ
string NAME + ".mesh"
log NAME 0x0 SIZE
```
## Post #11
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-26T07:51:20+00:00
- Post Title: DC Legends

> Reply from AceWell
>
> 
yeah that isn't right, XP renames them unique where 8.1 doesn't at that step.   
the only thing i did different was not use that first space when i renamed the first one, like
"__data1" instead of "__data 1" like you did

afterwards all those __data files were named like this
__data1 (1)
__data1 (2)
__data1 (3)
etc
Ok,thanks,i will try again.

> Reply from AceWell
>
> 
that is something you have to discuss with the tool developers, nothing i can do about that   
i can tell you though that UnityEx will say some meshes are compressed when they really aren't,
sometimes you can "Export selected" and change the .mesh extension to .43 and open them with
finalle00's .43 Noesis script.

edit
i just checked the __data sample you uploaded in both UnityEx and UABE and both list 162 mesh files,
they are just listed with different names.  
but the same compressed mesh conversion method involving UABE and Unity Studio still applies here.  

edit2
if you extract all the meshes from your __data sample with UABE as "Export Raw" the files are given a generic name,
this bms script will attempt to give the extracted dat files a proper name  
Code: Select allget SIZE asize
get NAMESZ long
getdstring NAME NAMESZ
string NAME + ".mesh"
log NAME 0x0 SIZE
I renamed files extension to .43 using Total Commander (sorry,forgot to mention this,the extension was .mesh by default.) just for test if noesis script works. And it works well,but some models can and can't be opened
[http://i.imgur.com/k2PXZnj.png](http://i.imgur.com/k2PXZnj.png)
Any other models (only a few models from my samples can be loaded successfully)
[http://i.imgur.com/fU5Z51S.png](http://i.imgur.com/fU5Z51S.png)

Thanks in advance.
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-26T08:15:41+00:00
- Post Title: DC Legends

> Reply from Rutabaga
>
> Any other models (only a few models from my samples can be loaded successfully)
http://i.imgur.com/fU5Z51S.png
right, those that won't open in Noesis are likely compressed and you have to use UABE and Unity Studio.
## Post #13
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-26T12:42:51+00:00
- Post Title: DC Legends

> Reply from AceWell
>
> Rutabaga wrote:Any other models (only a few models from my samples can be loaded successfully)
http://i.imgur.com/fU5Z51S.png
right, those that won't open in Noesis are likely compressed and you have to use UABE and Unity Studio.
I tried your method but it doesn't work..
uabe doesn't see meshes

UABE
[http://i.imgur.com/4KywAL7.png](http://i.imgur.com/4KywAL7.png)
Unity EX
[http://i.imgur.com/MKsQHGS.png](http://i.imgur.com/MKsQHGS.png)

the _data files are not different,sample are here
[https://mega.nz/#!mthj3LqT!oKM4VH0kdv-p ... A72xzcmmro](https://mega.nz/#!mthj3LqT!oKM4VH0kdv-pmzllOkNBQZRwEybIu9pt0A72xzcmmro)
Thanks.
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-26T20:23:01+00:00
- Post Title: DC Legends

> Reply from Rutabaga
>
> I tried your method but it doesn't work..
yes it does, i have no reason to lie to you  

> Reply from Rutabaga
>
> uabe doesn't see meshes
UABE
http://i.imgur.com/4KywAL7.png
it most certainly does, don't you see the word "Mesh" right there beside the names?   
like i said before the only difference is how the files are named but you have to discuss that with the tool developers.
you have all information you need so good luck!
## Post #15
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-27T09:34:40+00:00
- Post Title: DC Legends

> Reply from AceWell
>
> 
you have all information you need so good luck!
You are right,i have all information,but i need more game files to rip more models from this game   (my 900mb files is isn't enough)
I tried this tutorial which made Chrrox ([viewtopic.php?f=29&t=16055](http://forum.xentax.com/viewtopic.php?f=29&t=16055)&) but i stuck on "Public IP" stage..
I tried to PM Chrrox but he is doesn't respond (i don't know why,maybe he is busy)
so i hope you can help me.. (or give me a tip,because my english is isn't a best,you know)
## Post #16
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-30T13:55:36+00:00
- Post Title: Re: DC Legends

I managed to get more character files.
Now i need to know how to batch decompress multiple _data files,i tried UABE but when i select multiple files it decompresses only single one.
And is there any good Atc texture converter? because my compressonator is doesn't save textures alpha channels
i'm using this version btw
[http://i.imgur.com/nnJZQSj.png](http://i.imgur.com/nnJZQSj.png)

Thanks in advance!
