## Post #1
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-06-13T10:11:17+00:00
- Post Title: (DREAM C CLUB) file.TGF

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-06-13T19:42:19+00:00
- Post Title: (DREAM C CLUB) file.TGF

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-06-13T20:33:13+00:00
- Post Title: (DREAM C CLUB) file.TGF

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-06-21T00:44:09+00:00
- Post Title: (DREAM C CLUB) file.TGF

Well i try ro use the Onechancara tool in TGF file Dream C Club game but it doesn't work, i need win 32bit? or that tool doesn't work with this game file???
## Post #5
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2010-06-21T06:22:46+00:00
- Post Title: (DREAM C CLUB) file.TGF

Well what did you do when you use that tool? like input and such.
## Post #6
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-06-21T21:55:43+00:00
- Post Title: (DREAM C CLUB) file.TGF

> Reply from Nexus Elite ns
>
> Well what did you do when you use that tool? like input and such.

i create a folder called "test" in my "c", then i make this...

[](http://imagefra.me/)

But nothing happens...
## Post #7
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2010-06-22T07:38:16+00:00
- Post Title: (DREAM C CLUB) file.TGF

FEATHER, you must enter the name of your TGF file (for example cha01_bd.tgf) - then converter creates a DAE file!
After that use OpenCollada plug-in to import DAE into 3DS MAX.
## Post #8
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2010-06-25T20:11:38+00:00
- Post Title: (DREAM C CLUB) file.TGF

> Reply from Doronetty
>
> FEATHER, you must enter the name of your TGF file (for example cha01_bd.tgf) - then converter creates a DAE file!
After that use OpenCollada plug-in to import DAE into 3DS MAX.
So you would enter "cha01_bd.tgf" into model file name and friendly name then?
## Post #9
- Username: Rolandonmilk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 30, 2010 5:26 am
- Post datetime: 2010-06-26T05:13:25+00:00
- Post Title: (DREAM C CLUB) file.TGF

seem to get this error when i try it on the tgf 

"Unknown vertex size" on both samples 
[](http://img156.imageshack.us/i/oooooos122.png/)
## Post #10
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2010-06-29T19:44:12+00:00
- Post Title: (DREAM C CLUB) file.TGF

Bad news...   
I think decision is to send Surveyor a common message with request to fix his version of TGF=>DAE converter! By the way his converter don't understand or working wrong with some TGF files from Oneechanbara too...
## Post #11
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-06-30T18:11:27+00:00
- Post Title: (DREAM C CLUB) file.TGF

1. open the edited tgf in hedit or similiar, tools->search TGF

2. ignore the first   tgf and delete the rest

3. save as file [mdltgf01.bin]

4. open Oneechanbara.exe

extractor file  [mdltgf01.bin]

SOS: anyone upto cracking the TGF format? I want to put models into onechanbara.






SOS: anyone upto cracking the TGF format? I want to put models into onechanbara.
[dx1.jpg](https://xentaxbackup.github.io/file/3184_dx1.jpg)
## Post #12
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-30T20:08:18+00:00
- Post Title: (DREAM C CLUB) file.TGF

I took a quick look and think i know how the TGF files are layed out.

tonight ill try to write a converter.

TGF
num models
unknown
offset to texture list
offset to some list?
num something
offset to bones list?
offset to another list having to do with boens?
array of mesh entry headers


each mesh entry header has two flags and offset to mesh


each mesh has a mesh header which holds alot of unknown but also num verts, num polys, and vertex stride(num bytes in each vertex)
then is a list of vertex,
then a list of polygons

and that is the entire file


so main unknown is the 3 offsets in the header probably to do with bones or animations
## Post #13
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2010-07-01T19:50:54+00:00
- Post Title: (DREAM C CLUB) file.TGF

Surix, I wish you GOOD LUCK with your TGF converter!!!
## Post #14
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-07-27T09:50:17+00:00
- Post Title: (DREAM C CLUB) file.TGF

Thanks guys for your comments, Any news about the converter???
## Post #15
- Username: ZAN
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jun 19, 2010 6:09 pm
- Post datetime: 2010-08-04T10:28:35+00:00
- Post Title: (DREAM C CLUB) file.TGF

airi Convert Success
In addition, four people were able to convert it.
## Post #16
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-04T18:55:23+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

> Reply from ZAN
>
> airi Convert Success
In addition, four people were able to convert it.

I need to ask... how to do that??
## Post #17
- Username: ZAN
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jun 19, 2010 6:09 pm
- Post datetime: 2010-08-06T07:44:48+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

oneechanbara model converter It is possible to do.
## Post #18
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-06T09:51:20+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

I have problem with Oneechanbara converter when i press enter the converter close i don't why .... i use win 64 maybe that's the reason???
## Post #19
- Username: ZAN
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jun 19, 2010 6:09 pm
- Post datetime: 2010-08-06T18:10:06+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

I succeeded though I tried with windows7 x64. 

   Example to airi Head model
1.c0912000.bin Unpack
2.cha10_hd.tgf is moved to the folder with Oneechanbara.exe.
3.Oneechanbara.exe Execution tgf to dae
4.tex1.can Unpack
5.tex folder making move to .dds
6.3ds max Cha10_cos10.dae is read use OpenCOLLADA plug-in

Other files are the same procedures. 

The file that cannot be converted does the program end.
## Post #20
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-06T21:01:49+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

Thanks bro but i'm still failing... maybe my file sample is bad or something... Can some body upload other file sample for testing again?
## Post #21
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-08-08T12:58:47+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

does anyone have DLC for this game?
[http://www.d3p.co.jp/dreamclub_first/do ... index.html](http://www.d3p.co.jp/dreamclub_first/download/index.html)

I've bought alot, but was hoping to trade with someone to obtain more. the DLC is quite expensive.

here's what I have so far, no download links yet. does anyone have DLC they want to share or trade?



DREAM C CLUB DLC DOWNLOADS
## Post #22
- Username: ZAN
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jun 19, 2010 6:09 pm
- Post datetime: 2010-08-10T10:44:42+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

Convertible clothes are distributed there.
It is only a body. 
Please download the game disk somewhere when you want the head and the hair.
## Post #23
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-14T19:27:22+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

> Reply from ZAN
>
> oneechanbara model converter It is possible to do.

Thanks ZAN, only work's with the files in the "model convertion success list", what about the other files???
## Post #24
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-14T20:31:47+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

Thanks pceengied i will try
## Post #25
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-15T20:30:03+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

The contents of this post was deleted because of possible forum rules violation.
## Post #26
- Username: kiddadesu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 23, 2012 7:05 pm
- Post datetime: 2012-06-23T11:08:57+00:00
- Post Title: Re: (DREAM C CLUB) file.TGF

Would it be possible for someone to convert Mio into a .dae or .obj file, Possibly with textures. ?

~Would be much appreciated C:~
