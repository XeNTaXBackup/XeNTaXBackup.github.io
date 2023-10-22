## Post #1
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-11-19T22:15:26+00:00
- Post Title: Beatles Rockband .dat files help needed

Hi, with the help of user GHFear on Zenhax he provided me with an offzip, tool that allowed a ".milo_ps3" file from the Beatles Rockband for PS3 game to extracted to a "sample.dat" and when I unpacked it I was given the following files:



Now I am not sure where to proceed from here. GHFear said someone can probably make a Noesis script to see what exactly these files are. I really hope something comes out of this,it's been too long since The Beatles have not been ripped from the game but other games keep getting attention.

Here's the sample files at the bottom. For anyone curious I took the "budokan01.milo_ps3" file from George Harrison's folder in general body and got this.

I'm honestly willing to pay for this game to be cracked at this point.

[https://www.mediafire.com/file/fhyhlc3l ... t.rar/file](https://www.mediafire.com/file/fhyhlc3lxraaov0/George_Sample_Dat.rar/file)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-20T03:56:21+00:00
- Post Title: Beatles Rockband .dat files help needed

You'll need to correctly unpack the archive first. 

Anyway there's at least geo and/or texture data in these files.

(00060eb0.dat)



00060eb0.dat_torso.png (99.47 KiB) Viewed 302 times



(0003b9b8.dat)


(Wrapping data of 000121cd.dat from offset 110 in PVRTexTool)
## Post #3
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-11-20T13:53:16+00:00
- Post Title: Beatles Rockband .dat files help needed

> Reply from Bigchillghost ↑Wed Nov 20, 2019 11:56 am at Wed Nov 20, 2019 11:56 am
>
> 
You'll need to correctly unpack the archive first. 

Anyway there's at least geo and/or texture data in these files.

(00060eb0.dat)
00060eb0.dat_torso.png

(0003b9b8.dat)


(Wrapping data of 000121cd.dat from offset 110 in PVRTexTool)

Thank you sooooooooo much for taking the time to look into this finally!

 You said unpack the archive, I have little experience with this unfortunately. Can you specify what exactly I should do or have to do to go about that here?
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-20T14:38:13+00:00
- Post Title: Beatles Rockband .dat files help needed

> Reply from Assasinge ↑Wed Nov 20, 2019 9:53 pm at Wed Nov 20, 2019 9:53 pm
>
> 
Thank you sooooooooo much for taking the time to look into this finally!
"Finally"? You just posted this today, didn't you?

> Reply from Assasinge ↑Wed Nov 20, 2019 9:53 pm at Wed Nov 20, 2019 9:53 pm
>
> 
Can you specify what exactly I should do or have to do to go about that here?
You'll have to wait for someone to write an unpacking script/tool unless you're capable of doing it on your own.
## Post #5
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-11-20T14:48:46+00:00
- Post Title: Beatles Rockband .dat files help needed

> Reply from Bigchillghost ↑Wed Nov 20, 2019 10:38 pm at Wed Nov 20, 2019 10:38 pm
>
> 
Assasinge wrote: ↑Wed Nov 20, 2019 9:53 pm
Thank you sooooooooo much for taking the time to look into this finally!
"Finally"? You just posted this today, didn't you?
Assasinge wrote: ↑Wed Nov 20, 2019 9:53 pm
Can you specify what exactly I should do or have to do to go about that here?

You'll have to wait for someone to write an unpacking script/tool unless you're capable of doing it on your own.

Well by finally I meant that it's been years since anyone bothered to look into this game and you're the first one to actually look into it and view these meshes and such. I'm just surprised no one has been interested in ripping the Beatles themselves all this time but will rip stuff from other games. I guess there aren't as many fans as I thought there were left of the Beatles today.

And I see. Well I am not capable of writing some sort of script unfortunately, I guess I will have to wait then.
## Post #6
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-11-21T15:01:10+00:00
- Post Title: Beatles Rockband .dat files help needed

About a year ago, I wrote some rudimentary tools to unzip the archive and get model and textures (not user friendly):
[https://github.com/HENDRIX-ZT2/rockband-tools](https://github.com/HENDRIX-ZT2/rockband-tools)
## Post #7
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-11-21T15:13:14+00:00
- Post Title: Beatles Rockband .dat files help needed

> Reply from DMZT2 ↑Thu Nov 21, 2019 11:01 pm at Thu Nov 21, 2019 11:01 pm
>
> 
About a year ago, I wrote some rudimentary tools to unzip the archive and get model and textures (not user friendly):
https://github.com/HENDRIX-ZT2/rockband-tools

Hey thanks for the reply! If I'm correct, I should run these python scripts in Blender? However you said it's not user friendly but that's fine with me. Could you briefly explain what I should do with this after I have opened these in Blender? I'm on Blender 2.79 btw.

Edit: Script returns an error in Blender.
## Post #8
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-11-21T15:31:20+00:00
- Post Title: Beatles Rockband .dat files help needed

See the lines at the end of each script. They define which archive or model is supposed to be read.
Yeah mesh.py is a plugin for blender 2.79.
## Post #9
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-11-21T15:35:14+00:00
- Post Title: Beatles Rockband .dat files help needed

Ah I see, it appears I didn't set the filepath. So I assume the mesh.py is to import a mesh of some sort, but I don't have that yet. What do I do with the milo.py, run the script on any .milo_ps3 file and see what it outputs? Sorry if I'm asking too much, I don't use Blender as much as Max.
## Post #10
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-11-21T15:43:58+00:00
- Post Title: Beatles Rockband .dat files help needed

Yeah, first you'll need to run milo.py on a milo file.
## Post #11
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-11-21T17:00:40+00:00
- Post Title: Beatles Rockband .dat files help needed

Alright I'm trying to do that but I'm running into this error here: 



One thing I noticed is that the original py file had a .milo_ps2, this is a ps3 file. That may be why this isn't working...
## Post #12
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-11-21T17:03:35+00:00
- Post Title: Beatles Rockband .dat files help needed

Use forward slashes in your path.
## Post #13
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-11-21T17:08:33+00:00
- Post Title: Beatles Rockband .dat files help needed

Well that was dumb of me. But... it's still acting all screwy! Now I got this:
## Post #14
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-11-21T18:28:22+00:00
- Post Title: Beatles Rockband .dat files help needed

Same screenshot?
## Post #15
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-11-21T18:30:28+00:00
- Post Title: Beatles Rockband .dat files help needed

Whoops, I updated the image.
## Post #16
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-11-21T20:10:00+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

Sounds like your file path is wrong...?
## Post #17
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-11-21T22:40:20+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

Hm, I don't know if that's the problem.

This is my current edit of your script:



Now there's 2 "read_milos", I'm not sure why or what that entails but I put the filepaths to the milo I have in both of them. Upon running the script it points to line 197 as an error and then line 19 as well. Your original unedited script simply had the name of the milo file at the very very bottom, and then a second ps2 milo file above it somewhere as well. I simply tried to follow similar formatting the first time and got errors. There's also some png_wii thing, I'm not sure if this is a texture thing or not from the looks of it but I left it alone. Other than that, I'm not well versed in Python so I don't know if I'm overlooking something simple here or not.
## Post #18
- Username: Sorashiba
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 13, 2022 4:56 am
- Post datetime: 2022-01-13T10:16:18+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

I got these dat files too, can anyone help me with opening them in Advanced Mesh Reaper?
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-13T12:00:40+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

@Sorashiba: Bigchillghost already showed how to do it 2 years ago, so what? (klick up arrow)

> Reply from Bigchillghost ↑Wed Nov 20, 2019 11:56 am at Wed Nov 20, 2019 11:56 am
>
> 
.
I'm more familiar with my own tool (but sooner or later I hope to implement a json parameter exporter for AMR  )
.



3b9b8-dat.png (88.91 KiB) Viewed 166 times
## Post #20
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-13T12:50:06+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

Actually these models have already been ripped here:

[https://www.deviantart.com/fuckyeahkimb ... ckband-ps3](https://www.deviantart.com/fuckyeahkimbra/gallery/72165524/the-beatles-rockband-ps3)

Problem is they're not 100% good rip and lack a skeleton. There hasn't been any way to properly extract these models despite Turk's script there unfortunately.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-13T13:32:13+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

> Reply from Assasinge ↑Thu Jan 13, 2022 8:50 pm at Thu Jan 13, 2022 8:50 pm
>
> 
Actually these models have already been ripped here:

https://www.deviantart.com/fuckyeahkimb ... ckband-ps3

Problem is they're not 100% good ripWhat do you mean exactly? I can't seem to find a problem here:
.



smooth.png (167.76 KiB) Viewed 152 times

(increased face indices count to 6288)
## Post #22
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-13T13:48:14+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

for their heads, all the eyeballs and eyelashes were manually placed by hand. If you import a milo into Blender using the original script, you'll find that initially some of the Beatles's eyeballs, eyelashes or eyebrows are in incorrect positions and need to be placed manually, I did all that work by hand for these models. The outfits themselves are fine, it's mainly the heads that are problematic.
## Post #23
- Username: Sorashiba
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 13, 2022 4:56 am
- Post datetime: 2022-01-13T20:43:03+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

Crazy thing that everyone knows how to view these dats while I am a total noob about it lol
## Post #24
- Username: Sorashiba
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 13, 2022 4:56 am
- Post datetime: 2022-01-13T20:46:19+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

I think it may be that I dont really understand Hex
## Post #25
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-01-13T21:24:55+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

Don't worry, I don't know anything. That script wasn't even written by me, it was a guy named Turk or something on the Xentax discord lol.
## Post #26
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-07-11T22:30:48+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

I'd like to bump this topic actually, wondering if anyone still has interest in a proper extraction of TBRB? The current script for extracting its contents is incomplete and a bit jank, would be super appreciated if anyone would like to help get proper tools for this game so we can get the models with proper weights and positions etc.

Willing to pay for this as well.
## Post #27
- Username: xentax3dmodels
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 16, 2022 5:10 pm
- Post datetime: 2022-07-16T09:13:16+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

Hi, I currently took a tutorial yesterday on extracting models with Hex and I think I got a pretty good base (I hope) when I get a PC I will try to build a Noesis tool for TBRB milo ps3 files to be opened (I cant go as far as animations sadly) but maybe we can get some stuff out Turks script cant (no offense) and I hope you will understand if I wont be able to do it cause of an issue, but I will try for you

Update: Mine I dont think will be able to have bones, uvs, or anims, but I think it should still pull out more than turks, so if you dont mind rigging and all that stuff then ill gladly try to do it
## Post #28
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-07-16T18:48:40+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

> Reply from xentax3dmodels ↑Sat Jul 16, 2022 5:13 pm at Sat Jul 16, 2022 5:13 pm
>
> 
Hi, I currently took a tutorial yesterday on extracting models with Hex and I think I got a pretty good base (I hope) when I get a PC I will try to build a Noesis tool for TBRB milo ps3 files to be opened (I cant go as far as animations sadly) but maybe we can get some stuff out Turks script cant (no offense) and I hope you will understand if I wont be able to do it cause of an issue, but I will try for you

Update: Mine I dont think will be able to have bones, uvs, or anims, but I think it should still pull out more than turks, so if you dont mind rigging and all that stuff then ill gladly try to do it

Well I'd still like to try get the rigs but if not possible currently then that's okay. No UVs though? Hm I don't know. Can we talk on discord?
## Post #29
- Username: xentax3dmodels
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 16, 2022 5:10 pm
- Post datetime: 2022-07-17T09:17:33+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

yeah dude
## Post #30
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-07-18T15:03:03+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

> Reply from xentax3dmodels ↑Sun Jul 17, 2022 5:17 pm at Sun Jul 17, 2022 5:17 pm
>
> 
yeah dude

Sent you a pm
## Post #31
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-02-21T15:16:37+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

> Reply from andreen ↑Tue Feb 21, 2023 3:26 pm at Tue Feb 21, 2023 3:26 pm
>
> 
Thanks for sharing them, even though you always deny the problem   

ovo game

What is this supposed to mean?
## Post #32
- Username: breh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 17, 2023 2:39 am
- Post datetime: 2023-09-16T18:42:17+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

Hey, so I thought I would share that there is a new tool out that can rip a lot of The Beatles: Rock Band models (some venues) with the skeletons, but not weights. If you're interested, should I send you a message on Discord?
## Post #33
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-09-16T20:08:54+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

> Reply from breh ↑Sun Sep 17, 2023 2:42 am at Sun Sep 17, 2023 2:42 am
>
> 
Hey, so I thought I would share that there is a new tool out that can rip a lot of The Beatles: Rock Band models (some venues) with the skeletons, but not weights. If you're interested, should I send you a message on Discord?

You could if you want, sure. Though I don't see the point of having the skeletons of the meshes without the weights if you ask me but, still a cool development nonetheless. My discord name is the same as it is here.
## Post #34
- Username: breh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 17, 2023 2:39 am
- Post datetime: 2023-09-16T20:36:12+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

Alright, I'll shoot you a message.
## Post #35
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2023-09-20T17:26:31+00:00
- Post Title: Re: Beatles Rockband .dat files help needed

> Reply from breh ↑Sun Sep 17, 2023 4:36 am at Sun Sep 17, 2023 4:36 am
>
> 
Alright, I'll shoot you a message.
Feel free to send me an invite, discord handle _hendrix_
