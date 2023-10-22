## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-14T22:42:04+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

Hey Guys,

right now, I'm able to edit two Nintendo 3DS Games almost completely (after I got a repacker for [xbb-files, pp-files](http://forum.xentax.com/viewtopic.php?f=21&t=12649) and [darc-files](http://forum.xentax.com/viewtopic.php?f=10&t=12660)) because the Scripts and Codes are in PlainText and easily editable.

But now, I want to edit / add new Models to the Game, but the good known ["EveryFileExplorer"-Tool](https://gbatemp.net/threads/release-every-file-explorer.373615/) is not able to export and reimport the models completely/correctly.

i can export the models and textures and open them with Blender, but it seems that the "Material Animation" of the bcmdl-file is not exported, too.
This means: When I try to recreate a bcmdl-file, there are no "Material Animations" and some Textures are missing/have wrong names.

Here's a Sreenshot how the original Model and the reimported one looks:
[https://puu.sh/gAmq1/f4dead5e55.png](https://puu.sh/gAmq1/f4dead5e55.png)
The Material-Animation is missing and some Textures are missing.

When I try to import this new created bcmdl-file to the game, the Game will crash.

I can open the exported model with Blender:
[http://puu.sh/gAqij/6860feb5f9.png](http://puu.sh/gAqij/6860feb5f9.png)


I've uploaded the bcmdl-file and the exported obj-file.
[http://puu.sh/gAqsf/258ef7a4d6.rar](http://puu.sh/gAqsf/258ef7a4d6.rar)


It would be great if you can help me with this Problem. 
I want to create a new/modified model with modified Textures and the missing Material_Animation.
Please help me with this x_x
## Post #2
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-15T20:44:43+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

/push :/
## Post #3
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-17T09:31:38+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

/bump
## Post #4
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-19T12:26:34+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

/bump^
## Post #5
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-22T10:17:53+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

/bump³
## Post #6
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-24T15:20:00+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

/bump²³
## Post #7
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-04-02T19:35:56+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

/push it to the top because i need this
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-04-03T10:47:37+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

Can't you just wait for Every File Explorer to add this functionality?
## Post #9
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-04-03T11:18:33+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

I opened this thread because the creator of EveryFileExplorer is very busy and I don't want to wait 6months or more ._. I just want to modify a game where I was already able to rewrite the scripts/codes and to add new Events.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-03T12:27:33+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

> Reply from ChrisX930
>
> , but it seems that the "Material Animation" of the bcmdl-file is not exported, too.on obj export
only these two materials are exported: Body_718 and lam_face_000

But seems there are 4 textures "bound" to the body-material.
Do you have any information "how this is done" by the bcmdl format?
It's not a "simple" multitexture feature, I guess.
I can see overlapping uvs used by the body textures
 (to create a coloured blinking dragon on the shirt? While in the textures it's a small coloured rectangle only).

Is there any model without "Material Animation"?
If so I would try out to re-import such a model first.
## Post #11
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-04-03T12:49:28+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

Heya 

> But seems there are 4 textures "bound" to the body-material.
>
> Do you have any information "how this is done" by the bcmdl format?
Sorry, I don't know how this was done .__.

> I can see overlapping uvs which are probably used by 3 of the body textures to create a coloured blinking dragon on the shirt
I don't think that the dragon on the shirt should blink ingame. I guess the "Player" should be able to switch between the colors ingame (in shop, not in character creation).
All character models have Material-Animations and especially these character-models are this, which I want to add/edit.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-03T12:54:03+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

> Reply from ChrisX930
>
> Sorry, I don't know how this was done .__.too bad.

> All character models have Material-Animations and especially these character-models are this, which I want to add/edit.Then there's  only little chance to solve it in the next 6 months.  

What I could think of is comparing the re-created bcmdl file with the original one and see if one could fix it manually.
## Post #13
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-04-03T12:59:26+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

Yea, possible but weird :/

I guess I uploaded both of them (the original one and the recreated one).

Otherwise if you need some more Files to make something out of it, I could upload them.
Just tell me what I should do. (I don't really know some specific things about file formats, I just know how to edit them with the given tools (3dsmax, notepad++ or whatever))
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-03T13:07:41+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

what I meant was a recreated bcmdl file, not the obj.

What I can create is a bcres file but it's only half the size of the original bcmdl.
So that won't help, I guess.

(For some strange reason I can't save the original bcmdl as bcres.)
## Post #15
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-04-03T13:18:25+00:00
- Post Title: Nintendo 3DS - BCMDL-File Format

> Reply from shakotay2
>
> 
What I can create is a bcres file but it's only half the size of the original bcmdl.
So that won't help, I guess.
I guess it's because some textures and the mat-animation is missing.
I think you can rename the bcres to bcmdl. In HEX, they've the same Header
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-03T14:35:40+00:00
- Post Title: Re: Nintendo 3DS - BCMDL-File Format

well, that was too obvious to be seen by me, hahaha..  

But comparing these two bcmdl files is not as easy as I thought.
For example "DICT" is contained 10 times in b_718.bcmdl versa 4 times in the exported bcmdl/bcres.

If I had more time I would try to add a bcmdl format logger to the Every File Explorer project, but sadly
I've my own projects to care for.
## Post #17
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-04-03T14:43:58+00:00
- Post Title: Re: Nintendo 3DS - BCMDL-File Format

uhhhmmm would be cvool if you could look into it anyways 
I'm not sure but I think "DICT" could be "directory" or the path of each file. the unmodded bcmdl-file should have 10 of them and the reexported one obviously have less than 10 because there are some files missing
## Post #18
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-10-24T09:54:15+00:00
- Post Title: Re: Nintendo 3DS - BCMDL-File Format

/push :/
Still need help with this...
here's another file I want to edit/replace
[PC05.zip](https://xentaxbackup.github.io/file/9911_PC05.zip)
