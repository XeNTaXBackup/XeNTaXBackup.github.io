## Post #1
- Username: Ako
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 07, 2022 10:59 pm
- Post datetime: 2023-05-09T12:10:24+00:00
- Post Title: [PS3] FF13 extracting Hope weapon

Hi everyone,

I'm having a hard time with one FF13 model. I'm trying to extract screenshots of all weapons like this lovely site :
[https://finalfantasy.fandom.com/wiki/Fi ... Boomerangs](https://finalfantasy.fandom.com/wiki/Final_Fantasy_XIII_weapons/Boomerangs)
Currently, Noesis is my friend and is enought with the Ultra-shot option.

However when I encounter Hope weapon, there is a model (for Ninurta, Jatayu, Vidofnir, Hresvelgr) which have a "web" design and the hole are not cropped under Noesis. I'm guessing that it's because the surface of render is "flat" (not in 3D, it's a 2D curved plan) and the engine inside Neosis doesn't remove that part.

Here is my result :
[https://ibb.co/88gqV47](https://ibb.co/88gqV47)
And here is the real render into the game : 
[https://finalfantasy.fandom.com/wiki/Ja ... Jatayu.png](https://finalfantasy.fandom.com/wiki/Jatayu_%28weapon%29?file=FFXIII_Jatayu.png)

(We can note that the handle is well cropped because there is some depth)

Noesis probably have an option or a property to change (in the Data Viewer section) but I'm having a hard time founding how to solve this problem. The export to 3DS Max (with fbx output) has the same problem.
Someone has already faced that or has a tips to share ?

Thx for listening,
Ako
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2023-05-09T14:04:34+00:00
- Post Title: [PS3] FF13 extracting Hope weapon

It looks like you just need to enable the Alpha for the texture for those webbed sections, thats it.
## Post #3
- Username: Ako
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 07, 2022 10:59 pm
- Post datetime: 2023-05-09T18:11:38+00:00
- Post Title: [PS3] FF13 extracting Hope weapon

With your tip, I found this related subject:
[viewtopic.php?p=120216#p120216](https://forum.xentax.com/viewtopic.php?p=120216#p120216)

I'm exactly on the same spot, but the thread remains wild open.. It helps me understanding how the alpha channel is encoded in this case. I tried to juggle with all opacity/transparency/alpha properties I found (Material -> Alpha test/Opacity texture & Persistent Settings -> View -> Render opacity mask) in the Data Viewer but it doesn't seem to render the way that it should. Chat GPT doesn't give me an understandable way neither to do this. 
I also search on the Export command to check if there is any related command to the alpha channel but nothing seems useful..

Thanks to put me on the track, I'll keep searching !
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-10T00:59:32+00:00
- Post Title: [PS3] FF13 extracting Hope weapon

> Reply from Ako ↑Tue May 09, 2023 8:10 pm at Tue May 09, 2023 8:10 pm
>
> ...Someone has already faced that or has a tips to share ?...
Not sure how this may prove to be useful to you, but... After you import/load the desired model, in the viewport of Noesis, at the bottom left corner, there's the following ICON


AlphaIcon.PNG (3.73 KiB) Viewed 50 times

Click on it until correct Alpha is enabled, and on the Debug Log pop up window you will see what each cycle represents, and they are:

```
Default blend: Alpha + alpha test
Default blend: Alpha (no test)
```

Or on keyboard press F11 to cycle through that option, if that particular model has different type of setup for the Alpha, then your best bet is to export it and import it in another 3D Editor to place the textures accordingly.
