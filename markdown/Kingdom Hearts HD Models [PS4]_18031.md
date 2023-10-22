## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-26T21:51:39+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

Hello,

I recently got the game files of Kingdom Hearts HD on ps4, and I am looking for the model data. I wasn't quite sure where to start, as the extracted files don't have proper filenames or extensions. After looking at the files, I have found out some which seem to have index/vertex data.

Here are some samples : [http://www.mediafire.com/file/1phso0fpk ... amples.rar](http://www.mediafire.com/file/1phso0fpkay76ww/kh_samples.rar)

At first glance it looks like there are indices near the beginning, and a bit after that is a set of floats (possibly vertex data). Still there are lots of repeating indices which doesn't make much sense, so I might be mistaken. I would appreciate it if you can take a look.

Thanks for your help.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-27T08:26:52+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

Hello, I'd suggest to start with vertices here, since as long as you don't get a decent point cloud even perfect face indices wouldn't help you.

I tried multiples of four for the FVF size (12, 16, ...) to no avail:



modsamp4.jpg (136.31 KiB) Viewed 908 times
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-27T09:02:14+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

> Reply from shakotay2
>
> I'd suggest to start with vertices here, since as long as you don't get a decent point cloud even perfect face indices wouldn't help you.
Thanks for the tip shakotay, I will focus on the vertices. I also still have doubts if these are really model files, so I will check out some other files first.
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-01T00:00:11+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

An update on this. Those were indeed not the model files. Also there are no indices for the meshes, vertices are already provided in order.

I decided to switch to KH1 files and noticed the "MOBJ" header in some files. The model format is almost identical to KH1 on ps2. So revelation's noesis plugin code is still viable. I just noticed a small difference for bone matrices, that's all.

In the end I was able to load quite a few models, by re-implementing the plugin code. Here is Yuffie for example.



There are out of place vertices for some of the characters. Either there are some small changes in the format that I didn't notice or there is a slight problem with my implementation. Still it is sufficient for me atm.

The character models don't seem really impressing though. There is little to no improvement on the models/textures compared to the ps2 version. I will still take a look at the KH2 models, but I don't think I will see much improvement there either.
## Post #5
- Username: onelight
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 01, 2017 12:05 am
- Post datetime: 2018-06-17T05:29:11+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

I just got Kingdom Hearts HD 1.5+2.5
How did you extract psacr files, my psarc.exe not working
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-17T09:15:31+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

> Reply from onelight
>
> my psarc.exe not working
Use this quickbms script : [http://aluigi.org/bms/brink.bms](http://aluigi.org/bms/brink.bms)
## Post #7
- Username: onelight
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 01, 2017 12:05 am
- Post datetime: 2018-06-17T10:34:45+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

> Reply from akderebur
>
> onelight wrote:my psarc.exe not working
Use this quickbms script : http://aluigi.org/bms/brink.bms
Think you, brink.bms working though files don't have proper filenames or extensions.
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-17T11:08:59+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

> Reply from onelight
>
> files don't have proper filenames or extensions.
Still the names don't seem to be all that random. It looks like files have hashes as names. For KH2 the extracted file with the name "00000000000000000000000000000000" contains the proper names for all of the files. There is also another file called "KH2.IDX" which seems to contain some offsets, and possibly hashes. I think you might be able to get proper names using both of those files.

I only wanted to get the models, so I ended up writing a program that bulk parses all the files and loads the ones that have model data. It worked out well for me, so I didn't bother with the file names.
## Post #9
- Username: onelight
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 01, 2017 12:05 am
- Post datetime: 2018-06-30T07:18:22+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

> Reply from akderebur
>
> onelight wrote:files don't have proper filenames or extensions.
Still the names don't seem to be all that random. It looks like files have hashes as names. For KH2 the extracted file with the name "00000000000000000000000000000000" contains the proper names for all of the files. There is also another file called "KH2.IDX" which seems to contain some offsets, and possibly hashes. I think you might be able to get proper names using both of those files.

I only wanted to get the models, so I ended up writing a program that bulk parses all the files and loads the ones that have model data. It worked out well for me, so I didn't bother with the file names.
I finally found a worikng psarc.exe and get the files with right names.
BTW, do you have any idea how to modding this game, for exmaple, how to edit *.bar file



tt.PNG (63.56 KiB) Viewed 718 times
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-30T08:02:27+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

File formats are almost identical to the ps2 version, at least the ones related to models. If you can find some info on ps2 modding, you can probably apply it to these files too.
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-07-02T07:54:22+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

akderebur, is any progress on the tool?
## Post #12
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-02T09:58:00+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

> Reply from Tosyk
>
> akderebur, is any progress on the tool?
I did make a tool for my personal use, but actually you don't need new tools to load these files. For KH2, after you unpack the psarc, you can use the bms script I attached to unpack the textures and the mdlx file from the model files. Finding which files are model related isn't easy without proper names, but if onelight shares the psarc program he mentioned, you can probably spot them easier. After you have the mdlx, you can just load it with Noesis, using the KH2 plugin for ps2.



Of course the KH2 plugin doesn't use the new GNF textures, but it uses the lower quality ones (for ps2) inside the mdlx file. So I made a tool for myself to load the models faster and bit more conveniently. It is based on the ps2 model viewer khkh_xldMii, I just added support for the GNF textures. Also you don't need the bms script anymore. I might release it after I polish it a bit, but I don't think it is that necessary.


[kh25bms.rar](https://xentaxbackup.github.io/file/14540_kh25bms.rar)
## Post #13
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-07-02T15:20:49+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

Nice work here akderebur   
Just for the future, Noesis supports .psarc files (also from PS4 games) with names extraction, should make it easier.
## Post #14
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-02T16:40:42+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

> Reply from o0Crofty0o
>
> 
Just for the future, Noesis supports .psarc files (also from PS4 games) with names extraction, should make it easier.
Didn't know that noesis is able to extract psarc archives. I will take note of that.
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-07-04T07:00:03+00:00
- Post Title: Kingdom Hearts HD Models [PS4]

> Reply from akderebur
>
> Tosyk wrote:akderebur, is any progress on the tool?
I did make a tool for my personal use ... I might release it after I polish it a bit, but I don't think it is that necessary.thanks for the info, akderebur, I'll take a look at it when I get back home this evening. It' would be nice to have the better textures and the only way to get them is to use your tools as I understand - so please share it if possible    thanks again
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-04T09:46:59+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

> Reply from Tosyk
>
> the only way to get them is to use your tools as I understand
Not quite. The bms script still exports the gnf textures, you just need to apply them manually. My tool is just for convenience really.
## Post #17
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-04-13T11:50:01+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

A bit of update on this. So Noesis does extract the PSarc files, but for some reason no file inside works, either PNG, or SCD or anything else. What could be the reason? Perhaps I'm using a wrong PKG?
## Post #18
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2019-05-26T21:42:53+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

Has someone been able to find Peter Pan’s high poly model? For some reason, I’ve only managed to find the low poly one. No sign of the high poly model on the files...
## Post #19
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-05-26T23:07:34+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

you sure there is one?
## Post #20
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2019-05-27T04:50:07+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

> Reply from Devilot ↑Mon May 27, 2019 7:07 am at Mon May 27, 2019 7:07 am
>
> 
you sure there is one?
Yup, look:
[https://imgur.com/syEJRf9](https://imgur.com/syEJRf9)
## Post #21
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-05-27T08:21:38+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

I'll take a look
## Post #22
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2019-05-27T16:58:42+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

> Reply from Devilot ↑Mon May 27, 2019 4:21 pm at Mon May 27, 2019 4:21 pm
>
> 
I'll take a look
Ok thank you! Please let me know if you find anything.
## Post #23
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-05-28T12:13:15+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

Nothing yet but I haven't looked very deeply. Any more cues as to identify the high poly model?
## Post #24
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2019-05-28T12:46:03+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

> Reply from Devilot ↑Tue May 28, 2019 8:13 pm at Tue May 28, 2019 8:13 pm
>
> 
Nothing yet but I haven't looked very deeply. Any more cues as to identify the high poly model?
Hmm, not really. Apparently the model is only used in, like, 2 cutscenes? One before facing Hook and the other at the end in the Clocktower. Maybe because of the model not being used that much they put it in some other part of the game’s files?
I don’t have the PS4 files, I only have the PS2 ones for reference so I don’t know if the structure is any different, but in PS2 the majority of the models are stored at KINGDOM.idx file. I did not check the IRX files yet because I don't know how to extract them so idk what they contain, but maybe one of them contains some hidden models (beta models, models that aren’t used that much, etc)? And if the PS4 files follow the same structure as the PS2 ones, maybe the high poly model for Peter Pan is hidden in some of those? We could try checking those.
## Post #25
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-05-29T08:46:29+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

I already unpacked all the PS4 files needed, it's just a matter of Kh1 animations not being viewable in Noesis.
## Post #26
- Username: rtscholten
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 26, 2019 10:57 pm
- Post datetime: 2019-07-29T14:42:04+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

Anyone got KH3 models for download?
## Post #27
- Username: Pence
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 31, 2018 6:19 am
- Post datetime: 2019-08-24T07:19:50+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

Can anyone send me a dump of the textures for each model? I'm using the ps3 dump and get all sorts of folders like this, can't even open the mdlx files up with noesis.
## Post #28
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-08-24T18:12:48+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

Truth be told, its more interesting get textures over models, specially keyblades textures
## Post #29
- Username: Pence
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 31, 2018 6:19 am
- Post datetime: 2019-08-24T22:22:00+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

Exactly, I honestly just want those. Lol
## Post #30
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-08-24T23:55:29+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

> Reply from Pence ↑Sun Aug 25, 2019 6:22 am at Sun Aug 25, 2019 6:22 am
>
> 
Exactly, I honestly just want those. Lol

Then we're two~.
I mostly want the ones of the 3D, because many were very amazing on that one
## Post #31
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-08-25T19:39:37+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

> Reply from Darkhowlings ↑Sun Aug 25, 2019 2:12 am at Sun Aug 25, 2019 2:12 am
>
> 
Truth be told, its more interesting get textures over models, specially keyblades textures

How so?
## Post #32
- Username: Pence
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 31, 2018 6:19 am
- Post datetime: 2019-08-26T03:00:05+00:00
- Post Title: Re: Kingdom Hearts HD Models [PS4]

Does anyone know how to open up or export the GNF textures? I'd like to use them.
