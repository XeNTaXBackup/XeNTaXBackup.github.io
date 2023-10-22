## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-20T15:24:42+00:00
- Post Title: Parasite Eve (PS1)

Parasite Eve (PS1) tools.

1. extract game packages from PE.IMG
Just run Parasite_img.exe in the folder with PE.IMG, also exedata.bin provided must be there. This table from game executable tell the tool about package offsets.

2. drop any package onto Parasite_assets.exe (or run on all them in batch)
This will extract all assets from the package. Each package may have 12 types of assets. All of them will be extracted to corresponding folders without names, just sequential numbers. Models are type 2. I dont have time to research about asset codes and other types.

3. drop model file onto Parasite_model.exe (obsolete)
This will produce 2 files: model in SMD format and a 2-frame animation SMD which will set lenghts for all bones. Apply animation SMD to the model and move to frame 2 to make it work. After that you only need to rotate bones to more natural position to make model look better.

Video showing how it can be done on the example of Silent hill - [https://www.youtube.com/watch?v=6Gq0rtpjEY0](https://www.youtube.com/watch?v=6Gq0rtpjEY0)




[parasite_eve1.rar](https://xentaxbackup.github.io/file/19246_parasite_eve1.rar)
## Post #2
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2020-12-20T16:08:00+00:00
- Post Title: Parasite Eve (PS1)

Great Work deamon1!

Parasite Eve are one of my Fav games ^^

any chance that you can take a look at thee second game ?
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-21T16:18:43+00:00
- Post Title: Parasite Eve (PS1)

> Reply from The Chief ↑Mon Dec 21, 2020 12:08 am at Mon Dec 21, 2020 12:08 am
>
> 
any chance that you can take a look at thee second game ?
Second game was already done by someone like 4 years ago
## Post #4
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2020-12-23T08:16:06+00:00
- Post Title: Parasite Eve (PS1)

I was researching about Parasite Eve 2 Models and i ended with a bunch of files .pe2img .pe2clut .pe2pkg and the models where supposed to be inside the .pe2pkg files but in words of the guy who made the blender script:

"those scripts are NOT end-user friendly and require a lot of additional steps of extracting the models (and animations) from *.pe2pkg files manually with HEX editor"

In a few words i wasn't able to extract models from those files. 
I have samples if you want.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-23T09:32:11+00:00
- Post Title: Parasite Eve (PS1)

> Reply from Casedey ↑Wed Dec 23, 2020 4:16 pm at Wed Dec 23, 2020 4:16 pm
>
> 
In a few words i wasn't able to extract models from those files. 
I have samples if you want.
no, i have samples
maybe i check this later.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-23T13:51:02+00:00
- Post Title: Parasite Eve (PS1)

Model tool updated.

It will now assign materials according to image index used. Must allow to texture complex models that are using multiple textures.

The only problem remains that some faces are not textured, instead they are filled with solid colors. I could export that in another format, but SMD doesnt support it. Maybe later.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-24T16:52:06+00:00
- Post Title: Parasite Eve (PS1)

Getting backgrounds now. I think its the last option planned, and then i can move to PE2.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-25T16:17:59+00:00
- Post Title: Parasite Eve (PS1)

This picture was taken from one of her animations, which are also extractable. It allows to finally get characters in proper poses.

A couple of animation examples. They are either 8-bit or 12-bit. This one is smooth:

[https://www.youtube.com/watch?v=a_lDoNomxRY](https://www.youtube.com/watch?v=a_lDoNomxRY)

And this one "i'm gonna show you my badge" if you remember, is 8-bit, and its shaky, as it was in game:

[https://www.youtube.com/watch?v=pnnAxBxIYTg](https://www.youtube.com/watch?v=pnnAxBxIYTg)
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-27T08:54:52+00:00
- Post Title: Parasite Eve (PS1)

Backgrounds tool added. The way it works on PS1 is kind of complicated, so i'm not going to fully export all the data. Here's how it works:

you need 3 files to provide for it:
1 - background (from folder 6)
2 - palette (from folder 9), this file is usually first palette, and its size is the biggest, 16384 (other palettes will be smaller, they are for models)
3 - memory.dat file from the root of the folder
(you need to re-unpack assets from room packages with updated Parasite_assets.exe)

Once you run it like 
 Parasite_bg.exe <background> <palette> <memory.dat>

it will make a "tex" folder with all layers, and a few combined images, which are final backgrounds. Most of the time there are 1, 2 or 3 of them: one big background and 1 or 2 closeups. Some layers may exceed final background size, and i decided to export them with those oversized parts, so you can see them too. Tool will also make a list of which layers are animated and how.

Some backgrounds are using PS1 semi-transparent modes. About 8 of them have "normal" transparency, like the one with police car ride. About 6 with darkening (shadows), like menus with help. And only 1 most special with 2 types, which is magic carriage ride. That one has both a shadow and semi-transparent flame ahead of carriage. 

Technically i could get all these transparency modes properly, but i think its not needed, because its possible to combine all needed parts from layers.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-29T07:38:53+00:00
- Post Title: Parasite Eve (PS1)

Animation tool.

Since game has no t-poses, only animations allow to get characters in proper poses. Model tool is now obsolete.

To convert an animation, you need 2 files: model and animation. After asset extraction, folder 2 will have models, folder 3 will have animations.
For both, first number in filename is character code, it will correspond, with one exception: almost any room has a few aya (main hero) animations, and they are always 0. But when there's actual AYA model in the room, her animations are also 0, but her model is 2.

Usage: Parasite_anim.exe <model> <anim>

It must make 2 SMD files: one for model, another for animation. Apply animation to model to make it work.
Example animation of Maeda running:
[https://www.youtube.com/watch?v=PMXHGdLzi-s](https://www.youtube.com/watch?v=PMXHGdLzi-s)
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-29T08:06:05+00:00
- Post Title: Parasite Eve (PS1)

Many images in this game are 16-color paletted images. For example, aya texture has 18 palettes. This is how they look if you apply them to texture:



The tool collects palette indices from the model, for each quad and triangle. Notice how each region is taken from particular palette, and all 18 are used:



After that, the tool combines parts using that palette map, so it looks like this:



Then it extends them to full rectangles, so in the end, we're getting a full texture:
## Post #12
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-29T11:22:22+00:00
- Post Title: Parasite Eve (PS1)

Very interesting. This reminded me of color id map/mask textures used in modern games for customization. I thought it was a fairly new technique. Impressed to see that something similar was used in a PS1 game.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-12-30T16:51:45+00:00
- Post Title: Parasite Eve (PS1)

Texture tool.

usage:
Parasite_tex.exe <texture> <palette>

All textures in this game are split in 2 parts: main part and very small tail 128 bytes part. I don't know why is that. You need to merge them before converting. You can use "copy" cmd for it, or hex editor, or any file manager allowing to merge files.
A typical example of texture layout inside 9 folder:



First you see some images and big 16kb palette for background. Then character textures follow, which include texture data and palettes, sometimes they follow each other, sometimes they are in sets, but its always sequential, so obvious which palette is for which texture.

Texture may be 16-color or 256-color image.

16-color type is 256x256 and it will be 32768 bytes image and 1024 bytes palette.
(for these you need palmap.dat generated by the anim tool)

256-color type is 128x128 and it will be 16384 bytes image and 512 bytes palette.
(these have full 256-color palettes so palmap.dat is not needed)

note:
Some models use "broken" image palettes which make broken palmap.dat. I saw Torres texture, the bottom of his boots were UV-mapped on the middle of his shirt. You can't see it in game, but when converting texture, it breaks the final image. Tool will give you warning in this case and if you need, you can fix only the shirt part using individual parts, i'm saving them too.
## Post #14
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2021-01-01T19:18:06+00:00
- Post Title: Parasite Eve (PS1)

Thanks for this 
but when i click Parasite_img.exe it just open it then say it stopped responding..and crash
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-04T15:57:19+00:00
- Post Title: Parasite Eve (PS1)

> Reply from Casedey ↑Wed Dec 23, 2020 4:16 pm at Wed Dec 23, 2020 4:16 pm
>
> 
I was researching about Parasite Eve 2 Models...
In a few words i wasn't able to extract models from those files.

I checked PE2 and it looks like it was made by different people. Everything is different absolutely in terms of archive formats, models, etc.
So i made a new thread for it here:

[viewtopic.php?f=16&t=23250](https://forum.xentax.com/viewtopic.php?f=16&t=23250)
## Post #16
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2021-01-06T23:32:57+00:00
- Post Title: Re: Parasite Eve (PS1)

The tool doesn’t work for me it just flat out crash
Please forgive me for being a pathetic noob not worthy
Of getting help or even recognized as a existing person
## Post #17
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-01-07T00:22:20+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from Tsunani ↑Sat Jan 02, 2021 3:18 am at Sat Jan 02, 2021 3:18 am
>
> 
Thanks for this 
but when i click Parasite_img.exe it just open it then say it stopped responding..and crash


Edit, why did I expect to get a reply...

Did you extract the parasite eve ISO/bin file?
PE.IMG is a file inside of that, its 201,380KB.

Also if you're using Chrome, make sure to right click the zip file containing daemons tools and select 'trust/safe' or whatever the option is called.
Folder should look like this.



Capture.PNG (16.16 KiB) Viewed 190 times
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-07T09:04:41+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from Tsunani ↑Thu Jan 07, 2021 7:32 am at Thu Jan 07, 2021 7:32 am
>
> 
The tool doesn’t work for me it just flat out crash
Tools can't just crash. They always give error message. Without error message its impossible to tell whats the problem.

If window is closing, you have to open command window yourself and run the tool from there to see error message. If you dont know how to use command window, google it. There are so many ways to open and use it, that if i start explaining it here, it will take too much time and space.
## Post #19
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2021-01-08T11:11:17+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from lionheartuk ↑Thu Jan 07, 2021 8:22 am at Thu Jan 07, 2021 8:22 am
>
> 
Tsunani wrote: ↑Sat Jan 02, 2021 3:18 am
Thanks for this 
but when i click Parasite_img.exe it just open it then say it stopped responding..and crash


Edit, why did I expect to get a reply...


Did you extract the parasite eve ISO/bin file?
PE.IMG is a file inside of that, its 201,380KB.

Also if you're using Chrome, make sure to right click the zip file containing daemons tools and select 'trust/safe' or whatever the option is called.
Folder should look like this.
Capture.PNG
> Reply from daemon1 ↑Thu Jan 07, 2021 5:04 pm at Thu Jan 07, 2021 5:04 pm
>
> 
Tsunani wrote: ↑Thu Jan 07, 2021 7:32 am
The tool doesn’t work for me it just flat out crash



Tools can't just crash. They always give error message. Without error message its impossible to tell whats the problem.

If window is closing, you have to open command window yourself and run the tool from there to see error message. If you dont know how to use command window, google it. There are so many ways to open and use it, that if i start explaining it here, it will take too much time and space.

Alright well i already had tried using a comand prompt, in both case it stop working the message is : 

"Parasite stopped working
A problem made the program stop working correctly.
Windows will close this program and indicate if a solution is avaible"

then the two choices are
Debogging - close program

in the end it doesnt show a solution and the option it gives aside closing it
doesn't work either

as for the folder it  look exactly like the screencap in the reply, the PE.IMG is 206, 213KB
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-08T11:23:13+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from Tsunani ↑Fri Jan 08, 2021 7:11 pm at Fri Jan 08, 2021 7:11 pm
>
> 
Alright well i already had tried using a comand prompt, in both case it stop working the message is : 

"Parasite stopped working
this is not error message
message must be inside of command window. if you can't copy it, make a screenshot
## Post #21
- Username: HijackTheRipper
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Aug 29, 2014 9:28 pm
- Post datetime: 2021-01-08T12:08:06+00:00
- Post Title: Re: Parasite Eve (PS1)

Really impressive work daemon1
## Post #22
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2021-01-10T15:23:55+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from daemon1 ↑Fri Jan 08, 2021 7:23 pm at Fri Jan 08, 2021 7:23 pm
>
> 
Tsunani wrote: ↑Fri Jan 08, 2021 7:11 pm
Alright well i already had tried using a comand prompt, in both case it stop working the message is : 

"Parasite stopped working

this is not error message
message must be inside of command window. if you can't copy it, make a screenshot

Thats the problem, the command window open and its still black/empty then i get what i described before anything happen
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-10T15:43:29+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from Tsunani ↑Sun Jan 10, 2021 11:23 pm at Sun Jan 10, 2021 11:23 pm
>
> 
Thats the problem, the command window open and its still black/empty then i get what i described before anything happen
after you close the messagebox "described before", there must be message inside of command window
## Post #24
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2021-01-13T14:46:42+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from daemon1 ↑Sun Jan 10, 2021 11:43 pm at Sun Jan 10, 2021 11:43 pm
>
> 
Tsunani wrote: ↑Sun Jan 10, 2021 11:23 pm
Thats the problem, the command window open and its still black/empty then i get what i described before anything happen

after you close the messagebox "described before", there must be message inside of command window

Like i said nothing appear in the command window it goes on  a white overlay  the "does not respond" then all i can do is clic "close program"
[there.png](https://xentaxbackup.github.io/file/19298_there.png)
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-13T15:48:04+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from Tsunani ↑Wed Jan 13, 2021 10:46 pm at Wed Jan 13, 2021 10:46 pm
>
> 
daemon1 wrote: ↑Sun Jan 10, 2021 11:43 pm
Tsunani wrote: ↑Sun Jan 10, 2021 11:23 pm
Thats the problem, the command window open and its still black/empty then i get what i described before anything happen

after you close the messagebox "described before", there must be message inside of command window


Like i said nothing appear in the command window it goes on  a white overlay  the "does not respond" then all i can do is clic "close program"
AFTER you close the messagebox (click "close program"), there must be message inside of command window.
## Post #26
- Username: RedToaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 13, 2020 8:17 am
- Post datetime: 2021-01-15T06:27:41+00:00
- Post Title: Re: Parasite Eve (PS1)

Can't seem to find Aya's model (Opera and Normal outfit) in the files, Seem to only find NPCs and enemy models?
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-15T07:55:56+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from RedToaster ↑Fri Jan 15, 2021 2:27 pm at Fri Jan 15, 2021 2:27 pm
>
> 
Can't seem to find Aya's model (Opera and Normal outfit) in the files, Seem to only find NPCs and enemy models?
there are multiple instances of both of her outfits in the files
## Post #28
- Username: RedToaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 13, 2020 8:17 am
- Post datetime: 2021-01-15T08:00:09+00:00
- Post Title: Re: Parasite Eve (PS1)

Weird I just can't find them, Like I'm looking through many of the file extractions and looking in folder 2 .models and can just never find them, I'll keep looking unless I'm somehow screwing up like an idiot.
## Post #29
- Username: testhello
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 10, 2021 1:30 pm
- Post datetime: 2021-06-11T20:09:35+00:00
- Post Title: Re: Parasite Eve (PS1)

Hey so thank you for putting these resources up! I'm a little confused though on how exactly you find what's within the packages? Like if I want to sort out and find the 3D models used for Eve in the various stages in the game is there an easy way to do so with this just being numbered/lettered?
## Post #30
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-06-13T07:45:17+00:00
- Post Title: Re: Parasite Eve (PS1)

Join my discord I extracted everything there.
[https://discord.gg/j5RYUEwJ24](https://discord.gg/j5RYUEwJ24)
## Post #31
- Username: Sarahchan1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 10, 2021 12:34 am
- Post datetime: 2021-09-09T16:39:45+00:00
- Post Title: Re: Parasite Eve (PS1)

Thanks for this!
How do I use it on a phone?
## Post #32
- Username: churriguera
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 20, 2022 9:32 pm
- Post datetime: 2022-02-20T15:35:24+00:00
- Post Title: Re: Parasite Eve (PS1)

I have the same problem than the other user...
Parasite_img.exe works, but the others when they open a windows message appears to close, then appears a message on the window's exe, but it close before I can read it... It's too fast I can do anything...
Well, I only want the image backgrounds, If anyone have them...
## Post #33
- Username: Sarahchan1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 10, 2021 12:34 am
- Post datetime: 2022-04-23T11:35:31+00:00
- Post Title: Re: Parasite Eve (PS1)

> Reply from Sharppy ↑Sun Jun 13, 2021 3:45 pm at Sun Jun 13, 2021 3:45 pm
>
> 
Join my discord I extracted everything there.
https://discord.gg/j5RYUEwJ24
You're link expired
