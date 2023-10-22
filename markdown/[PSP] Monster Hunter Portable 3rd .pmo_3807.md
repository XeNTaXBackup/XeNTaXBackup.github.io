## Post #1
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2009-10-25T08:23:03+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

Hey all,

Game: Monster Hunter Portable / Freedom (any; 2, 2nd G, Unite)
Platform: PSP
Model format: PMO
Texture format: TMH (already editable)

PMO files contain TMH as well, so I highly assume they are the models.

Examples: [http://vuvu.bplaced.net/MHP3rd/mhp3pmo.zip](http://vuvu.bplaced.net/MHP3rd/mhp3pmo.zip)

Please take a look at it! Custom Models would be so great!

I gathered some info from a buddy, maybe it helps:

> there are
>
>  6 vector headers
>
>  lenght 0x30
>
>  starting @ 0x10
>
>  and 6 vector type identifiers
>
>  lenght 0x10, starting ò 0x190
>
>  and i can split vectors too
>
>  the split code is 
>
>  1E 7F 7F 1E
>
>  can you see it?
>
>  1E 7F separates coordinates, 1E 7F 7F 1E separates vector points

kind regards and thank you,
Vuze
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-10-29T12:57:19+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

TMH is a texture package and pmo is 3d package!?
TMH format is simple, a set of gim images with custom header. I only spend 15mins to figure it!

```
  char[8]     ResID
  dword       numGIMImage
  dword       pad0
}
struct GIM_Image {
  dword       GIMsize
  dword_3    GIMFlags
  struct Gim_data {
    dword     DataSize
    dword     flag
    dword     ImageType
    word      Width
    word      Height
    <Data>
  }
  struct GIM_Palette {
    dword     PaletteSize
    dword     flag
    dword     PaletteType
    dword     ColorCount
    <palette color>
  }
}
```


PMO format

```
struct ResIndex {
  dword      ofsResStart
  dword      ResLength
}

```
## Post #3
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2009-10-29T14:26:33+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

K cool, thanks 
But how do I use your script/program   
Sorry for being noob v_v
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-29T14:34:45+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

Use Quickbms
[viewtopic.php?f=29&t=3525](http://forum.xentax.com/viewtopic.php?f=29&t=3525)
## Post #5
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2009-10-29T14:36:55+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

I did, but it says "Invalid command 'struct' at line 1" etc.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-29T14:41:37+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

I mean write a quickbms script from the information he sent you or make an image converter.
this is just the format information
## Post #7
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2009-10-29T14:42:26+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

Oh lol xD
Well, I would but I don't know how xD
## Post #8
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2009-11-02T13:23:56+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

Sorry for bumping, but could anyone please write an extractor / converter for TMH  Please!
## Post #9
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-02T17:22:10+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

@fatduck: did you try to convert the images? I tested it a while ago, but I got a messed up image...
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-11-04T22:43:04+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

Yes, I can convert them without any problem! Do you know you have to read in 16*8 block!?

Here is my converted images
[converted_Image.rar](https://xentaxbackup.github.io/file/2499_converted_Image.rar)
## Post #11
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2009-11-05T07:18:33+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

O_o
You rock man!
Can you give me a short instruction on how to convert them please?
And maybe how to convert them back?
ZOMG Awesome xD
## Post #12
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2009-11-08T17:15:52+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

Sry for Double Post, but I finally was able to extract the Single images from a tmh ^•^
the question now is: how to create a gim file outta them?
What exactly do I have to do with my file starting with 30020200 and ending with DEBE74FF?
(first image with Palette from the example tmh I provided)
## Post #13
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2010-08-14T21:34:46+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

Rise from the ashes, very old thread! (or sorry for bumping this thread up)

Hello there all! I'd like to extract pmo-s and tmh-s as well, but I don't know how to write a proper code for this. Can someone send me a script or something to extract these files, or write a very detailed guide? I'm über n00bish in these things.....
## Post #14
- Username: codestation
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jan 18, 2011 3:52 am
- Post datetime: 2011-01-17T23:48:05+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

BUMP   , i am looking too for a way to convert those pmo files from Monster Hunter Portable 3rd into something that can load in a 3d viewer/editor like blender or other. I managed to extract from those containers (lets call them .pak files for now) some binary files, pmo files and tmh files (who contain gim images). 

With the tmh files i dont have problems as i can extract the images to something editable (png), then convert them back to gim files and repack into the tmh container, but i want something more than texture modding so i am here looking for hints about the pmo file (and the other bin file that idk what is for).

Attachments: Jinouga .pak file
pak file [http://www.mediafire.com/?misem3psi04zlod](http://www.mediafire.com/?misem3psi04zlod)
pak file broken in parts [http://www.mediafire.com/?ggfh5bukpvga5mv](http://www.mediafire.com/?ggfh5bukpvga5mv)
## Post #15
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-10-16T08:01:15+00:00
- Post Title: [PSP] Monster Hunter Portable 3rd *.pmo

I gathered some info from a buddy, maybe it helps:

> there are
>
>  6 vector headers
>
>  lenght 0x30
>
>  starting @ 0x10
>
>  and 6 vector type identifiers
>
>  lenght 0x10, starting ò 0x190
>
>  and i can split vectors too
>
>  the split code is 
>
>  1E 7F 7F 1E
>
>  can you see it?
>
>  1E 7F separates coordinates, 1E 7F 7F 1E separates vector points

Please! Somebody take a look at it
## Post #16
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2011-10-25T00:19:59+00:00
- Post Title: Re: [PSP] Monster Hunter Portable 3rd *.pmo

What in the hoozies is this all about? Are we finally actually able to see models and animations in MHP3d? If so, can you give me the code to create an extractor. The complete process? I just want to extract the actual model and animation file (and texture) and view them.
## Post #17
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-10-26T16:07:34+00:00
- Post Title: Re: [PSP] Monster Hunter Portable 3rd *.pmo

No, nobody seems to be taking care of this topic - and I don't know why, I mean MHP3rd is quite popular...
## Post #18
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2012-01-01T13:30:50+00:00
- Post Title: Re: [PSP] Monster Hunter Portable 3rd *.pmo

Up to the top my little thread!

Please someone... can't be possible that noone is intersted in this quite popular games models xD
## Post #19
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2012-02-22T08:16:34+00:00
- Post Title: Re: [PSP] Monster Hunter Portable 3rd *.pmo

*bump*
## Post #20
- Username: Fileking
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 05, 2015 7:41 am
- Post datetime: 2016-02-11T14:34:13+00:00
- Post Title: Re: [PSP] Monster Hunter Portable 3rd *.pmo

Dose any one have the obj models rip? looking for the Zinogre  armor files
please and thank you
