## Post #1
- Username: Nappasaiyan
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Aug 06, 2023 1:48 pm
- Post datetime: 2023-08-22T23:06:16+00:00
- Post Title: The Punisher 2005 Models rip

Hi, this is my first post.
I recently used "Ninja ripper" to get The Punisher 2005 models.
For now, all good.
I just wanted to know how I could fix this error in the UVMaps, if there is any method or addon.
My intention is to get all the weapon and character models.
I use blender.
[Captura de pantalla 2023-08-22 200442.jpg](https://xentaxbackup.github.io/file/24259_Captura de pantalla 2023-08-22 200442.jpg)
## Post #2
- Username: Franky212
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 29, 2023 4:07 am
- Post datetime: 2023-08-24T19:52:13+00:00
- Post Title: The Punisher 2005 Models rip

> Reply from Nappasaiyan ↑Wed Aug 23, 2023 7:06 am at Wed Aug 23, 2023 7:06 am
>
> 
Hi, this is my first post.
I recently used "Ninja ripper" to get The Punisher 2005 models.
For now, all good.
I just wanted to know how I could fix this error in the UVMaps, if there is any method or addon.
My intention is to get all the weapon and character models.
I use blender.
Try to import with these settings:
Texturing "TexCoord in multi attributes"
TexU "6 0"
TexV "7 1" or TexV "7 0"



BlenderImportNRSettings.jpg (55.6 KiB) Viewed 149 times


Info from Ninja Ripper importer manual:
[https://github.com/riccochicco/ninjarip ... /README.md](https://github.com/riccochicco/ninjaripper/blob/master/README.md)
TexCoord (u,v) - fields for enter data defining texture coordinates of the model, one of the most important parameters. For games, wich model imports without a proper uv-coordinates, a pair of UV always choosing by search. At the time is Identified that pairs can not exceed number 50, that is can be 6-7 or 18-19 or 24-25 or 39-40 etc. In very rare cases, a pair of uv can be 3-4 or 4-5 or 5-6, which is within the "normal field of definition", as well as 8-6 or 12-11, which is at odds with common sense, but may still be.
## Post #3
- Username: Nappasaiyan
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Aug 06, 2023 1:48 pm
- Post datetime: 2023-08-25T03:59:52+00:00
- Post Title: The Punisher 2005 Models rip

I'm sorry I didn't reply to your message.
I saw it at the time, simply that I have done what you recommended a little later.
At the moment I have not had good results (using the values ​​you gave as an example) but I imagine it will be something to test.
## Post #4
- Username: Nappasaiyan
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Aug 06, 2023 1:48 pm
- Post datetime: 2023-08-25T04:23:56+00:00
- Post Title: The Punisher 2005 Models rip

I took the Punisher Trenchcoat model apart for testing.
I mean, I have a folder with the Punisher .NR files.
[Captura de pantalla 2023-08-25 012239.jpg](https://xentaxbackup.github.io/file/24265_Captura de pantalla 2023-08-25 012239.jpg)
## Post #5
- Username: Franky212
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 29, 2023 4:07 am
- Post datetime: 2023-08-25T19:18:38+00:00
- Post Title: The Punisher 2005 Models rip

> Reply from Nappasaiyan ↑Fri Aug 25, 2023 11:59 am at Fri Aug 25, 2023 11:59 am
>
> 
I'm sorry I didn't reply to your message.
I saw it at the time, simply that I have done what you recommended a little later.
At the moment I have not had good results (using the values ​​you gave as an example) but I imagine it will be something to test.
Hi. If the UV 6-7 pair doesn't work, try other pairs from the list. Or create a multi-volume archive with NR files and send it to me in private messages, I can try to find the right pair of UVs to import. If you send me the NR files, don't forget to show me a screenshot from the game so I know how the textures should look right.
## Post #6
- Username: Nappasaiyan
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Aug 06, 2023 1:48 pm
- Post datetime: 2023-08-25T20:57:25+00:00
- Post Title: The Punisher 2005 Models rip

Oh that sounds great.
Again, I'm so sorry to reply late.
I'm from Argentina, our hours are different.
I will attach the files in a mediafire link and a photo of how it should look.
As you said, I'll send it to you privately
## Post #7
- Username: Nappasaiyan
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Aug 06, 2023 1:48 pm
- Post datetime: 2023-08-25T23:30:46+00:00
- Post Title: The Punisher 2005 Models rip

For those who are reading this.
I managed to correctly apply the textures using the following values: U: 3 0 V: 3 1.
I don't know if this could cause a problem.
At least in Blender it looks good.
When I rip everything (weapons and characters) it is likely that I will make a publication with the respective Links of each model
[punisher.png](https://xentaxbackup.github.io/file/24274_punisher.png)
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-08-26T06:31:15+00:00
- Post Title: The Punisher 2005 Models rip

I used to make plugins for this game
*.vpp (game archive), *.rxm (static model), *.rxc (character model), *.ceg (texture container)
with skin(rig)/and bones
[2a97e78c15efcb6c9.png](https://xentaxbackup.github.io/file/24275_2a97e78c15efcb6c9.png)
## Post #9
- Username: Nappasaiyan
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Aug 06, 2023 1:48 pm
- Post datetime: 2023-08-26T08:09:56+00:00
- Post Title: The Punisher 2005 Models rip

At the time I saw that post (and obviously your comments) I was very desperate!
The truth is that although I am very attracted to the idea of ​​making modifications to the game (and I have a very basic knowledge about it) I am only excited to rip all the models and reveal them to the public for the personal use of each user.
What I usually do with this kind of thing is make mods for left 4 dead 2, although in this case I don't know if I'm going to do it.
It's one of those things where you wonder why nobody has ripped the models or at least why they haven't published it?
I'm especially excited for the simple fact that this is one of my childhood games, plus seeing this kind of thing is always interesting.
