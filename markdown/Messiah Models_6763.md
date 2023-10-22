## Post #1
- Username: CyberDemon5150
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2011 9:58 pm
- Post datetime: 2011-06-10T19:06:55+00:00
- Post Title: Messiah Models

Game: Messiah
Developer: Team Ego (under Shiny Entertainment)
Year: 2000
Uses Direct3D 7 or 3DFX Glide 3

I've been having a bit of trouble getting a hold of the models in this game. They seem to be proprietary, and each model folder contains a .dcr file, a .000MAX file, and a .001-.006/.008 file. Some also have a .000MIN file, but this file seems to have less importance than the .000MAX. 

I've done a bit of experimenting, and while it hasn't resulted in me finding a solution, here are my findings:

-.dcr files appear to be the actual model. Swapping these but not the .000MAX results in the skin of the character being replaced getting stretched over the model of the character you intended to replace them with.
-.000MAX files appear to be the skin for the model. Note that .000MAX files come in either 389 kb or 454 kb form. These sizes are not interchangeable between models, and swapping them with odd models (IE, replacing a 389 witha 454 or vice-versa) will cause a crash when the character is rendered.
-.001 thru .008 files appear to have no significance, removing them from the folder seems to make no difference... But they have to be there for a reason...

I have yet to find a program which will convert .dcr to a more useful format, so instead I made several attempts to rip the models directly from the game as they were rendered, utilizing such programs as 3D Ripper DX and Game Assassin. Unsurprisingly, 3D Ripper DX did absolutely nothing, as it is advertised as only working for DirectX 6, 8, and 9. GameAssassin failed to do anything as well. So now I'm turning to the people of the Internet for help with this matter. Has anybody else performed any experiments involving the ripping of models from Messiah?
## Post #2
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2011-09-21T19:52:18+00:00
- Post Title: Messiah Models

000, 001, etc. - this is textures in TGA format - copy, change extension and see them (or use viewer like ACDSee with image format autodetection).
My best progress with this game is launch with [Glide Wrapper](http://www.zeus-software.com/downloads/nglide) and got "Ready to capture" message.
But captured scene do not contains any polygons. Also, captured textures have strange pallete and low resolution (glide restriction).
3DVIA PrintScreen didn't work with d3d version too.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-09-28T08:32:36+00:00
- Post Title: Messiah Models

I looked at the DCR file format really quick and it seems like a super easy format. Look at subgirl1, at offset 0xF9B0, that's an obvious index buffer. Look at ammog, the smallest model file, and that file seems pretty obvious to me too... points, index buffer, etc. If you know a little C++ or maxscript, and have a little patience, those models are as good as yours. I've got my hands full at the moment with neptunia and black rock shooter, but maybe one of the other guys can do it.
## Post #4
- Username: CyberDemon5150
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2011 9:58 pm
- Post datetime: 2011-10-10T05:33:04+00:00
- Post Title: Messiah Models

@Andrakann, thanks for your contributions. I did not know that the extensions could simply be changed to allow the opening of the numbered files. Very handy information.

@howfie, I have been learning C++ over the past few months, but I'm not sure how I could use what I know to turn them into a usable format. Does it involve coding a plugin so that a common model editor can import the model? If so, may it be possible to write a Blender script with Python? I don't know any Python myself, unfortunately, but in any case, I don't know how to write an import/export plugin in any language.

I don't know, is anybody out there a bad enough dude to help me out with this? 
I can upload one or two of the model files to help you get a feel for the model format if any of you want give this a try. Alternatively, if anyone could point me to some instructions for doing this for myself, that would be great.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-17T15:54:43+00:00
- Post Title: Messiah Models

i looked at it more thoroughly this time. vertex data appears to be encrypted or masked (integer-based). i tried to find different kinds of floats at all possible file positions and it was a no go every time. this game is pre-half-float era too so not that either. it really would take a bad enough dude (or a lucky one) to figure this one out. since it's such an old game, best bet would be to find one of the original developers and asking him.
## Post #6
- Username: CyberDemon5150
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2011 9:58 pm
- Post datetime: 2011-10-20T18:48:26+00:00
- Post Title: Messiah Models

Ah, alrighty, thanks for taking a look!

I've already tried contacting the team before, but the only one I could successfully contact was the character designer. He didn't have many answers as to the tech side of things, of course, and the actual people responsible for the engine and any custom model formats they created for his models were non-responsive.

The designer said he was pretty sure he still had the original un-encrypted 100,000-400,000 poly models on disc somewhere, and that he'd take a look for them, but this was back at the very beginning of the year, so I'm beginning to think that deciphering this model format is the only way (even if the intercepted models aren't nearly as high-quality as the originals.)

Also, I don't know if this helps things, but he said that a special tool developed by one of the devs converted these ordinary Max models into "Non Uniform Rational B splines".
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-28T07:39:48+00:00
- Post Title: Messiah Models

I looked at it again a few weeks ago and was able to extract some of the weapons, but not all. Simple weapons use normalized signed short vertex buffers. Other weapons and characters use some other vertex format... haven't been able to figure it out yet. Funny shit... this model is in the weapons directory but it looks like an origami dog ruff ruff ruff ruff he he he.
## Post #8
- Username: CyberDemon5150
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2011 9:58 pm
- Post datetime: 2011-11-11T01:58:16+00:00
- Post Title: Messiah Models

Haha, great work! Actually, I don't remember seeing that model at all in-game... Maybe they realized how silly it looked and decided not to actually implement it, but forgot to cut it from the game files.
## Post #9
- Username: CyberDemon5150
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 08, 2011 9:58 pm
- Post datetime: 2011-12-28T07:40:23+00:00
- Post Title: Messiah Models

Update: I found out a bit more about the model format myself (nothing technical, unfortunately, but information nonetheless.)

Indeed, the .001-.006 files are .TGA skin files, but I recently found the function of the .000MIN, .000MAX, and .000MED files. They're texture mapper files, generated by the game each time you change character skin detail levels.
Perhaps this was obvious to some, but being me, I was completely overthinking it and assuming they had something to do with the model data. Turns out the model is, fortunately, just the .dcr file. Of course, finding a way to map the existing textures to the model, if the format is deciphered, will probably be a bit of a pain.
## Post #10
- Username: Andrakann
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2017-05-20T16:02:47+00:00
- Post Title: Messiah Models

> Reply from howfie
>
> i looked at it more thoroughly this time. vertex data appears to be encrypted or masked (integer-based). i tried to find different kinds of floats at all possible file positions and it was a no go every time. this game is pre-half-float era too so not that either. it really would take a bad enough dude (or a lucky one) to figure this one out. since it's such an old game, best bet would be to find one of the original developers and asking him.
Oh, howfie, to think you were so young once. The years have passed us by, and we are old men now, still toiling away on esoteric problems in obscurity. Yet, I feel as though I may be...through some ontological calling, a bad dude.

I happened to snag this one on a bounty earlier this week. Because the guy offering the bounty is offering it to have the format and specs opened up to the community, as he isn't a massive dickchugger like everyone who's ever offered a "bounty" here. That means Messiah will be supported in the next build of Noesis, and loader code will be forthcoming.

Also, yeah, this was a little terrible as formats go. Nowhere approaching something like Bujingai, of course, but still a little terrible.
## Post #11
- Username: Spellca
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 22, 2011 10:39 am
- Post datetime: 2022-10-09T02:16:04+00:00
- Post Title: Messiah Models

> Reply from MrAdults ↑Sun May 21, 2017 12:02 am at Sun May 21, 2017 12:02 am
>
> 
howfie wrote:i looked at it more thoroughly this time. vertex data appears to be encrypted or masked (integer-based). i tried to find different kinds of floats at all possible file positions and it was a no go every time. this game is pre-half-float era too so not that either. it really would take a bad enough dude (or a lucky one) to figure this one out. since it's such an old game, best bet would be to find one of the original developers and asking him.
Oh, howfie, to think you were so young once. The years have passed us by, and we are old men now, still toiling away on esoteric problems in obscurity. Yet, I feel as though I may be...through some ontological calling, a bad dude.

I happened to snag this one on a bounty earlier this week. Because the guy offering the bounty is offering it to have the format and specs opened up to the community, as he isn't a massive dickchugger like everyone who's ever offered a "bounty" here. That means Messiah will be supported in the next build of Noesis, and loader code will be forthcoming.

Also, yeah, this was a little terrible as formats go. Nowhere approaching something like Bujingai, of course, but still a little terrible.
Do you still have this model? I have always wanted to examine some of the models in this game
