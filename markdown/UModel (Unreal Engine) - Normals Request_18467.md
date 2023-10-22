## Post #1
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-07-19T17:38:53+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

Hey peeps. I'm looking for help on getting normal's supported through the unreal engine upk's. Either using Umodel which is open source, or a custom code set which just grabs out normal's from UPK's.

Gildor, the creator of Umodel made it clear he neither has the time, or desire to add Normals support (Source [Here](http://www.gildor.org/smf/index.php?topic=6098.0)). He does not wish to add support for FBX or other file types which support normals. Not to sure why he hasn't thought of the probability of simply adding Normals within the .pksx filetype and reading it with his other tool "ActorX". He did state the pks cannot support it, but I heard conflicting information from others familiar with file types and models.

I am ignorant to the difficulty of that, and the only bases I have is witnessing a friend of mine immediately turn one of his tools into a max-script in 1 day, making a custom file type and importer for XC2 models, before PredatorCZ made his tool. I already attempted to find and ask for help from 5 people I know who deals with game models and extractions and no one had the time to help, its disappointing but understandable, that's why I turn to a request.

I am trying to rip out Normals from Guilty Gear Xrd Rev 2, where the Normals are EVERYTHING on a model. The devs themselves rave about how much their normal work is, so the models are nothing without them. Normal support would also benefit My Hero's One Justice and FighterZ extracts as well. I am merely looking for normal's, I am not asking for entire support, I'll be happy with the mesh + normal's as I can use Umodel afterwards and import the Normals into the rigged mesh there. I thought about using Ninja Ripper to grab the Normals, but NinjaRipper does not (I thought it advertises that it does?). GGXrd Rev 2 uses Unreal 3 while DB FighterZ uses 4, so I'm not to sure if the way Normals are stored changes. As it stands Guilty Gear Xrd Rev 2 model extracts suffer from "Granny Lips" due to the lack of normals. Cellshading shaders alleviate this to a degree, but it still misses a load of details.

If you think you could help, or hell, know of a way I could potentially rip normals out through the game process itself, please let me know. I don't wish to give up on this prospect so soon. I can provide files to look at and analyze.

Here is Ramlethal's UPK files as reference. Viewable in Umodel, follow the image Guide. Encrypted UPK also provided just in case for some reason the decryption loses normal data (who knows?)
[https://mega.nz/#!QF9CQQ7A!aVcUibhR20QK ... 6O9AxtjBqg](https://mega.nz/#!QF9CQQ7A!aVcUibhR20QKz-ZddzrwUjvgmZa1TVzai6O9AxtjBqg)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-07-20T06:52:23+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

> Reply from kurokairaku
>
> as I can use Umodel afterwards and import the Normals into the rigged mesh there.
How are you supposed to do that?

> Reply from kurokairaku
>
> I can provide files to look at and analyze.
Sure, why not?
## Post #3
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-07-21T07:03:56+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

> Reply from Bigchillghost
>
> kurokairaku wrote:as I can use Umodel afterwards and import the Normals into the rigged mesh there. 
How are you supposed to do that?
kurokairaku wrote:I can provide files to look at and analyze.
Sure, why not?

Please don't misunderstand, I'd much prefer to have direct support so I dont have to do manual work such as importing normals onto the original mesh. I just can do that easily in 3DS Max by quite litterally copy pasting the normals over. So long as the mesh is handled the same, has the same number of tri's and verts, it shall be easy. Ideally its still the same mesh, I'm just trying to give people a break here by saying "I only need this one thing" so they dont try to go all out and make full support.

Im hoping it would encourage people to give it a shot.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-07-21T07:32:25+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

> Reply from kurokairaku
>
> So long as the mesh is handled the same, has the same number of tri's and verts, it shall be easy.
That's a premise you don't need to explain, but what I'm curious about is

> Reply from kurokairaku
>
> I just can do that easily in 3DS Max by quite litterally copy pasting the normals over.
How are you supposed to COPY and PASTE normals from one mesh to another such as its clone? That, is what I was asking.

> Reply from kurokairaku
>
> 
Im hoping it would encourage people to give it a shot.
Nothing can be done if you don't upload any samples.
## Post #5
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-07-21T14:09:20+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

> Reply from Bigchillghost
>
> 
How are you supposed to COPY and PASTE normals from one mesh to another such as its clone? That, is what I was asking.

Ah Sorry, I misunderstood your question. Its quite simple. I'll just put a "Edit Normal Modifier" over the copy mesh that has it, then paste that modifier and its information over to the other mesh. It always worked when I attempted it, so I'm hoping it will work in this situation as well. 

I was gonna provide models to those willing to help, but I guess providing it outright would be easier for those who wana quick look. Its Ramlethal so nothing special. It contains UPK files for it, as well as its encypted UPK files, as originally it had to be decrypted through a tool. It also contains other bits which don't really pertain to the problem at hand, they where just there for after I get my hands on the normals. You can find the download in the main post.

Are you actually aiming to help? If so I wish you luck, I've been stuck on this for months now. I KNOW there is normals there. Not only do models suffer from Granny Lips due to improper shading/normals, the devs theselves brag about it. There are possibilities that normals are located elsewhere, or hell the normals are handled by the game and is camera dependent, but alas, I know nothing.
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-21T16:33:32+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

Not much to look at really. From what I have understood UModel is already able to read the normals, it just won't export them. A small modification to the UModel to write the normals to a text file or something should be enough.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-07-22T05:12:30+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

> Reply from kurokairaku
>
> 
Are you actually aiming to help? If so I wish you luck.
I don't think questioning people like that is a polite way to ask for help.

The upk files are compressed and I do not intend to spend any time on the format. But if UE Viewer actually read the normals when displayed, it should not be too difficult to insert a few lines of code somwhere  in the source to write the read normals (maybe even tangents) to an obj or an fbx file. Unfortunately, the source was released without a VS solution, which could result in more work.
## Post #8
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-07-22T08:48:08+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

> Reply from akderebur
>
> Not much to look at really. From what I have understood UModel is already able to read the normals, it just won't export them. A small modification to the UModel to write the normals to a text file or something should be enough.
I am aware of this which is why for the past few months I've been trying to find someone who is adept at this kind of things. In my main post I talked about adding support or exports in normals in Umodel itself. Unfortunately even though "it should be enough" no one I asked had the time to do it or outright refused. All the people I found who had the power where unfortunately busy with their own projects. I respect that of course, that's why I made this post, in hopes someone might be kind enough to help me.

Though I have a sneaking suspicion despite that, Umodel doesn't display Guilty Gear normals properly, considering even within program the models have granny lips issues as well as obvious lack of details. It could be a special case in this regard, in which I hope it wont be too difficult to add support when the time comes...

> Reply from Bigchillghost
>
> 
I don't think questioning people like that is a polite way to ask for help.
I apologize, since you requested files I figured you where aiming to help. Sorry for being so presumptuous. I had no intention of being rude.

> Reply from Bigchillghost
>
> 
The upk files are compressed and I do not intend to spend any time on the format. But if UE Viewer actually read the normals when displayed, it should not be too difficult to insert a few lines of code somwhere  in the source to write the read normals (maybe even tangents) to an obj or an fbx file. Unfortunately, the source was released without a VS solution, which could result in more work.
Its all nice and dandy but unfortunately I have 0 coding knowledge. I spent months trying to find help in that regard, referencing to my reply to akderebur. To be quite honest while I know Umodel reads normals, they sure as hell don't display them properly. Hopefully GG models don't employ special type of normals. As you say it will be work. FBX is obviously out of the question since Gildor himself isn't willing to add support so .obj is the next best thing.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-07-22T09:34:38+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

> Reply from kurokairaku
>
> To be quite honest while I know Umodel reads normals, they sure as hell don't display them properly. Hopefully GG models don't employ special type of normals.
From my rough glance on the source Umodel seems to auto calculate normals if the mesh contians no normals (or unsupported ones?).
If that's the case, you might still need to look into the upk file itself.

> Reply from kurokairaku
>
> FBX is obviously out of the question
Not really. You don't have to use the FBX SDK for that. 
(unless you need your tool be licenced?)

It's rather simple to create a custom ascii FBX file though it doesn't support skeletons yet.
But now that you appreciate obj format so much guess I don't need to bother about that.
## Post #10
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-07-22T23:23:05+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

> Reply from Bigchillghost
>
> kurokairaku wrote:To be quite honest while I know Umodel reads normals, they sure as hell don't display them properly. Hopefully GG models don't employ special type of normals. 
From my rough glance on the source Umodel seems to auto calculate normals if the mesh contians no normals (or unsupported ones?).
If that's the case, you might still need to look into the upk file itself.

Not really. You don't have to use the FBX SDK for that. 
(unless you need your tool be licenced?)

It's rather simple to create a custom ascii FBX file though it doesn't support skeletons yet.
But now that you appreciate obj format so much guess I don't need to bother about that.

Gildor makes it sound like its a job and a half to get FBX supported, so I figured the worst, Still considering you said it doesn't support skeletons then obj would just be simpler i think. Same functions, I get normal. I guess now I need to find someone who's willing to look into what kind of normals are in GG's UPK, support them via Umodel, and get a rough normal export function going so I can start my work. 

I hope the decryption isn't destroying the normals somehow, and the only other thing I notice is the "Unknown blendmode 255" when opening the decrypted upks. Since umodel is recalculating the the normals, it makes me apprehensive, though that explains why it looks bad in there as well.
## Post #11
- Username: gildor
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 25, 2010 5:15 am
- Post datetime: 2019-07-06T16:38:53+00:00
- Post Title: UModel (Unreal Engine) - Normals Request

Hi,

Re: fbx in umodel. I've explained things here: [https://github.com/gildor2/UModel/pull/75](https://github.com/gildor2/UModel/pull/75)

Re: extending pks format. Actually it's not hard to extend file format, and make additional things exported with umodel. Harder thing (for me) is to import that back. There are 2 importers for psk: for 3ds Max (coded by myself) and for Blender ("third-party"). I can't request Blender's developer to update things, and actually there are already some features which are missed there. Regarding 3ds Max import, it's a hard thing for me. I'm very rarely starting Max, and even less - making MaxScript things there. So, adding normals would require a lot of research work for me, I simply don't know how to do that. And free time is the less resource I have - I'd prefer not wasting it for something "3ds Max-ish".

Re: export of normals. It is possible for nearly a year now. You can export models and animations into glTF format - [https://www.gildor.org/smf/index.php/topic,6281.0.html](https://www.gildor.org/smf/index.php/topic,6281.0.html). It is easily imported into Blender and Unity, not sure about anything else (I'm not taking into account various WebGL pages, they are "toys"). As far as I know, Autodesk doesn't support glTF anywhere yet, despite they're part of glTF Kronos group.

Import into UE4: Epic has glTF importer for Unreal, at the moment it's stuck with StaticMesh import. As far as I know, Epic has plans continuing it.
