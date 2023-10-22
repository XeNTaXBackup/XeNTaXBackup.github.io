## Post #1
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-11T09:41:10+00:00
- Post Title: Silent Hill 3 - PICT

I recently discovered bitmap files in an SH3 archive
that starts with "PICT" , anyone has any kind of idea on
how to read them properly? , i do convert them to TGA
but they get scrambled, but it for sure are textures,
but they differ from the other textures in the game which
are raw 32bit data. i havent found any information on the net,
and sorry that i cant post an attachment as im not having internet
anymore at my home =( , if someone just happens to have the
game and are into fileconverting i would be thrilled to have
this format explained. thanks =)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-11T12:46:26+00:00
- Post Title: Silent Hill 3 - PICT

You haven't got internet, yet you post? 

Did you try my PICT2BMP tool? You never know, they might be the same format. 

[http://wiki.xentax.com/index.php/Game_Tools#PICT2BMP](http://wiki.xentax.com/index.php/Game_Tools#PICT2BMP)

If not, we do need to have an example from somewhere.
## Post #3
- Username: MadHatterReturns
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-11T14:51:45+00:00
- Post Title: Silent Hill 3 - PICT

Hmm, I think that tool might not work. 

Okay, here's a script for the Silent Hill 3 .ARC archives. Should allow replacement as well. Scroll down for the BMS, then follow KorNet's instructions to add the script to MultiEx Commander (similar to [viewtopic.php?p=13289#13289](http://forum.xentax.com/viewtopic.php?p=13289#13289) ). 


```
Get U1 Long 0 ;
Get FileNum Long 0 ;
Get Dir2Size Long 0 ;
Get U2 Long 0 ;
For T = 1 To FileNum ;
SavePos FOO 0 ;
Get FO Long 0 ;
Get OffDir2 Long 0 ;
SavePos FSO 0 ;
Get ComSize Long 0 ;
Get UnComSize Long 0 ;
Log "" FO ComSize FOO FSO ;
Next T ;

```


Also, I attached a sample of a texture that you refer to. There are some BMP files in the pic.arc file (start with 'BM6'), but also some undefined. 

I can't take a look at them with the right tools at work, will check later. Perhaps someone else already will know the answer.
[arc.zip](https://xentaxbackup.github.io/file/580_arc.zip)

[textures_unknown.zip](https://xentaxbackup.github.io/file/579_textures_unknown.zip)
## Post #4
- Username: MadHatterReturns
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-11T15:01:22+00:00
- Post Title: Silent Hill 3 - PICT

Ah, and it was easy to create a script for the AFS files of the game too. Also supports replacement of the sounds, but use with care, as the game might not enjoy the removal of padding by MultiEx Commander injections. 

```
ImpType Standard ;
Get D Byte 0 ;
Get FileNum Long 0 ;
For T = 1 To FileNum ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log "" FO FS FOO FSO ;
Next T ;

```

[afs.zip](https://xentaxbackup.github.io/file/581_afs.zip)
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-13T09:35:55+00:00
- Post Title: Silent Hill 3 - PICT

Just some funny information:
Mr.Mouse, yes there are 3 bitmaps there (pic.arc),
these are the Konami Logo, etc etc, the same pictures as
found in the "pic" dir in the mainfolder. why they have duplicates in
the archivefile i dont know ;D

but then they have loads of duplicates of other textures aswell.

if they had compressed the textures with atleast RLE encoding
and deleted all the extra textures they could have squeezed the game down
with atleast 1GB =X   (or more)
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-13T11:48:35+00:00
- Post Title: Silent Hill 3 - PICT

Just some more useless information that i thought was funny.

There are tons of strange textures and miss-spellings in the game,
but as you never get this close to the textures in the game you never see them.

example, on one texture of a map it says "infomation" , not information.

on all the textures for Gun Ammo, gun is spelled Gan.
like Shotgan, Handgan..

the most funny stuff can be found on posters and magazines as these are complete jidderish. like on one note it says "mating room lolr 1.given somebody"

and on one poster "get drunk in japan!"

its hilarious...=D
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-13T19:09:50+00:00
- Post Title: Silent Hill 3 - PICT


