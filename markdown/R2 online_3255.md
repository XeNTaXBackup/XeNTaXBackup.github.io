## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-18T22:01:31+00:00
- Post Title: R2 online

Well, here is another thread with a game that i play, this time it's R2 ONLINE and this is a russian version. I have found that all archives are in .rfs

I will post the smallest one, if we can "unlock" this, can we also unlock the others? Is it normally so?

I attach the file to this post. It's 111kb small

Here are, as always, some screenies to get your attention 






[fx.rar](https://xentaxbackup.github.io/file/1786_fx.rar)
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-20T19:39:13+00:00
- Post Title: R2 online

hm, first line in one of the files model.rfs is like this:

00000000 50 4B 03 04 14 00 0D 00 08 00 67 55 37 34 60 4B F7 64 5D 0E 00 00 20 2E 00 00 0D 00 00 00 63 30 30 30 30 PK........gU74`K.d]... .......c0000

Doesnt that mean its a pkzip library?

Hm, found a program just called pkzip and i could open it there:



One problem i have is i cant extract anything, just asks for passworkd and then says that "no file found"
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2008-12-21T16:03:05+00:00
- Post Title: R2 online

dang that means it is just like granado espada and the archives are encrypted.
once someone finds the key it will be easy to extract the files.
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-21T18:23:40+00:00
- Post Title: R2 online

ywah but wonder what kind of 3d models format is hiding
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-17T05:02:48+00:00
- Post Title: R2 online

is it really hard to decrypt this? I guess it would take quite some time if they have say 5-6 characters in password
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-17T07:57:41+00:00
- Post Title: R2 online

It seems to me the .exe should hold the key.
## Post #7
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-17T12:24:14+00:00
- Post Title: R2 online

So maybe if i post a .exe file someone might be lucky then? 

[http://www.2shared.com/file/4665754/ce3 ... files.html](http://www.2shared.com/file/4665754/ce35db62/R2files.html)

the small file is the launcher and then bigger is the main exe
## Post #8
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-17T22:26:42+00:00
- Post Title: R2 online

I took a peek inside the main exe and found this line, dont know if it is interesting:

```
0068CF91 70 4C 00 70 7E 4C 00 73 76 72 6E 6F 3D 25 30 35 64 26 69 64 3D 25 73 26 76 61 6C pL.p~L.svrno=%05d&id=%s&val
0068CFAC 75 65 3D 25 64 00 00 00 70 87 4C 00 50 8C 4C 00 7A 69 70 00 7A 25 2E 33 64 00 00 ue=%d...p.L.P.L.zip.z%.3d..
0068CFC7 00 7A 25 2E 32 64 00 00 00 70 6B 62 61 63 6B 23 20 25 2E 33 64 00 5C 00 00 5C 5C .z%.2d...pkback# %.3d.\..\\
0068CFE2 3F 5C 75 6E 63 5C 00 00 00 00 5A 69 70 41 72 63 68 69 76 65 20 4D 61 70 70 69 6E ?\unc\....ZipArchive Mappin
0068CFFD 67 20 46 69 6C 65 00 40 C4 4C 00 00 00 00 00 96 30 07 77 2C 61 0E EE BA 51 09 99 g File.@.L......0.w,a...Q..
0068D018 19 C4 6D 07 8F F4 6A 70 35 A5 63 E9 A3 95 64 9E 32 88 DB 0E A4 B8 DC 79 1E E9 D5 ..m...jp5.c...d.2......y...
0068D033 E0 88 D9 D2 97 2B 4C B6 09 BD 7C B1 7E 07 2D B8 E7 91 1D BF 90 64 10 B7 1D F2 20 .....+L...|.~.-......d.... 
0068D04E B0 6A 48 71 B9 F3 DE 41 BE 84 7D D4 DA 1A EB E4 DD 6D 51 B5 D4 F4 C7 85 D3 83 56 .jHq...A..}......mQ.......V
```


But you have pkback and ziparchive mapping
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-21T07:21:24+00:00
- Post Title: R2 online

I've found out that they used ZipArchive code from Artpol. 

[http://www.artpol-software.com/ZipArchive/](http://www.artpol-software.com/ZipArchive/)

Judging from their assembly code, they have used this open source project. ZipArchive's source code shows there is also a SetPassword function. There is an executable ZipArc.exe from Artpol that has this function implemented. It needs to be set after opening of a zip file, but before extraction of anything. The thing to do now is find that particular function in assembly code, using stuff like W32Dasm or preferably OllyDgb. I hope I can come with some more answers soon.
## Post #10
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-21T12:29:49+00:00
- Post Title: R2 online

sounds promising. I started to scan the archive with a password recovery with 7 letters and came up with 350billion combinations and then i gave up
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-24T00:55:44+00:00
- Post Title: R2 online

I have extracted the archives from this game 
Here is the tool to do it.
[http://www.sufi.cc/aionemu/RPGViewer_3. ... d1024_.zip](http://www.sufi.cc/aionemu/RPGViewer_3.0__Build1024_.zip)
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-24T07:56:49+00:00
- Post Title: R2 online

If you know the password to the zip, then please share it. That's what this forum is about. Also, the RPGViewer does not work, do I have to have more files for it to work?
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-24T10:57:58+00:00
- Post Title: R2 online

I do not have the password for the archive unfortunately.
But I have extracted all the archives from this game with rpg viewer.
I go to file -> open -> online games -> R2 reign of revolution.
then I click on one of the archives it shows and choose 
addon -> archive -> extract
and it asks where I want to dump the files and it then dumps them.
[](http://xs.to/xs.php?h=xs435&d=09046&f=r21507.jpg)[](http://xs.to/xs.php?h=xs435&d=09046&f=r22331.jpg)[](http://xs.to/xs.php?h=xs435&d=09046&f=r23117.jpg)[](http://xs.to/xs.php?h=xs435&d=09046&f=r24238.jpg)[](http://xs.to/xs.php?h=xs435&d=09046&f=r5873.jpg)
[m00130_3.rar](https://xentaxbackup.github.io/file/1841_m00130_3.rar)
## Post #14
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-24T11:40:06+00:00
- Post Title: R2 online

uh lala. i also see aion there. But what is the model format? Is it openable somewhere? This is getting hot
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-01-24T14:23:31+00:00
- Post Title: R2 online

the password of the zip archive used by RPGViewer is 4a3408a275b0343719ae2ab7250a8cab0c03b2178a58f2de
but I have not verified if it's fixed or generated at runtime (lack of interest).
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-24T15:24:31+00:00
- Post Title: Re: R2 online

Holy shit, Bugtest, that's it! That's the password !  Brilliant! 

4a3408a275b0343719ae2ab7250a8cab0c03b2178a58f2de

I tried it on many rfs files ! It worked for all of them!  

Now, you should be able to change files in there easily using a standard ZIP GUI 

Full credits to Bugtest for finding it in RPGViewer and Chroxx for coming up with RPGViewer in the first place
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-01-24T15:41:51+00:00
- Post Title: Re: R2 online

eh eh eh unfortunately I simply looked at the memory of RPGViewer with ollydbg 

anyway what amazes me is that a so good program which supports a so big number of games here in occident is totally unknown while (as far as I have seen searching on google some minutes ago) in china it's well known and used...
maybe this is caused by the language or, in this case, probably by the official website of RPGViewer which works only on Internet Explorer: [http://pigspy.ys168.com](http://pigspy.ys168.com)
## Post #18
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-29T21:47:04+00:00
- Post Title: Re: R2 online

Here are the files that is in the extracted model.rfs

Anyone care to look at them? 
[r2models.rar](https://xentaxbackup.github.io/file/1846_r2models.rar)
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-30T07:05:17+00:00
- Post Title: Re: R2 online

> - <ModelScript version="1.1.0">
>
> - <Information>
>
>   <Name>c00001</Name> 
>
>   <Type>TYPE2</Type> 
>
>   <Part>BODY</Part> 
>
>   </Information>
>
> - <Mesh>
>
>   <FileName>c00001.rmb</FileName> 
>
>   </Mesh>
>
> - <Animation Group="G_DEFAULT">
>
> - <Action Name="A_IDLE" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_STAND1" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_STAND2" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_WALK" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_ITEM_PICKUP" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_DEAD" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_SKILL" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_RUNNOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_ATTACK1" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_ATTACK2" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_DAMAGE_UPNOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_DAMAGE_DOWNNOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_DAMAGE_LEFTNOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_DAMAGE_RIGHTNOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_WALK_BACKNOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_STAND_JUMPNOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_STAND_FALLNOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_STAND_LANDNOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_REGENORSAY" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_ONTHEWATER_NOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
> - <Action Name="A_SWIMMING_NOWEAPON" Loop="TRUE">
>
>   <FileName>c00001_00.rab</FileName> 
>
>   </Action>
>
>   </Animation>
>
>   </ModelScript>

The text file seems to be xml? The rab file could contain the scripts for animating the model to the specific stances, while the textures are in the rmb?

Perhaps you should post this specific request in the 3D / 2D Models/Graphics forum?
## Post #20
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-30T12:20:46+00:00
- Post Title: Re: R2 online

Ok, i thought keeping all in one thread was better but i can make a new one in 3D section. The textures are not in one of those because textures have their own archive like chartexture.rfs or something.

So i guess its model + animation + xml table or some such
## Post #21
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-17T21:05:52+00:00
- Post Title: Re: R2 online

If anyone wants to translate this game the password to LangPack.mdb in gui.frs is r821m0d8b27
this contains 99% of the in game text all 11,349 lines in access lol.
## Post #22
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-23T18:12:19+00:00
- Post Title: Re: R2 online

Does anyone have this now as a program that loads meshes in t-pose? Bones added?
## Post #23
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-18T11:13:49+00:00
- Post Title: Re: R2 online

well thanks a lot for it, because the link for RPG Viewer of chrox is broken I update it with new one enjoy.

[RPG Viewer 3 Build 1212](http://depositfiles.com/files/6nnke3jzt)
## Post #24
- Username: premiumorange
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 10, 2011 8:45 am
- Post datetime: 2011-07-10T01:35:44+00:00
- Post Title: Re: R2 online

CriticalError, the depositfile link you posted seems to be down. Could you reupload it?
## Post #25
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-10T17:08:26+00:00
- Post Title: Re: R2 online

> Reply from premiumorange
>
> CriticalError, the depositfile link you posted seems to be down. Could you reupload it?
[RPGViewer3 Build 1212](http://filekeen.com/1f1v1yr2fbgi/RPGViewer3_Build_1212_by_CriticalError.rar.html)
## Post #26
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2013-02-06T14:32:36+00:00
- Post Title: Re: R2 online

Can anyone reupload RPG Viewer 3 Build 1212?
## Post #27
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2013-02-06T14:40:36+00:00
- Post Title: Re: R2 online

> Reply from Drawing
>
> Can anyone reupload RPG Viewer 3 Build 1212?use google, is your friend 

[RPG Viewer 3 Build 1212](http://www.google.com.ar/#hl=es&tbo=d&output=search&sclient=psy-ab&q=RPGViewer3+Build+1212&oq=RPGViewer3+Build+1212&gs_l=hp.3...78.78.0.989.1.1.0.0.0.0.576.576.5-1.1.0...0.0...1c..2.hp.oKfv5WGWWEw&pbx=1&bav=on.2,or.r_gc.r_pw.r_qf.&bvm=bv.41934586,d.dmg&fp=f8af18abcd8ebbcd&biw=1680&bih=935)
