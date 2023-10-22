## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2012-04-13T12:21:27+00:00
- Post Title: Star Ocean 3 models?

Hello, I have been trying to rip model from Star Ocean 3. After some research I have found a tool to extract the files from the iso which gave me files like pk1, pk2, pk3, slz, and so on. After that I have found [another tool](http://www.romhacking.net/utilities/819/) to extract files from the slz files, but i'm not really sure where to go from there..
I'm pretty sure that the models can be extracted because of this [link.](http://ps23dformat.wikispaces.com/Star+Ocean+Till+the+End+of+Time)
any help on the subject is much appreciated.
## Post #2
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-04-13T14:26:07+00:00
- Post Title: Star Ocean 3 models?

Read the rules here did you?
## Post #3
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2012-04-13T19:19:49+00:00
- Post Title: Star Ocean 3 models?

I did red the rules. Guessed I missed the part about the linking.
Sorry about that.
It would be awesome If I can still get help with the models.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-13T22:44:18+00:00
- Post Title: Star Ocean 3 models?

Yes, you can extract the models if you follow their instructions, which they don't seem to have provided.

I personally never looked into how to extract models by copying hex code into a *word document* or whatever, but it gets you the faces.
## Post #5
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2012-04-14T01:23:37+00:00
- Post Title: Star Ocean 3 models?

Well that's what I have been trying to do but I'm not entirely sure how. 
Just a way to get a mesh like in the link will be enough.
## Post #6
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-10-08T18:21:07+00:00
- Post Title: Star Ocean 3 models?

The tri-strips are explicitly stated right before every object!
What Luck!

What's crazy is, there's objects composed of tri-strips like
"04 03 04 03 03 03 03 03 03 03 03 03 03".
So with the degenerate triangles removed to delineate the tri-strips you're left with
"02 01 02 01 01 01 01 01 01 01 01 01 01",i.e., 11 of the 13 tri-strips consist of only a single triangle!   
Seems like this would be rather inefficient.
(don't even get me started on "03 03 03 03 03 03 03 03 03"  )
## Post #7
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-10-08T19:19:22+00:00
- Post Title: Star Ocean 3 models?

I didn't look at this game. But from what your picture show, that indices "03 03 05 03 07 07 05 06 04" is how many vertices for a single strip!
What that means is:
3: [1,2,3]
3: [4,5,6]
5: [7,8,9,10,11]
3: [12,13,14]
7: [15,16,17,18,19,20,21]
...

But "02 01 02 01 01 01 01 01 01 01 01 01 01" sound ridiculous!?
## Post #8
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-10-09T00:01:18+00:00
- Post Title: Star Ocean 3 models?

Yes. I was going by faces instead of vertices, but it amounts to the same thing.
I have a strange (usually backwards) way of visualizing things.  
Anyway, here's that "ridiculous" object. 16 objects like this make Sophia's head.
Are the PS2 models made from many small objects because of the VU's memory limitations?
## Post #9
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-10-09T06:27:30+00:00
- Post Title: Star Ocean 3 models?

It's the skinning problem! see this reference: [http://www.gamasutra.com/view/feature/1 ... zation.php](http://www.gamasutra.com/view/feature/1566/skinned_mesh_export_optimization.php)
## Post #10
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-10-09T16:10:07+00:00
- Post Title: Star Ocean 3 models?

Well to paraphrase Dark Force over at [http://superfamicom.org/translations/in ... an-english](http://superfamicom.org/translations/info/star-ocean-english);
...damn this format is evil. The Dude will now be recuperating from Star Ocean-induced injuries.

Here's the utilities and importer: [https://app.box.com/s/q1cnoiwi9nfs50777owl](https://app.box.com/s/q1cnoiwi9nfs50777owl)

[](http://fc01.deviantart.net/fs71/f/2014/093/5/2/albel_s_christmas_presents_by_mrfuzzlebum-d6y2i5d.jpg)
## Post #11
- Username: soneek
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Oct 20, 2011 5:43 am
- Post datetime: 2013-01-06T21:06:58+00:00
- Post Title: Star Ocean 3 models?

> Reply from TheDude
>
> Well to paraphrase Dark Force over at http://superfamicom.org/translations/in ... an-english;
...damn this format is evil. The Dude will now be recuperating from Star Ocean-induced injuries.

I love you (no homo). I have Valkyrie Profile 2. I can test your maxscript out on that game since it's the same developer. I'm expecting it to fail, but I'll report back results after I give it a shot.
## Post #12
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-01-07T02:57:40+00:00
- Post Title: Star Ocean 3 models?

> Reply from soneek
>
> TheDude wrote:Well to paraphrase Dark Force over at http://superfamicom.org/translations/in ... an-english;
...damn this format is evil. The Dude will now be recuperating from Star Ocean-induced injuries.


I love you (no homo). I have Valkyrie Profile 2. I can test your maxscript out on that game since it's the same developer. I'm expecting it to fail, but I'll report back results after I give it a shot.

I only looked at one file from VP2 (Lenneth), but the format was exactly the same. I tested a few Radiata Stories models as well, and they mostly worked. The RS models are more dependent on the skeleton than SO3 so don't expect people to always be in one piece.
## Post #13
- Username: soneek
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Oct 20, 2011 5:43 am
- Post datetime: 2013-01-07T11:26:44+00:00
- Post Title: Star Ocean 3 models?

> Reply from TheDude
>
> 
I only looked at one file from VP2 (Lenneth), but the format was exactly the same.

Do you remember which file it was for Lenneth's model?
## Post #14
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-01-07T15:37:54+00:00
- Post Title: Star Ocean 3 models?

You'll have to ask Satoh; I don't remember what he sent me.
## Post #15
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2013-01-07T15:59:04+00:00
- Post Title: Star Ocean 3 models?

So you got some of the RS models to work, How? I've tried to extract models from the kod, pk3 and slz using the quickbms scripts you posted and I only get errors or empty files.
## Post #16
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-01-07T19:57:11+00:00
- Post Title: Re: Star Ocean 3 models?

Ha-ha! I'm such a hoser. Delete the first line in kod.bms.
I don't know how that got in there.
## Post #17
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2013-01-07T23:15:13+00:00
- Post Title: Re: Star Ocean 3 models?

Thanks, but now I'm getting this warning when I load the Raw0 models in Max 2010



The models load, but as soon as I get this message



the models are deleted.
## Post #18
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-01-08T01:30:08+00:00
- Post Title: Re: Star Ocean 3 models?

I don't recall seeing the first message when I was testing it.
Just check "do not show again" followed by "yes".

As far as the second message goes, the importer works abput 80% of the time.
There're too many variations in the data and I gave up trying to make it work on everything.
Only thing I can say is keep trying different files. Character files stand a much better chance of working.
Maybe in the 100-400KB range. The larger files are more than likely things like outside environments, building etc.
Except with SO3. Some of the character files are around 1.6MB because they contain the character animations as well.
And good luck looking for a specific character: 
With Rumina from Star Ocean 3, her name in the file is "OJYOH000" 
Assuming little endian byte order it would be HOYJO. Possibly her Japanese name.
Even assuming you know the character's Japanese name, a lot of the names are abbreviated in strange ways.
## Post #19
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-01-20T02:10:23+00:00
- Post Title: Re: Star Ocean 3 models?

Aren't star ocean 3 files hidden on the disc?
## Post #20
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-01-20T18:44:06+00:00
- Post Title: Re: Star Ocean 3 models?

> Reply from ShinKun
>
> Aren't star ocean 3 files hidden on the disc?
Depends what you mean by "hidden". Data is data regardless of how it's stored.
You just need the right tools to extract it......like the one's in the link on the previous page.
## Post #21
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2013-04-24T05:22:15+00:00
- Post Title: Re: Star Ocean 3 models?

> Reply from TheDude
>
> I don't recall seeing the first message when I was testing it.
Just check "do not show again" followed by "yes".

As far as the second message goes, the importer works abput 80% of the time.
There're too many variations in the data and I gave up trying to make it work on everything.
Only thing I can say is keep trying different files. Character files stand a much better chance of working.
Maybe in the 100-400KB range. The larger files are more than likely things like outside environments, building etc.
Except with SO3. Some of the character files are around 1.6MB because they contain the character animations as well.
And good luck looking for a specific character: 
With Rumina from Star Ocean 3, her name in the file is "OJYOH000" 
Assuming little endian byte order it would be HOYJO. Possibly her Japanese name.
Even assuming you know the character's Japanese name, a lot of the names are abbreviated in strange ways.

Mostly correct Dude, but in fact the actor names (OJYOH000 and such) are in plain text order... which I suppose is big endian. Ojyoh (or Ojou) is a word meaning roughly "daughter" (Or possibly princess, I forget) This is an appropriate name for an NPC of moderate importance... more than a random maid, less than the final boss. 
Truly random NPCs tend to have random(seemingly) letter strings (3 letters, underscore, letter, underscore, letter or number: npE_a_e_f003 as a random example of format)
PC map characters sometimes follow this format as well... Some models have not been found (by me anyway, despite much MUCH searching, and unarchiving many different forms of packages... why TriAce needed more than one archive format I have no clue...) Luther's out of battle model remains unfound, yet he has three separate models for the three times he appears in battle (these cannot be imported correctly at this time, missing parts...much to my chagrin)
Lenneth has not been found, Freya on the other hand, has. (And has not imported correctly for me yet) 

Fayt's name is FATE, Peppita's is SOUFLE (one F as I recall) Clair is Crea, Blair is BUREA. You'll have to go full-on engrish if you want to get the best shot at finding SO3 models. 

Enemies almost always use the 3 letter sequence format explained above. There are many MANY copies of the same enemy (presumably with different textures) and a few different resolutions for story centric characters. (Some animated textures for faces, some with lowpoly face animation, some with higher poly facial animation) 

Character battle models, particularly in relation to the different outfits that are wearable, each have unique UVs, so you cannot dump the model for one outfit and expect the textures for the others to work simply as palette swaps. Even thought the geometry is the same, the textures are laid out differently, for whatever reason. Dump each outfit individually.
## Post #22
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-04-24T17:07:21+00:00
- Post Title: Re: Star Ocean 3 models?

I humbly bow to you in light of your great wisdom oh guru of rpgs.
## Post #23
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2013-07-06T11:19:22+00:00
- Post Title: Re: Star Ocean 3 models?

I try it out, It is such a butt hurt, wonder anyone use emulator and rip it with ripper?
## Post #24
- Username: headgehof
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jun 27, 2010 10:11 pm
- Post datetime: 2013-07-06T16:21:41+00:00
- Post Title: Re: Star Ocean 3 models?

please re upload utilities and importer
## Post #25
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2014-09-15T10:14:58+00:00
- Post Title: Re: Star Ocean 3 models?

> Reply from TheDude
>
> Well to paraphrase Dark Force over at http://superfamicom.org/translations/in ... an-english;
...damn this format is evil. The Dude will now be recuperating from Star Ocean-induced injuries.

Here's the utilities and importer: http://www.mediafire.com/?dnc6jy3f32k32bw

can't download, I want it.
## Post #26
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-15T11:39:04+00:00
- Post Title: Re: Star Ocean 3 models?

I don't exactly remember what was uploaded, but I think this might be it?
[https://www.dropbox.com/s/sywjebskds0da ... s.zip?dl=0](https://www.dropbox.com/s/sywjebskds0dagz/TA%20utilities.zip?dl=0)
## Post #27
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2014-09-15T13:48:16+00:00
- Post Title: Re: Star Ocean 3 models?

> Reply from o0DemonBoy0o
>
> I don't exactly remember what was uploaded, but I think this might be it?
https://www.dropbox.com/s/sywjebskds0da ... s.zip?dl=0
I need use proxy, can rip texture?

Edit:  I imported so3 model, but vp2 model can't, sad.
## Post #28
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2014-09-30T21:30:57+00:00
- Post Title: Re: Star Ocean 3 models?

Sorry. That importer I made is a decroded piece of crap!



Anywho, for the 10 year anniversary I wanted to do a little somthin'-somethin':  [https://app.box.com/s/57ict0yenx1b0r3kgk5g](https://app.box.com/s/57ict0yenx1b0r3kgk5g)



EDIT: fixed links on first page
## Post #29
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-01T06:14:33+00:00
- Post Title: Re: Star Ocean 3 models?


