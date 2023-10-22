## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-06T22:46:48+00:00
- Post Title: Rusty Hearts

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-06T22:59:25+00:00
- Post Title: Rusty Hearts

the format is very simple just need to parse the skeleton and it should be done.
the motion is in the .ma files.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-07T02:15:40+00:00
- Post Title: Rusty Hearts

Here is a 3ds max importer
Supported so far
Verts,Normals,UV's,Faces

[Rusty Hearts.rar](https://xentaxbackup.github.io/file/4588_Rusty Hearts.rar)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-07T02:25:58+00:00
- Post Title: Rusty Hearts

Hmm, is there way to parse the file without jumping from offset to offset? Or is that how the format is structured? (I notice many of your scripts store offsets and then jump around to store data. Don't know if this is just something that is convenient in max script)
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-07T02:28:17+00:00
- Post Title: Rusty Hearts

There is a Chunk Table at the start of this file that gives the offset , size , and chunk type.
i just seek to chunk type 6 mesh
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-07T02:29:45+00:00
- Post Title: Rusty Hearts

Hmm, chunk table. Guess I haven't seen many of those to recognize it.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-07T02:32:35+00:00
- Post Title: Rusty Hearts

it just gives an id string
then it gives a version?
then it gives the number of chunks
then there is a list of offsets * the number of chunks
then a list of the chunk size * the number of chunks
then there is a chunk id/type * the number of chunks

i just store these in an array then loop through them and when chunk type == 6 go to that offset and read the mesh.

i am not sure where you are confused.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-07T02:53:43+00:00
- Post Title: Rusty Hearts

I got the chunk table part after looking at the script. Didn't know what it was when I first looked at it.
## Post #9
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-09T23:28:57+00:00
- Post Title: Rusty Hearts

> Reply from finale00
>
> I got the chunk table part after looking at the script. Didn't know what it was when I first looked at it.the importer just don't do nothing, don't know why, just try import Mgm files and nothing happened anyway thanks for Importer CHROX
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-09T23:59:33+00:00
- Post Title: Rusty Hearts

this adds bones no weights yet because i am not sure on how the bone id's work yet.
thanks to help from reveal8n
[Rusty Hearts.rar](https://xentaxbackup.github.io/file/4604_Rusty Hearts.rar)
## Post #11
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-10T00:13:04+00:00
- Post Title: Rusty Hearts

well don't know really, I only get bones in MAX and you show a picture up with model working :S
[Bones.jpg](https://xentaxbackup.github.io/file/4606_Bones.jpg)
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-10T01:12:45+00:00
- Post Title: Rusty Hearts

what file are you loading?
## Post #13
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-08-10T07:17:36+00:00
- Post Title: Rusty Hearts

> Reply from chrrox
>
> what file are you loading?

Try the sample files at the first post. Most of these files have type 5 not type 6.  

Type 5 has an extra 9 floats before the Vertices datas.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-10T15:40:19+00:00
- Post Title: Rusty Hearts

chrrox has the client and I'm guessing he's only interested in doing characters lol
I only uploaded small stuff like items, which happen to be type 5. Skinned vs unskinned maybe?
## Post #15
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-08-10T15:52:05+00:00
- Post Title: Rusty Hearts

> Reply from finale00
>
> I only uploaded small stuff like items, which happen to be type 5. Skinned vs unskinned maybe?

As I tried the Type 5 works as Type 6 except the Type 5 has an extra 9 floats before the Vertices datas. 

I downloaded the public client but I don't know how can I extract the .pck files under Vista 64.
I tried the pwpack.exe, but nothing happened.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-10T15:56:10+00:00
- Post Title: Re: Rusty Hearts

Did you use the extractors that were uploaded in the archive thread I linked?
These pck's are different from the previous ones.

Fiel uploaded one, and chrrox found one from ragezone which is incomplete but still gets stuff out.
## Post #17
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-10T17:01:09+00:00
- Post Title: Re: Rusty Hearts

> Reply from chrrox
>
> what file are you loading?I trying with different files and one of theme is angela_change.mgm is a character.

> Reply from Karpati
>
> finale00 wrote:I only uploaded small stuff like items, which happen to be type 5. Skinned vs unskinned maybe?

As I tried the Type 5 works as Type 6 except the Type 5 has an extra 9 floats before the Vertices datas. 

I downloaded the public client but I don't know how can I extract the .pck files under Vista 64.
I tried the pwpack.exe, but nothing happened.
I use Windows 7 Ultimate 64 Bits and unpacker post chrox work fine, pwpack not used for this files because the unpacker connected f00X.dat to get files.
## Post #18
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-08-10T17:53:32+00:00
- Post Title: Re: Rusty Hearts

> I use Windows 7 Ultimate 64 Bits and unpacker post chrox work fine, pwpack not used for this files because the unpacker connected f00X.dat to get files.

Thank you for your information. I readed the first page of archive thread, but unfortunately I did not see, it has a second page.  
The extractor (RustyHeartsExtractor.exe) works fine.
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-10T19:39:32+00:00
- Post Title: Re: Rusty Hearts

lol, let me link to the second page so anyone else won't have to go through that.

RustyHeartsExtractor.exe is incomplete, as Fiel pointed out.
I've confirmed that there are folders that should contain models, but doesn't.

Though there are already plenty of models to work with.
## Post #20
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-10T19:45:05+00:00
- Post Title: Re: Rusty Hearts

ill make a bms for this game soon wont be too hard.
## Post #21
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-12T10:32:07+00:00
- Post Title: Re: Rusty Hearts

Here is an updated script weights are not perfect yet i have a few ideas on this to try.
Also it now imports all of the type 6 mesh not just the first part.
[Rusty Hearts.rar](https://xentaxbackup.github.io/file/4617_Rusty Hearts.rar)
## Post #22
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-12T18:01:07+00:00
- Post Title: Re: Rusty Hearts

> Reply from chrrox
>
> Here is an updated script weights are not perfect yet i have a few ideas on this to try.
Also it now imports all of the type 6 mesh not just the first part.
thanks a lot for support chrox, you rock bro, really helpful a lot always keep working.
## Post #23
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-08-14T00:32:50+00:00
- Post Title: Re: Rusty Hearts

Some of these textures look like they need alpha channels.
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-14T01:43:55+00:00
- Post Title: Re: Rusty Hearts

you need to set them as implied alphas as they are dxt1.
## Post #25
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-08-14T11:53:33+00:00
- Post Title: Re: Rusty Hearts

> Reply from chrrox
>
> you need to set them as implied alphas as they are dxt1.

@chrrox Anyway to import "Weapon" into 3ds max ? I tried to import weapon with your script but it import only bone, not mesh.
## Post #26
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-14T12:35:20+00:00
- Post Title: Re: Rusty Hearts

> Reply from goder2910
>
> chrrox wrote:you need to set them as implied alphas as they are dxt1.

@chrrox Anyway to import "Weapon" into 3ds max ? I tried to import weapon with your script but it import only bone, not mesh.it import only characters for now
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-14T12:43:50+00:00
- Post Title: Re: Rusty Hearts

chrrox probably isn't interested in adding support for non-characters.
Mesh type 5 is probably very similar to mesh type 6 though.

Unfortunately most people that know anything about models seem to be

1: only interested in the games they are working with
2: not interested in reversing the format, only having the import script
3: of course, do not reverse formats

Perhaps the tools we have are too difficult to work with.
Maybe a blender import template would spark more interest.
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-14T13:17:11+00:00
- Post Title: Re: Rusty Hearts

ill add type 5 its identical to type 6 i just have not got to it yet. was hoping to fix the weighting issues first.
## Post #29
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-08-15T08:16:33+00:00
- Post Title: Re: Rusty Hearts

For weighting issues please try type 2.
Create array of bone names from this type and change vertex id group in correct bone name.
Skeleton use type 3.
[rusty.jpg](https://xentaxbackup.github.io/file/4625_rusty.jpg)
## Post #30
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-15T09:49:30+00:00
- Post Title: Re: Rusty Hearts

ah that's what type 2 is for lol seems like a waste.
Here is the updated script ill post type 5 later today.
[Rusty Hearts.rar](https://xentaxbackup.github.io/file/4626_Rusty Hearts.rar)
## Post #31
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T06:47:46+00:00
- Post Title: Re: Rusty Hearts

[http://db.tt/8WjMD9Oq](http://db.tt/8WjMD9Oq)

Static meshes can be loaded (type 5)
Still trying to figure out what's wrong with the way I'm parsing the type 6 meshes lol...
## Post #32
- Username: DarkKaine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 12, 2014 2:21 pm
- Post datetime: 2014-10-19T12:24:00+00:00
- Post Title: Re: Rusty Hearts

I know this is a long shot and a necro post but is there any chance of these tools ever being finished?
The developer went out of business and soon only the Chinese version will be on, I think the game will be discontinued soon.
I'm on a team that is developing a private server (from scratch by reversing packets) for this game and we want to pick up where they left off and make new content
## Post #33
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-10-19T13:12:11+00:00
- Post Title: Re: Rusty Hearts

Did you try the 3D Object Converter on your files?

[http://3doc.i3dconverter.com](http://3doc.i3dconverter.com)
## Post #34
- Username: DarkKaine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 12, 2014 2:21 pm
- Post datetime: 2014-10-19T14:28:04+00:00
- Post Title: Re: Rusty Hearts

Yep I have, the problem is that the skeleton is not exported.
If I understand the file format correctly, I could convert 3ds models back to mgm and use them in-game, that's my goal for now
## Post #35
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-10-19T15:26:34+00:00
- Post Title: Re: Rusty Hearts

I am using the XNALara Binary .mesh export format as a 'gateway' to transfer the fully textured objects (with Bone information) to the 3D Studio Max.

You can download the Importer/Exporter script from this web page:
[http://www.tombraiderforums.com/showthread.php?t=181251](http://www.tombraiderforums.com/showthread.php?t=181251)


Procedure:
1. First time you must copy the "XnaLara Converter.ms" file into your installed 3D Studio Max Scripts folder.
2. Run your 3D Studio MAX

3. Open your .mgm file with 3D O.C.
4. Export the loaded object as XNALara Binary .mesh format.

5. Run your "XnaLara Converter.ms" script using the MAXScript/Run Script... menuitem.
6. Press the Import button on the XNALara Converter window.
7. Browse the converted .mesh file.
