## Post #1
- Username: DarkStrife7
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 02, 2014 11:03 am
- Post datetime: 2014-05-19T08:51:27+00:00
- Post Title: Saint Seiya Ultimate Cosmo [PSP]

Hello All, I've been trying to extract these low Poly models from this psp game, It all turns out fine on the unpacking part, with quickbms Cpk script. Once I see the folders everything looks understanding, until I get to the actual scenery or character files. They're in the .pac format, that I have not been able to open or view with any tool on this forum. I tried Noesis's pac file viewer but it seems it's not compatible. I tried hex2obj But I couldn't figure out the locations and what not, Maybe someone can)  I tried many methods, and still no success. Can anyone help me?  on these links is the file to two characters. 

[http://www.mediafire.com/download/fscff ... kog_01.pac](http://www.mediafire.com/download/fscffpd6ig4ye5l/kog_01.pac)
[http://www.mediafire.com/download/o52zt ... sey_01.pac](http://www.mediafire.com/download/o52zto361ldpdgo/sey_01.pac)

[Edit] Here's the cpk file you can extract with QuickBms to view all the files. 
[http://www.mediafire.com/download/5ec22 ... rchive.cpk](http://www.mediafire.com/download/5ec223gbhvcadun/archive.cpk)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-21T10:31:20+00:00
- Post Title: Saint Seiya Ultimate Cosmo [PSP]

These are mostly all texture files packed i think :S


Have a look at the file:


You can see a bunch of texture names with the .GIM extension, a quick google revels they are PSP GIM textures which are converted using a tool called GimConv.exe

I won't provide the tool but you if you're able to do a simple google search you can get your hand on it.

Whats even more scroll down a bit further 



There you have it GimConv was used 

Lets take a look at the first entry


Cut and paste the chunk into a new file rename it to .gim and use the gimconv tool

```
GimConv EER.gim -o "EER.tga"
```


Bam 
KOG_00_FACE.GIM


KOG_01_EYE.GIM


KOG_01_LIP.GIM


They are just packaged GIMS, i don't have time currently to write a script to unpack them but i've given you enough info if you decide to write one.


-EDIT- the size of each image chunk is followed after the asciiz name so you have

```
uint32 unknownblank[4];
uint32 offset // Header + this (headers 128bytes)
uint32 sizeofentry;

```
## Post #3
- Username: DarkStrife7
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 02, 2014 11:03 am
- Post datetime: 2014-05-22T04:20:49+00:00
- Post Title: Saint Seiya Ultimate Cosmo [PSP]

Wow, Cra0 Thank you so much, I appreciate the information you provided, Those are amazing textures. It's nice to see something out of this game, If I hadn't realized I gave the texture files by accident, I would have been satisfied with just that! I made a mistake and realized I provided the texture Files, so you are an expert! I'm sorry for providing the textures only.   These are the actual File models:  

[http://www.mediafire.com/download/88tqg ... kog(2).pac](http://www.mediafire.com/download/88tqgy9yydpc0hk/kog%282%29.pac)     --> Model

[http://www.mediafire.com/download/pehc6 ... 9z/sey.pac](http://www.mediafire.com/download/pehc6b7kflhe39z/sey.pac)   ---> Model

I open, I examined the file in Hexedit, and It says GMO on some parts. 

Once again, thank you for that amazing tutorial on the textures. Any instruction on how to extract the models with these new ones I provided, I'll take from there to extract the rest. Thank you Cra0.
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-23T15:46:21+00:00
- Post Title: Saint Seiya Ultimate Cosmo [PSP]

Yes .GMO are the animations


The file structure like I explained has the name of the node for example IDLE_WALK.GMOD followed by the offset and size and sometimes other arbitrary data. Since you're after the meshes they start around 0xD2A60



The mesh pieces are named followed by the triangelist indicies.

Then the vertex arrays which the indicies reference


Knowing this you should be able to use hex2obj to produce something.
