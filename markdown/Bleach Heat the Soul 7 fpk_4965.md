## Post #1
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-09-02T17:58:39+00:00
- Post Title: Bleach Heat the Soul 7 fpk

how do you open the fpk and export the models?
## Post #2
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-09-02T22:39:08+00:00
- Post Title: Bleach Heat the Soul 7 fpk

> Reply from philip92dk
>
> how do you open the fpk and export the models?
fpk extractor + ttd extractor
[viewtopic.php?f=10&t=4038&start=0&st=0&sk=t&sd=a](http://forum.xentax.com/viewtopic.php?f=10&t=4038&start=0&st=0&sk=t&sd=a)
These link will help extract.
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-09-03T13:44:14+00:00
- Post Title: Bleach Heat the Soul 7 fpk

seems its .gmo files so can be used by common psp utilities
## Post #4
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-09-03T13:51:00+00:00
- Post Title: Bleach Heat the Soul 7 fpk

thanks for the help youngmark
## Post #5
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-09-03T15:52:41+00:00
- Post Title: Bleach Heat the Soul 7 fpk

can i get the models with bones?
## Post #6
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-09-05T16:43:59+00:00
- Post Title: Bleach Heat the Soul 7 fpk

yes basically you need to export to dae and open it in max using opencollada plugin, not the fucking one that come with 3dsmax , then you got the mesh parts + bones
but i have noticed that the export is still a little wrong as it export some meshes merged in one group, like if the groups were grouped by material
## Post #7
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-09-07T11:45:32+00:00
- Post Title: Bleach Heat the Soul 7 fpk

thanks
## Post #8
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-09-10T08:44:42+00:00
- Post Title: Bleach Heat the Soul 7 fpk

model viewer nearly ready :


yeah !!!
## Post #9
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-09-10T18:04:09+00:00
- Post Title: Bleach Heat the Soul 7 fpk

cool a model viewer can it export in MDL with bones?
## Post #10
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-09-12T19:18:17+00:00
- Post Title: Bleach Heat the Soul 7 fpk

nope, no export function actually
## Post #11
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-05T21:54:11+00:00
- Post Title: Bleach Heat the Soul 7 fpk

You guys say it's gmo models. But it must be some derivative or compressed gmo as I can't get a gmo file out of anything I've extracted from the fpk.

I'm lead to believe that, 0000.psp.i3r would be the mesh/model data and I already know that the .tm2 files are the textures. But if the .psp.i3r files really are .gmo models how should I go about converting them? My apologies for the necropost, I was asked by someone to help them with this but I seem to have run into a problem with this.
## Post #12
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-11-06T13:02:09+00:00
- Post Title: Bleach Heat the Soul 7 fpk

use Noesis Zerox it can load the gmo  but i cant get the textures to work   
[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)
## Post #13
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-07T04:17:36+00:00
- Post Title: Bleach Heat the Soul 7 fpk

> Reply from Zerox
>
> You guys say it's gmo models. But it must be some derivative or compressed gmo as I can't get a gmo file out of anything I've extracted from the fpk.

I'm lead to believe that, 0000.psp.i3r would be the mesh/model data and I already know that the .tm2 files are the textures. But if the .psp.i3r files really are .gmo models how should I go about converting them?

I understand that Noesis can convert and view gmo models as well as the .tm2 textures. But As I posted above there are no gmo files extracted from the iso I searched the entire iso dump and came up empty. The string .gmo isn't located in any of the file names. I read somewhere else that the .i3r files were the .gmo model. Which is great but there is no converter for .i3r to .gmo. And simply changing the extension didn't work either.

You say you can find the ,gmo files but not the textures. Well I can find .i3r models that are supposedly .gmo but I can't find anyway to make them valid .gmo files. Yet I can find and convert the .tm2 textures with ease using Noesis.

I'll explain what I did and then perhaps you can explain what you did that allowed you to see .gmo files instead of the .i3r. First I converted the CSO compressed ISO to a normal ISO with a program called PSP ISO Compressor. Then I extracted the Iso with WINRAR. After this I looked around in the extracted files and found .fpk archives in the directory "ISO\PSP_GAME\USRDIR\data\fpack\chr\"'s inner folders. I used the fpk extractor posted earlier in this thread to extract those and then I looked in them and found the .tm2 texture files in the folders that were extracted. Inside this folder there were also .mpk, .psp.i3r (I don't know if it's all part of the extension but possibly), .seq, and .sgd. No gmo's in site even though the .tm2 textures were there. 

Specifically I was in the directory, "ISO\PSP_GAME\USRDIR\data\fpack\chr\or4\0000_fpk\chr\or4" After viewing the textures it was quite obvious I had found Orihime's data. Sadly though I couldn't find a .gmo.

This is where I found the textures for character models though. Please do enlighten me on how you managed to find actual .gmo models.
## Post #14
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-11-07T12:52:33+00:00
- Post Title: Bleach Heat the Soul 7 fpk

First i use winrar to extracted the fpack from my iso to a New folder I used the fpk extractor to extract the fpk  C:\Users\bigboss\Documents\3d model\data\fpack\chr\nem I used the fpk extractor on 0000.fpk and insite my fpk\0000_fpk\chr\nem 
is there gmo and ttd files
## Post #15
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-07T13:17:03+00:00
- Post Title: Bleach Heat the Soul 7 fpk

Is this the same FPK as Capcom used in Fate/Unlimited Codes? If so, Noesis should be able to handle it as well, although I see now that it's outputting screwy file names. I should probably fix that.
## Post #16
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-07T20:59:12+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

Well philip92dk, I tried that exact folder and still got i3r and .tm2 files. Quite odd. We seem to be doing the same thing yet getting different results. Does anyone know if this is because I converted mine from a compressed iso?

Mr. Adults it seems that Noesis can indeed extract them. It'd be great if you were able to make it work and produce valid .gmo files.
## Post #17
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-11-08T00:25:42+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

if you followed the workflow correctly you should be able to get .gmo and .ttd files. as that is what i'm getting from the fpkextractor. anyhow, have you tried other fpk files for other characters? if you're still getting the same results (i3r and .tm2 files) then, try checking the file through hex editor and search for "OMG" string as keyword, that is a good indicator if the i3r has gmo data. then, try using MrAdult's GitMo > [http://www.richwhitehouse.com/index.php ... nc_res.php](http://www.richwhitehouse.com/index.php?content=inc_res.php) to extract the gmo files from the i3r.

good luck, cheers!
## Post #18
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-08T03:41:44+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

Wow I feel totally sheepish now. I apologize for the trouble I caused. Turns out I made an iso outta Heat the Soul 5 rather than 7. I believe I just   myself. I'll make an iso off my 7 game now and come back with results later. My apologies for the confusion.
## Post #19
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-11-08T12:42:22+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

lolz i hav don dat Error myself
## Post #20
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-08T19:14:42+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

Okay that solved my problem I'm fully capable of getting these models now. Though when using Noesis to convert to .smd it seems to merge all the mesh parts into 1 piece though exporting it as an obj yields a result with them properly separated to match with their textures. The only issue being that there appears to be multiple hands that are all merged together but this is something I can fix manually.

So phillip what is it your struggling with on the .ttd? You just need to use the ttd extractor posted earlier in this thread.
## Post #21
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-11-09T10:52:25+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

> Reply from Zerox
>
> Zerox wrote:You guys say it's gmo models. But it must be some derivative or compressed gmo as I can't get a gmo file out of anything I've extracted from the fpk.

I'm lead to believe that, 0000.psp.i3r would be the mesh/model data and I already know that the .tm2 files are the textures. But if the .psp.i3r files really are .gmo models how should I go about converting them?

I understand that Noesis can convert and view gmo models as well as the .tm2 textures. But As I posted above there are no gmo files extracted from the iso I searched the entire iso dump and came up empty. The string .gmo isn't located in any of the file names. I read somewhere else that the .i3r files were the .gmo model. Which is great but there is no converter for .i3r to .gmo. And simply changing the extension didn't work either.

You say you can find the ,gmo files but not the textures. Well I can find .i3r models that are supposedly .gmo but I can't find anyway to make them valid .gmo files. Yet I can find and convert the .tm2 textures with ease using Noesis.

I'll explain what I did and then perhaps you can explain what you did that allowed you to see .gmo files instead of the .i3r. First I converted the CSO compressed ISO to a normal ISO with a program called PSP ISO Compressor. Then I extracted the Iso with WINRAR. After this I looked around in the extracted files and found .fpk archives in the directory "ISO\PSP_GAME\USRDIR\data\fpack\chr\"'s inner folders. I used the fpk extractor posted earlier in this thread to extract those and then I looked in them and found the .tm2 texture files in the folders that were extracted. Inside this folder there were also .mpk, .psp.i3r (I don't know if it's all part of the extension but possibly), .seq, and .sgd. No gmo's in site even though the .tm2 textures were there. 

Specifically I was in the directory, "ISO\PSP_GAME\USRDIR\data\fpack\chr\or4\0000_fpk\chr\or4" After viewing the textures it was quite obvious I had found Orihime's data. Sadly though I couldn't find a .gmo.

This is where I found the textures for character models though. Please do enlighten me on how you managed to find actual .gmo models.

so as i can see your are missing the thread name :
bleach heat the soul games (1 to 6 ) use i3r files for models (custom format) where bhts 7 use psp gmo files...
i can send a simple app to convert i3r to obj if needed :p
MrAdult>yup same as fate unlimited code psp gmo...

also i can say you the i3r models have better textures than the same model ported to gmo in bhts7, they downscaled the textures res :/
## Post #22
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-11-09T13:59:34+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

please do sir shadowmoy 

thank you so much!
## Post #23
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-09T14:18:56+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

Well as I said I figured out how to convert the gmo's of 7. But an obj converter for the other format could be helpful as well.
## Post #24
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-11-09T19:37:39+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

i hav solved my problem
## Post #25
- Username: bhts7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 26, 2011 10:02 am
- Post datetime: 2011-04-27T04:11:54+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

but where is the file with the animations?
I only get 2 gmo files, 1 mot file, 1 seq file and 4 ttd files
## Post #26
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-05-02T01:49:10+00:00
- Post Title: Re: Bleach Heat the Soul 7 fpk

its impossible to extract the animation i think
