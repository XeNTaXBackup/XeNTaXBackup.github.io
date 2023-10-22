## Post #1
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2018-10-15T07:44:31+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

Okay, so I know this was brought up like 6 years ago, but thats exactly the problem, it's old, so I'm not sure if I can rely on any responses from the original posters. Basically, Dark Cloud, Dark Cloud 2, and Dragon Quest 8 (all LEVEL-5 games) use a .chr compressing system for their models, similar to Valve using .vpk files, and someone from TCRF has found out how to extract the .chr files, but that leaves a whole new problem; The model file is entirely foreign to me. I've never heard of a .mds file, and I can't find an conversion tool for it. I've tried using some old QuickBMS script from a use called Falo. He wrote a script for unpacking individual .chr files that just plain doesn't work. Someone else wrote a QuickBMS script for unpacking the entire Dark Cloud 2 .dat for its models, but it just likes to spit out this garbage: 




 There's no texture, and the models are very broken. If at all possible, I'm just looking for a way to convert a .mds file to something like .obj easily. I don't need animations, and I can figure out textures later, but it's the model files that I'm stuck on. Thanks a ton.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-15T11:56:58+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

So why don't you just upload some sample files?
## Post #3
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2018-10-16T03:38:20+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from Bigchillghost
>
> So why don't you just upload some sample files?

Duh, Obviously. Sorry, I'm fairly new lmao.

[https://drive.google.com/drive/u/0/fold ... rvXF0laAH2](https://drive.google.com/drive/u/0/folders/1derxx25fRvKW2XLXq-vdTfrvXF0laAH2)

Obviously, the info.cfg is the configuration file

the mds is a model, and the img is a compressed tm2

and the rest are animations files, which i don't care about.

Thanks a ton for the help 

edit: Oh, and the mds and bbp with s at the end of the filename are shadows, they don't matter either, thanks.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-16T04:32:23+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

Your link is not accessable.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-16T05:42:54+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from Bumper3241
>
> There's no texture,A known problem with those PS2 (?) scripts; should be fixable, though.

> and the models are very broken. If at all possible, I'm just looking for a way to convert a .mds file to something like .obj easily.I found the scripts from FurryFan very helpful, though they are not really "readable". But you won't find an easy solution, imho.

> Reply from Bumper3241
>
> Someone else wrote a QuickBMS script for unpacking the entire Dark Cloud 2 .dat for its models
you're speaking of FurryFans script (?):
[viewtopic.php?f=16&t=7780&p=88954&hilit ... oud#p88954](http://forum.xentax.com/viewtopic.php?f=16&t=7780&p=88954&hilit=dark+cloud#p88954)
You might upload the first 32 MB of the Data.dat (mark bytes from offset 0 to 0x2000000 in a hexeditor, then save selected (binary)).
## Post #6
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2018-10-16T11:04:10+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from Bigchillghost
>
> Your link is not accessable.

I fixed it, sorry about that.
## Post #7
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2018-10-16T11:05:42+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> you're speaking of FurryFans script (?):
>
> viewtopic.php?f=16&t=7780&p=88954&hilit ... oud#p88954
>
> You might upload the first 32 MB of the Data.dat (mark bytes from offset 0 to 0x2000000 in a hexeditor, then save selected (binary)).

I have absolutely no idea how to do that.

> though they're not really readable

Well then what's the point if the .3ds output files aren't even readable?
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-16T12:50:03+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from Bumper3241
>
> the mds is a model
These files are too small and there're a lot fragments inside that couldn't even build a senseful point cloud. Do you have larger mds files (200 Kb at least)?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-16T16:55:27+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from Bumper3241
>
> Well then what's the point if the .3ds output files aren't even readable?would be nice if you didn't create wrong quotes!
I wrote that his scripts are not really readable.
The correct quote would have been:

> Reply from shakotay2
>
> I found the scripts from FurryFan very helpful, though they are not really "readable".And the point his that his scripts are the only ones which creates meshes, didn't find better solutions.
Why it doesn't work for you I can't tell as long you don't provide the required data.
## Post #10
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2018-10-17T00:17:36+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from Bigchillghost
>
> 
These files are too small and there're a lot fragments inside that couldn't even build a senseful point cloud. Do you have larger mds files (200 Kb at least)?

Well it's a model from a 2002 PS2 game, I wouldn't expect it to be that big. Especially with the liberties LEVEL-5 took with the models in DC2.

[https://drive.google.com/drive/u/0/fold ... rvXF0laAH2](https://drive.google.com/drive/u/0/folders/1derxx25fRvKW2XLXq-vdTfrvXF0laAH2)

Once again, the mds file is 63 kb, but the mot file is 300+. idk if maybe thats he model and we were all wrong, or what, but maybe try that if you could. thanks.
## Post #11
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2018-10-17T00:21:46+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from shakotay2
>
> Bumper3241 wrote:Well then what's the point if the .3ds output files aren't even readable?would be nice if you didn't create wrong quotes!
I wrote that his scripts are not really readable.
The correct quote would have been:
shakotay2 wrote:I found the scripts from FurryFan very helpful, though they are not really "readable".And the point his that his scripts are the only ones which creates meshes, didn't find better solutions.
Why it doesn't work for you I can't tell as long you don't provide the required data.

Sorry, you're dealing with a complete moron here lmao. i didn't mean to misquote you, i just misunderstood. I used the version directly from the ps2model website thing (i forgot the name of the site), but maybe i did something wrong. could you send me the script as a file, and i'll try using it. thanks.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-17T04:55:36+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

It's linked in one of my posts above:
[viewtopic.php?f=16&t=7780&p=88954&hilit ... oud#p88954](http://forum.xentax.com/viewtopic.php?f=16&t=7780&p=88954&hilit=dark+cloud#p88954)
It's the script you were already using(?, so this won't change anything...  )

I'd really suggest to use a hexeditor to create that 32 MB snippet from Data.dat I was talking of.
(HxD is a useful hexeditor and I could give advise on how to use it.)
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-17T08:58:13+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from Bumper3241
>
> the mds file is 63 kb, but the mot file is 300+. idk if maybe thats he model and we were all wrong, or what, but maybe try that if you could. thanks.
The mot files are definitely not model files. Probably the data inside are some quaternions, who knows. And the config file said it's motion data, which would make sense. Yeah, you can also tell that the mds are indeed model files from these info, as well as the contents in other files. But as you've said, the game is a 2002 game (WHAT?!!!), they probably used some old techniques for the model format, at least the indices are neither triangles nor trixstrips imo.
## Post #14
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2018-10-17T11:16:24+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from shakotay2
>
> It's linked in one of my posts above:
viewtopic.php?f=16&t=7780&p=88954&hilit ... oud#p88954
It's the script you were already using(?, so this won't change anything...  )

Yeah, but knowing me I probably messed something up.

> Reply from shakotay2
>
> I'd really suggest to use a hexeditor to create that 32 MB snippet from Data.dat I was talking of.
(HxD is a useful hexeditor and I could give advise on how to use it.)

Yes, please, that'd be insanely helpful.
## Post #15
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2018-10-17T11:18:19+00:00
- Post Title: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from Bigchillghost
>
> Bumper3241 wrote:the mds file is 63 kb, but the mot file is 300+. idk if maybe thats he model and we were all wrong, or what, but maybe try that if you could. thanks.
The mot files are definitely not model files. Probably the data inside are some quaternions, who knows. And the config file said it's motion data, which would make sense. Yeah, you can also tell that the mds are indeed model files from these info, as well as the contents in other files. But as you've said, the game is a 2002 game (WHAT?!!!), they probably used some old techniques for the model format, at least the indices are neither triangles nor trixstrips imo.

Yeah, Dark Cloud came out in 2000, and the sequel came out in 2002, and that's all we've had lmao. And other than that, I'm not exactly sure what you mean lol
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-17T11:38:17+00:00
- Post Title: Re: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from Bumper3241
>
> 
shakotay2 wrote:I'd really suggest to use a hexeditor to create that 32 MB snippet from Data.dat I was talking of.
(HxD is a useful hexeditor and I could give advise on how to use it.)

Yes, please, that'd be insanely helpful.You need to download HxD before.
## Post #17
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2018-10-23T03:44:39+00:00
- Post Title: Re: [Request] Dark Cloud 2 model/texture extraction tools?

> Reply from shakotay2
>
> 
(HxD is a useful hexeditor and I could give advise on how to use it.)

Could you please, that'd be great.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-23T20:54:01+00:00
- Post Title: Re: [Request] Dark Cloud 2 model/texture extraction tools?

so here we go, HxD is expected to have been downloaded to your pc:

> Reply from shakotay2
>
> You might upload the first 32 MB of the Data.dat (mark bytes from offset 0 to 0x2000000 in a hexeditor, then save selected (binary)).
File open
Data.dat
Edit / select block
Start-offset: 0
End-offset: 0x2000000
[ok] -> block is selected now

there's no "save selected" so
Edit/Copy
File/New
Edit/Paste insert
File save
"datasnippet32MB.bin"

or something like that (without the quotes)
upload to zippyshare/whatever filehoster (without the need of google, twitter login or other annoying stuff  )

done
