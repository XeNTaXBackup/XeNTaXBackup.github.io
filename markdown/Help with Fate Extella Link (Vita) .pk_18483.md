## Post #1
- Username: Sosfiro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 23, 2018 7:18 am
- Post datetime: 2018-07-23T08:50:45+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

I started to messing around with the pk file yesterday, and trying to decompile it with the pktools, which worked with the PC version of the previous game, Fate Extella. But, when I tried to do it, it fails at the start of the decompilation, giving an error.

So, I tried to use a QuickBms script that also works for PK files, and in this case I got some files, but after extract an incomprehensible number of files that go up in more than 150 GB (and more), I needed to stop it because lack of space in my hard drive. This not make sense, because the file is only 1,2 GB (Probably 3-4 GB decompressed).

This works, but I can't get the files with their original name, and the folder structure, which it's important to simplify the ripping.

So, anyone here knows about another tools or QuickBms script to work with these?

Main file (1,2 GB split in 3 rars): [https://mega.nz/fm/x0QCzQ6Q](https://mega.nz/fm/x0QCzQ6Q)

Tool and script used:
QuickBms script: [http://zenhax.com/viewtopic.php?t=2183](http://zenhax.com/viewtopic.php?t=2183)
PKtools for Fate Extella (PC): [https://github.com/kotcrab/fate-explorer/releases](https://github.com/kotcrab/fate-explorer/releases)
## Post #2
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2018-07-23T14:49:02+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

.pkh format was slightly changed, latest pktools now supports it.
## Post #3
- Username: Sosfiro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 23, 2018 7:18 am
- Post datetime: 2018-07-23T17:16:03+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

Thanks so much! Now the tool works well
## Post #4
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2018-08-05T06:59:53+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

pktools error out when dropping the Vita Extella Link .pk file.
## Post #5
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2018-08-05T07:59:07+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

Looks like you didn't decrypt it completely. Use psvpfstools after extracting main game pkg.
## Post #6
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2018-08-05T09:01:29+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

Got it working now. Thank you.
## Post #7
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-09-24T06:50:54+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

> Reply from Kotcrab
>
> Looks like you didn't decrypt it completely. Use psvpfstools after extracting main game pkg.

I am having the same problem. What do you mean "use" psvpfstools? Nothing on their documentation makes it clear what to do to decrypt this file.
## Post #8
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2018-09-24T16:07:22+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

pkg2zip will create an zip archive with encrypted files. After extracting it and renaming output directory to PCSG01091 you can then run psvpfsparser to decrypt those files:

```
psvpfsparser -i PCSG01091 -o PCSG01091_dec -z put-zRIF-here -f http://cma.henkaku.xyz/
```

You need to change that command to include valid zRIF. After that is done you can use pktools on .pk archive from PCSG01091_dec directory.
## Post #9
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-09-24T17:24:26+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

> Reply from Kotcrab
>
> pkg2zip will create an zip archive with encrypted files. After extracting it and renaming output directory to PCSG01091 you can then run psvpfsparser to decrypt those files:
Code: Select allpsvpfsparser -i PCSG01091 -o PCSG01091_dec -z put-zRIF-here -f http://cma.henkaku.xyz/
You need to change that command to include valid zRIF. After that is done you can use pktools on .pk archive from PCSG01091_dec directory.

uhh, ok so I have used pkg2zip, extracted it and renamed it. But I have no clue how to use psvpfsparser, and no idea what a zRIF is. I looked through all the files in psvpfstools and I don't see any exe files, so I'm guessing its some command prompt commands, but again I have no clue what any of it means. There is just a bunch of C/C+ Files.  

Edit: found the zRIF from where I downloaded the PKG
## Post #10
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2018-09-24T17:39:08+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

Download release zip for your OS, not the source code. [https://github.com/motoharu-gosuto/psvpfstools/releases](https://github.com/motoharu-gosuto/psvpfstools/releases)
## Post #11
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-09-24T17:47:51+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

> Reply from Kotcrab
>
> Download release zip for your OS, not the source code. https://github.com/motoharu-gosuto/psvpfstools/releases
-_- I am disappointed in myself for not thinking of that.
## Post #12
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-09-24T17:53:24+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

Ok no now I renamed it, copied your command, replaced the zRIF and now it says: "failed to find unicv.db file or icv.db folder"

Edit: geez i'm making all kinds of stupid mistakes, I just had to move the recursive file out of the PCSG01091 > App > PCSG01091

Now it is saying: 
Hash tree is ok
Building directory matrix...
Building file matrix...
Flattening file pages...
Building dir paths...
Building file paths...
Linking dir paths...
Linking file paths...
Matching file paths...
Mismatch in number of files + directories agains number of flat blocks

And nothing was decrypted

-______- ok there was another app folder messing everything up. I have no clue why there are multiple empty folders called "app" but I deleted those and now it worked
## Post #13
- Username: jay11800
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jul 12, 2018 10:42 pm
- Post datetime: 2018-09-24T18:29:03+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

alright, and one last question: do I change all the mxt files to dds like with extella, or is there software that will help me convert it?
## Post #14
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2018-09-24T21:51:52+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

Yeah, don't know about those app folders. They shouldn't be there.

Gxt from psp2/texture directory can be opened in Noesis. 
For mxt from psp2/mdltex you can rename them to gxt and try opening them in Noesis. This doesn't work for all mxt files though. There is probably some other tool that can handle this but I haven't looked into that. 
Also, if you want to use my mdl model loading plugin then don't rename them. It handles that automatically.
## Post #15
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-03-19T20:02:04+00:00
- Post Title: Help with Fate Extella Link (Vita) .pk

extracting the PC version of Extella Link gives this error when trying to extract the .pk
## Post #16
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2019-03-20T15:58:19+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

Fixed that in v1.1 [https://github.com/kotcrab/fate-explorer/releases](https://github.com/kotcrab/fate-explorer/releases)
Previous version can't handle archives larger than 4 GB.

Noesis model loader script was also updated to support PC version of Extella Link. Though it still needs more testing.
## Post #17
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-03-20T15:59:23+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

Appreciate the quick response! thanks for your hard work, looking foward to further updates, will report any bugs i find
## Post #18
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2019-03-21T10:05:03+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

If you're willing to and up for it, would there be any plan make the noesis script compatible with God Eater 3 meshes? as it runs on the same engine as extella link and pk extraction worked 100%. I believe akdrebur made a dirty quick edit of your old extella link script to make it work wit GE3 meshes files, so you can find it there and make a further refinements from his tweaks if possible.
[https://forum.xentax.com/viewtopic.php? ... 4&start=15](https://forum.xentax.com/viewtopic.php?f=16&t=17834&start=15)

If you need samples, I could send you some.
## Post #19
- Username: Misaki Ki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 07, 2017 12:08 am
- Post datetime: 2019-03-21T11:13:02+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

> Reply from Kotcrab ↑Wed Mar 20, 2019 11:58 pm at Wed Mar 20, 2019 11:58 pm
>
> Noesis model loader script was also updated to support PC version of Extella Link. Though it still needs more testing.

I was also surprised by the quick release, thank you so much!

The only issue I see so far is that only the albedo textures are exported with the model. Still, it isn't a huge issue since you can extract all the textures manually (or batched) by viewing all files and exporting from the corresponding mds.
## Post #20
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2019-03-21T13:25:44+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

> Reply from ventuhr ↑Thu Mar 21, 2019 6:05 pm at Thu Mar 21, 2019 6:05 pm
>
> 
If you're willing to and up for it, would there be any plan make the noesis script compatible with God Eater 3 meshes?

No, I'm not really interested in it. 
I got a message that my tool doesn't work for God Eater 3 update 1.2. Probably something has changed with how path CRC is calculated. I added sources to the GitHub release if somebody wants to update it or port to QuickBMS.

> Reply from Misaki Ki ↑Thu Mar 21, 2019 7:13 pm at Thu Mar 21, 2019 7:13 pm
>
> 
The only issue I see so far is that only the albedo textures are exported with the model. Still, it isn't a huge issue since you can extract all the textures manually (or batched) by viewing all files and exporting from the corresponding mds.

Edit the script and change this line to say False: 
```
onlyLoadAlbedoTexture = True
```
## Post #21
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-03-21T18:14:34+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

it seems on most models there is bad smoothing, is it possible to get original vertex normals from the game?
## Post #22
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2019-03-21T22:34:04+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

Looks like I can get normals working but I'm having a problem with default lighting settings in Noesis. 
After loading model I need to do "Change Base Orientation" to make preview look okay or use Data Viewer to change lights position. I'm not seeing an obvious way to do this through Noesis API so maybe someone can help me with this.

To enable normals you can add this after line 622, make sure to preserve indentation when editing script:

```
rapi.rpgBindNormalBuffer(vertBuff, noesis.RPGEODATA_FLOAT, vertStride, 0xC)
```
## Post #23
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-03-21T22:42:50+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

I seem to get an error in noesis about inconsistent use of tabs and spaces in indentation despite the script being fine and assumingly preserving indentation, i am using notepad++ btw
## Post #24
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2019-03-21T22:51:19+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

That's because you are mixing tabs and spaces and for some reason Notepad++ default for Python is tabs. 
Anyways I'm silly because I can just upload the script here...
[data_fate_extella.zip](https://xentaxbackup.github.io/file/15936_data_fate_extella.zip)
## Post #25
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-03-21T22:52:31+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

thanks a bunch
## Post #26
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-03-21T23:02:23+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

dang it looks like vertex normals are messed up now
## Post #27
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2019-03-21T23:18:41+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

Yeah it doesn't work, I had wrong assumptions. Ignore that script.

Alternative option is to enable

```
optimizeDx11Models
```

in script config. Depends on a model how well that works.
## Post #28
- Username: alonectorch
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 10, 2019 6:07 pm
- Post datetime: 2019-04-10T22:42:27+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

I've got a similar thing with a .pk for IA V/T Colorful.  Does there's a .pk and a .pkh. Someone here knows how to extract it, right?
## Post #29
- Username: mryesung
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 25, 2018 12:39 am
- Post datetime: 2019-04-23T01:45:22+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

Can someone help me with extracting the animation(motion) file of this game?
the file format is .mtb and I cannot find any programs that can read and extract this file format...
## Post #30
- Username: chlorophylls
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 30, 2019 9:31 am
- Post datetime: 2019-05-01T03:16:26+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

Using Kotcrab's fate-tools to extract the textures in the .pk of Extella Link PC seems to work on the attack and Noble Phantasm effect .ddses just fine, but doesn't seem to be able to extract the character portrait .ddses properly, rendering static noise .ddses instead.

Can anyone help with this?
## Post #31
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-04-25T17:16:52+00:00
- Post Title: Re: Help with Fate Extella Link (Vita) .pk

has there been any progress on the tools for this project?
