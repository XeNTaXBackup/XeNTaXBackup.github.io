## Post #1
- Username: miinecraft5
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 12, 2023 2:11 am
- Post datetime: 2023-06-12T12:16:45+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

I would like to change the color of dark fay's model from the overlord 2 game to the ones she has when she is queen fay but I can't find them in the model's hexadecimal file

the file has the extension prp but it can be opened perfectly with any hexadecimal program

I leave a link to the file here

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1hWa-8XepRg0M6AXrylH3alifkYUx7U8I?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-12T15:38:44+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

You might try/use a TextureFinder on the file. A quick check with 512x2048, 8 bit grayscale gives this:
.



prp.jpg (88.73 KiB) Viewed 206 times

(You'll need to trick around with the dimensions and format.)
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-06-12T16:49:04+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

> Reply from miinecraft5 ↑Mon Jun 12, 2023 8:16 pm at Mon Jun 12, 2023 8:16 pm
>
> 
 the extension prp

if you only want textures you can search for them as ".dds"
I made a plugin for Noesis which looks for textures in *.prp and also prints to DebugLog pixel offsets, width and height and format.
*you also need to check for mipmap
[tex_prp.py](https://github.com/Durik256/Noesis-Plugins/blob/master/tex_prp.py)
[Character Fay.prp.png](https://xentaxbackup.github.io/file/23914_Character Fay.prp.png)
## Post #4
- Username: miinecraft5
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 12, 2023 2:11 am
- Post datetime: 2023-06-13T10:52:18+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

but how can I once edited reintroduce them to the prp file and replace the others in the file?
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-06-13T10:59:20+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

> Reply from miinecraft5 ↑Tue Jun 13, 2023 6:52 pm at Tue Jun 13, 2023 6:52 pm
>
> 
but how can I once edited reintroduce them to the prp file and replace the others in the file?

they must be the same resolution and format, just replace (raw pixel buffer) in prp with yours (copy&paste after selecting it). in any HexEditor
## Post #6
- Username: miinecraft5
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 12, 2023 2:11 am
- Post datetime: 2023-06-13T11:44:43+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

I'm sorry but I'm a bit of a novice in this if you could explain me step by step I would appreciate it a lot
## Post #7
- Username: miinecraft5
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 12, 2023 2:11 am
- Post datetime: 2023-06-16T11:59:12+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

i think i almost have it i just would like to know how i can know how to get the RAW pixel buffer
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-16T17:25:41+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

> Reply from miinecraft5 ↑Fri Jun 16, 2023 7:59 pm at Fri Jun 16, 2023 7:59 pm
>
> how to get the RAW pixel bufferWhat do you mean exactly?
Did you notice the offsets?

1024 1024 7
offset: 17316 width: 1024 height: 1024 format: DXT1
1024 1024 11
offset: 716882 width: 1024 height: 1024 format: DXT5

So first DXT1's data starts at 0x43A0, size 0x80000
Just to give you an idea: if you copy&paste (in overwrite mode) 0x40000 bytes from 0xAF052 to 0x43A4 it looks like so:
.
Looks weird? Yes, because DXT5 data is interpreted as DXT1.  (well, I decided to delete it to not confuse people)

In a 2nd step copy a block from 0x2047BC. 
.



copyingData.jpg (170.07 KiB) Viewed 103 times


Once you got that you should be able to copy any DXT1 with same dimensions to 0x43A4 (after having modified colors).
## Post #9
- Username: miinecraft5
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 12, 2023 2:11 am
- Post datetime: 2023-06-17T12:24:27+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

thanks i got it
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-06-19T02:59:58+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

> Reply from miinecraft5 ↑Sat Jun 17, 2023 8:24 pm at Sat Jun 17, 2023 8:24 pm
>
> 
thanks i got it
i made form
this will automatically resize and convert the image to the selected format
and overwrite inside prp (without mipmaps, if necessary, you can also overwrite mipmaps manually)
*actually you can do it with your favorite files not only prp



form.png (112.23 KiB) Viewed 63 times


[WindowsFormsApp2.zip](https://drive.google.com/file/d/11-v9glJL1NOHIAeLreRJcy2Srw8F-MjW/view?usp=sharing)
"openPRP" and select your prp
"<",">" - selected need img
"Save As" - save and Edit
"Open IMG"  - open edited img
"<",">" - selected need img, or edit manualy(offset,width,hgth,frm)
"<replace" - replace img in prp
close form

*other:
checbox "save raw" - enable save raw (dxt1,dxt2,rgba32) from pictureBox(right)
## Post #11
- Username: miinecraft5
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 12, 2023 2:11 am
- Post datetime: 2023-06-23T08:52:32+00:00
- Post Title: change the color of a 3d model in a hexadecimal file

even though i made the change the model inside the game hasn't been changed, still thanks for the help
