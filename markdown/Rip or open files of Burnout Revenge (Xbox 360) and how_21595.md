## Post #1
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-11T12:01:32+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

Hi all,

I'm here this time with a big question: Rip or open Burnout Revenge (Xbox 360) files?

Because I had tried in all methods to rip 3d models of the game with ninjaripper on Xenia emulator... nothing works, and i have a idea of why it doesn't: it perhaps that latest Xenia build uses only DX12? If is ir, I don't wonder why NR dosen't works. Is perhaps another Xbox 360 emulator that NR actually works?

SO

I'm thinking to open the games vehicle files: .BGV, tha'ts the same used on Burnout 3 and Dominator (i I remember)... but I don't found a good tutorial here... So someone can explain me how to open theese 3d files, if possible on details?

p.s. I saw someone on Sketchfab does it, but idk if he opens the files or ripped from the game. If is the second one, how he does it? 
p.p.s. here the file: [https://www.dropbox.com/s/d77mk5hdlj8i0 ... A.zip?dl=0](https://www.dropbox.com/s/d77mk5hdlj8i02j/Car1A.zip?dl=0)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-11T15:59:12+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

use offzip (see forum threads how to use it), then hex2obj (view link in my sig)
.



car1A_bgv.png (188.34 KiB) Viewed 208 times
## Post #3
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-12T16:17:05+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from shakotay2 ↑Sat Jan 11, 2020 11:59 pm at Sat Jan 11, 2020 11:59 pm
>
> 
use offzip (see forum threads how to use it), then hex2obj (view link in my sig)
.
car1A_bgv.png

Ok, but what is Offzip? And what is it for?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-12T18:04:33+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

It's for decomressing files wtih zipped data blocks contained.
[https://www.aluigi.altervista.org/search.php?src=offzip](https://www.aluigi.altervista.org/search.php?src=offzip)
## Post #5
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-12T18:15:31+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

[https://www.dropbox.com/s/a0ejo95ocazpv ... g.jpg?dl=0](https://www.dropbox.com/s/a0ejo95ocazpvet/Anything.jpg?dl=0)

But there isn't any zipped data blocks into the .BGV file...
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-13T07:09:40+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

There is. Use offzip -a -z -15 Car1A.bgv [folder2extract2]
.

```
- enter in directory: D:\bgv
- zip data to check:  32 bytes
- zip windowBits:     -15
- seek offset:        0x00000000  (0)

+------------+-----+----------------------------+----------------------+
| hex_offset | ... | zip -> unzip size / offset | spaces before | info |
+------------+-----+----------------------------+----------------------+
  0x00000002 ...................................................................
................................................................................
................................................................................

................................................................................
................................................................................
.... 3094442 -> 6232032 / 0x002f37ac _ 2


- 1 valid compressed streams found
- 0x002f37aa -> 0x005f17e0 bytes covering the 99% of the file
```
## Post #7
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-13T10:19:21+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

Ok, I get it.

And Offzip gave me this screen
[https://www.dropbox.com/s/wmcysiiytz6xg ... d.jpg?dl=0](https://www.dropbox.com/s/wmcysiiytz6xgc7/Compressed%20streams%20found.jpg?dl=0)
and it found these files:
[https://www.dropbox.com/s/h3zoslp66yfps ... s.jpg?dl=0](https://www.dropbox.com/s/h3zoslp66yfps85/DATfiles.jpg?dl=0)
Question: what should I do with these .dat, vbq, .666, ect. files? Are they the submeshes' hex codes?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-13T10:41:25+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from Fiammanera628 ↑Mon Jan 13, 2020 6:19 pm at Mon Jan 13, 2020 6:19 pm
>
> Question: what should I do with these .dat, vbq, .666, ect. files? Are they the submeshes' hex codes?I dunno.
Start loading 00000002.dat (unzipped from the Car1A.bgv) into hex2obj. Get the mesh (File/SaveAs mesh).
Then check other .dat files. That's how I'd do it.
## Post #9
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-13T11:47:44+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

I haven't got a 00000002.dat 
the files stars with 0000cad0.dat 

And... how I understand where are the mesh? (yes, I'm not very into hex...  )

because

I tried to open the 0000cad0.dat file with Hex Editor Neo and give me this:

[https://www.dropbox.com/s/wahmcon5vlz4s4s/1.jpg?dl=0](https://www.dropbox.com/s/wahmcon5vlz4s4s/1.jpg?dl=0)

p.s. i attached the file here
[https://www.dropbox.com/s/bc1tyw8bttzwi ... 0.dat?dl=0](https://www.dropbox.com/s/bc1tyw8bttzwizn/0000cad0.dat?dl=0)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-13T11:57:11+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from Fiammanera628 ↑Mon Jan 13, 2020 7:47 pm at Mon Jan 13, 2020 7:47 pm
>
> 
I haven't got a 00000002.dat 
the files stars with 0000cad0.dat 

And... how I understand where are the mesh? (yes, I'm not very into hex...  )

because

I tried to open the 0000cad0.dat file with Hex Editor Neo and give me this:read the tutorial (tut button in hex2obj). Try to understand how to find the mesh in 00000002.dat (If you did we can talk again.)
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-13T12:14:07+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from Fiammanera628 ↑Mon Jan 13, 2020 6:19 pm at Mon Jan 13, 2020 6:19 pm
>
> 
Question: what should I do with these .dat, vbq, .666, ect. files? Are they the submeshes' hex codes?
You should never use Offzip for final extraction proccess. The whole file is zlib-compressed so simply decompress all data into a single file. 
Then you'll see those offsets in the header pointing to different blocks of the data:



PTRs.png (115.94 KiB) Viewed 163 times



And each block has more relative offsets to other data.
## Post #12
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-13T12:50:18+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from shakotay2 ↑Mon Jan 13, 2020 7:57 pm at Mon Jan 13, 2020 7:57 pm
>
> 
Fiammanera628 wrote: ↑Mon Jan 13, 2020 7:47 pm
I haven't got a 00000002.dat 
the files stars with 0000cad0.dat 

And... how I understand where are the mesh? (yes, I'm not very into hex...  )

because

I tried to open the 0000cad0.dat file with Hex Editor Neo and give me this:read the tutorial (tut button in hex2obj). Try to understand how to find the mesh in 00000002.dat (If you did we can talk again.)

I'm sorry, but I noticed now that I worked until now with the Xbox file instead of 360's one (despite I give to you the right file) ... I am stupid, sorry again
## Post #13
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-13T12:53:51+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from Bigchillghost ↑Mon Jan 13, 2020 8:14 pm at Mon Jan 13, 2020 8:14 pm
>
> 
Fiammanera628 wrote: ↑Mon Jan 13, 2020 6:19 pm
Question: what should I do with these .dat, vbq, .666, ect. files? Are they the submeshes' hex codes? 

You should never use Offzip for final extraction proccess. The whole file is zlib-compressed so simply decompress all data into a single file. 
Then you'll see those offsets in the header pointing to different blocks of the data:
PTRs.png

And each block has more relative offsets to other data.

I want to say sorry also to you, for the same reason that I explain to shakotay2... I think I understand what you say, but exactly you mean that the first "string"(00002210), when I found the 00000030 on 00002210 address, is the start of meshes on the .bgv file? Or on the .dat file?
correct me if I'm wrong (I hope I understand something  )
## Post #14
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-14T10:31:39+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

Ok, I think I'm wrong... and my question is: when I find the end of the realtives offsets? When I find the "string" FF FF FF FF? Because the only thing I understand is that I can find the 00002210 as address and I find the 00000030...
I tried to address also the 00000030 and it reminds me to 3f7073eb... and then? I mean, I can't put 3f7073eb as address... what should I do?

I tried also to enter the 00002210 address into the Car1A.bgv (right this time  ) and it give me this "string": FD9CF401... and is in the middle of the scrambled alphabet...
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-15T05:10:44+00:00
- Post Title: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from Fiammanera628 ↑Tue Jan 14, 2020 6:31 pm at Tue Jan 14, 2020 6:31 pm
>
> 
and my question is: when I find the end of the realtives offsets? When I find the "string" FF FF FF FF?
You were talking about "how" instead of "when" I suppose? And what's this "FF FF FF FF" "string"?

> Reply from Fiammanera628 ↑Tue Jan 14, 2020 6:31 pm at Tue Jan 14, 2020 6:31 pm
>
> 
Because the only thing I understand is that I can find the 00002210 as address and I find the 00000030...
I tried to address also the 00000030 and it reminds me to 3f7073eb... and then? I mean, I can't put 3f7073eb as address... what should I do?
You jump to 0x2210 + 0x30 = 0x2240 of course, that's why it's called a relative offset.

> Reply from Fiammanera628 ↑Tue Jan 14, 2020 6:31 pm at Tue Jan 14, 2020 6:31 pm
>
> 
I tried also to enter the 00002210 address into the Car1A.bgv (right this time  ) and it give me this "string": FD9CF401... and is in the middle of the scrambled alphabet...
I simply decompressed the whole Car1A.bgv and saved as the file "Car1A.bgvd" where the "d" indicates "decompressed". It's a total different file and has nothing to do with the original data in Car1A.bgv.
## Post #16
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-15T08:38:22+00:00
- Post Title: Re: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from Bigchillghost ↑Wed Jan 15, 2020 1:10 pm at Wed Jan 15, 2020 1:10 pm
>
> 
Fiammanera628 wrote: ↑Tue Jan 14, 2020 6:31 pm
and my question is: when I find the end of the realtives offsets? When I find the "string" FF FF FF FF? 
You were talking about "how" instead of "when" I suppose? And what's this "FF FF FF FF" "string"?
Ehm... I think you're right, how I find the end of the realtive offsets?
FFFFFFFF "string" was something I did wrong, of course
## Post #17
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-15T08:46:28+00:00
- Post Title: Re: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from Fiammanera628 ↑Tue Jan 14, 2020 6:31 pm at Tue Jan 14, 2020 6:31 pm
>
> 
I tried also to enter the 00002210 address into the Car1A.bgv (right this time  ) and it give me this "string": FD9CF401... and is in the middle of the scrambled alphabet...

> I simply decompressed the whole Car1A.bgv and saved as the file "Car1A.bgvd" where the "d" indicates "decompressed". It's a total different file and has nothing to do with the original data in Car1A.bgv.
You renamed the file "00000002.dat" into "Car1A.bgvd"
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-15T09:06:15+00:00
- Post Title: Re: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from Fiammanera628 ↑Wed Jan 15, 2020 4:38 pm at Wed Jan 15, 2020 4:38 pm
>
> 
Ehm... I think you're right, how I find the end of the realtive offsets?
Still, your question doesn't make any sense to me. What I did in the first place was merely to imply that the decompressed data uses absolute addresses in the header so you can't use offzip which'll generate pieces of irrelevant files.

> Reply from Fiammanera628 ↑Wed Jan 15, 2020 4:46 pm at Wed Jan 15, 2020 4:46 pm
>
> 
You renamed the file "00000002.dat" into "Car1A.bgvd"
I didn't use offzip at all, nor did I download your fragmental sample files generated with it. So forget about any of these "000000**.dat" or whatever.
## Post #19
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-15T09:42:39+00:00
- Post Title: Re: Rip or open files of Burnout Revenge (Xbox 360) and how?

> Reply from Bigchillghost ↑Wed Jan 15, 2020 5:06 pm at Wed Jan 15, 2020 5:06 pm
>
> 
Fiammanera628 wrote: ↑Wed Jan 15, 2020 4:38 pm
Ehm... I think you're right, how I find the end of the realtive offsets?

Still, your question doesn't make any sense to me. What I did in the first place was merely to imply that the decompressed data uses absolute addresses in the header so you can't use offzip which'll generate pieces of irrelevant files.
Fiammanera628 wrote: ↑Wed Jan 15, 2020 4:46 pm
You renamed the file "00000002.dat" into "Car1A.bgvd" 

I didn't use offzip at all, nor did I download your fragmental sample files generated with it. So forget about any of these "000000**.dat" or whatever.

Ok, so you work direcly with .bgv file renamed into .bgvd...
