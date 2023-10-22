## Post #1
- Username: SiegKaiser
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 26, 2019 6:58 am
- Post datetime: 2022-09-16T21:58:36+00:00
- Post Title: Help with .kslt textures

Hello.
I was translating the Marvel ultimate alliance 3, and the part graphic is being a problem.
The textures are in .kslt(TLSK3100) format.

I tried extracting with a FF Dissidia's bms tool, it even extracts the files, but none of them have header.

I tried to see them with TextureFinder, and the DXT5 format is what gave the image more accurately, but I can only export them.

I tried to use TileMolester to edit raw, but the texture looks better in 32bpp mode(2 dimensions), and for some reason, you can't change the palette in that mode.

Anyway, if anyone knows a way to edit or import them, I'd be grateful.

TextureFinder:


TileMolester:


File: [https://drive.google.com/file/d/19-mOny ... sp=sharing](https://drive.google.com/file/d/19-mOnyIAfgDXuLFrKKzgiIkglmNjvKTm/view?usp=sharing)
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-09-19T03:43:09+00:00
- Post Title: Help with .kslt textures

Use mummggtool

Its allow you to extract and reimport dxt5
## Post #3
- Username: SiegKaiser
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 26, 2019 6:58 am
- Post datetime: 2022-09-19T09:45:03+00:00
- Post Title: Help with .kslt textures

Thanks for answer. it work to export but not to import. i'm getting this error:
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-09-19T12:33:33+00:00
- Post Title: Help with .kslt textures

Hi,

Try this version.
Put all files in the same folder.

[https://drive.google.com/file/d/13mRS1f ... sp=sharing](https://drive.google.com/file/d/13mRS1fserWPys-gBZl2YZtgM3WWKpz0y/view?usp=sharing)
## Post #5
- Username: SiegKaiser
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 26, 2019 6:58 am
- Post datetime: 2022-09-19T17:22:55+00:00
- Post Title: Help with .kslt textures

> Reply from Rabatini ↑Mon Sep 19, 2022 8:33 pm at Mon Sep 19, 2022 8:33 pm
>
> 
Hi,

Try this version.
Put all files in the same folder.

https://drive.google.com/file/d/13mRS1f ... sp=sharing

Hello!
So, it work to export and import the texture, but it make the game crash. 
While the edited offset seems good, the other ones seems broken.
(Original / Edit)


I've open these 2 texure in a hex editor too, and the first 64 bits(maybe is the pallete) in the original, dissapears almost completely in the edit, and the begin of the graphic part(probaly the transparence color) don't look the same.
(Original)


(Edit)
## Post #6
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-09-19T19:27:27+00:00
- Post Title: Help with .kslt textures

Did you tried to export as bmp?
and import as well?
try to export and them import, without any modification.
is the first thing you have to do is eliminate the errors.
## Post #7
- Username: SiegKaiser
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 26, 2019 6:58 am
- Post datetime: 2022-09-19T20:39:51+00:00
- Post Title: Help with .kslt textures

> Reply from Rabatini ↑Tue Sep 20, 2022 3:27 am at Tue Sep 20, 2022 3:27 am
>
> 
Did you tried to export as bmp?
and import as well?
try to export and them import, without any modification.
is the first thing you have to do is eliminate the errors.

Exporting as bmp and importing without any modifications make it happens the same(break), but the texture became all white
## Post #8
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-09-19T22:09:47+00:00
- Post Title: Help with .kslt textures

for both?
png and bmp, without alteration?
## Post #9
- Username: SiegKaiser
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 26, 2019 6:58 am
- Post datetime: 2022-09-19T22:16:14+00:00
- Post Title: Help with .kslt textures

> Reply from Rabatini ↑Tue Sep 20, 2022 6:09 am at Tue Sep 20, 2022 6:09 am
>
> 
for both?
png and bmp, without alteration?

Yes!
## Post #10
- Username: SiegKaiser
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 26, 2019 6:58 am
- Post datetime: 2022-09-19T23:12:02+00:00
- Post Title: Help with .kslt textures

An little update:
i'm trying to get something changing the settings, and after check use alpha, i can see the texture exately how is ingame. but after import without changes, it still breaking. But now, the first 8 bits in hex is appearing correctly.
