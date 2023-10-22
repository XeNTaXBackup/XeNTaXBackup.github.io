## Post #1
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-09-18T17:50:50+00:00
- Post Title: [PS2] Gantz NKP models and texture files

hi there , just found out this mangas and the ps2 game derived from it, here is the nkp model files for kishiro if someone want to help on this one

the nkp files are packages containing several files, in it you can found:
- nkt witch is texture block that is also like tim2 files (paletized 256 color textures at what i have seen)
- nkm witch seems to be the mesh blocks
- some text files containing pointers ???
- nka for animations 

i have not started to work really on this one yet as i am busy with lot of other projects so if someone want to start working on it , sample files are here:

[http://www.mediafire.com/?ui9neo62n0u6adh](http://www.mediafire.com/?ui9neo62n0u6adh)
## Post #2
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-09-21T20:42:00+00:00
- Post Title: [PS2] Gantz NKP models and texture files

Here are the files unpacked
I am sorry I cannot be of much help.
## Post #3
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-09-29T15:56:28+00:00
- Post Title: [PS2] Gantz NKP models and texture files

ok so i finally managed to convert texture to tga, each nkt texture have this structure:

```
%magic         '//always &h1A54B4E ==441731918 ==( NKT &H1A 
$unkna * 36  '// 9 unknown integers
%paloffset     '//palette offset
%palsize       '//size of palette data in bytes (must be divided by 4 to get BGRA count)
$unkb * 224  '// another block of integers unknown
%width         '//texture width
%height        '//texture height 
$unkc * 168  '// another block of integers unknown
end type 

```

then you read the palette array
then you read the image indice data witch is always datasize= width * height
once done rebuild the image using the palette entries and do some stuffs to fix the palette order if needed
quite simple in fact.

now i will try my hands on the mesh format that looks real pain in ass
## Post #4
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-10-06T09:56:47+00:00
- Post Title: [PS2] Gantz NKP models and texture files

what do you used to unpack the nkp files ?
## Post #5
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-10-06T10:12:22+00:00
- Post Title: [PS2] Gantz NKP models and texture files

> Reply from shadowmoy
>
> what do you used to unpack the nkp files ?
Kaddy[http://www.alhexx.com/releases/kaddy.html](http://www.alhexx.com/releases/kaddy.html)
## Post #6
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-10-06T11:27:25+00:00
- Post Title: [PS2] Gantz NKP models and texture files

here are the tools i just wrote for this app:
- nkp extractor
- nkt2tga converter 
(seems some pics are swizled or something ( will look at it later)
[http://www.mediafire.com/?mi12chyuvmoa4ug](http://www.mediafire.com/?mi12chyuvmoa4ug)
