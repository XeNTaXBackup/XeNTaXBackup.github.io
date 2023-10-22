## Post #1
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-23T01:14:59+00:00
- Post Title: TextureFinder (Noesis)

Tool for noesis. For find texture in binary file.



TextureFinder(Noesis).png (36.37 KiB) Viewed 457 times



install:
1) drop "tool_TextureFinder.py" in "..\Noesis\Plugins\Python"
2) reload Noesis or click "Tools>Reload Plugins"
3) "Tools>Display Plugin Tools" (if not already activated)
use:
1) "Tools>Texture Finder"

functionality is similar to many similar programs.
[tool_TextureFinder.py](https://github.com/Durik256/Noesis-Plugins/blob/master/tool_TextureFinder.py)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-23T01:20:15+00:00
- Post Title: TextureFinder (Noesis)

SAMPLES:
[Re: Need help: 25 To Life .DBL](https://forum.xentax.com/viewtopic.php?p=141739#p141739)



T349.DBL.png (33.96 KiB) Viewed 545 times


[Metropolis Software *.texture files](https://forum.xentax.com/viewtopic.php?p=185972#p185972)

[ObsCure 2 (PS2) - Trying to load images](https://forum.xentax.com/viewtopic.php?p=185566#p185566)

[S.W.A.T. Target Liberty (*.TEX) Textures](https://forum.xentax.com/viewtopic.php?p=111733#p111733)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-23T05:27:42+00:00
- Post Title: TextureFinder (Noesis)

Hi, what about the formats? It's funny that it accepts R8 and B8 for example (tried r16g4b8 just for fun  ) but I'd prefer choosing from a list like so:
.



D3DDX.png (68.36 KiB) Viewed 521 times


(Dunno how many formats Noesis supports - but R4G4B4A4 to R8G8B8A8 (and variations) should cover most cases. So exotic ones in above list aren't needed.)

Another feature being very important when dealing with unknown textures is the variable sizing such as gimp allows with his "Raw image data" (-> window "Load Image from Raw Data"). Sadly gimp has only 5 RGB types for this feature.

Having a slider for the width at least would be cool.
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-24T16:13:15+00:00
- Post Title: TextureFinder (Noesis)

> Reply from shakotay2 ↑Fri Dec 23, 2022 1:27 pm at Fri Dec 23, 2022 1:27 pm
>
> 
Hi, what about the formats? (tried r16g4b8 just for fun  )

Hi, Shakotay)
noesis has a lot of stuff, but for now I only added raw data, raw data with palette, and compress [DTX1, DTX2, DTX5].
raw 'uncompress' format support thish chanel [R,G,B,A,P] with any lenght bits.
(by the way, if a palette is used, then the "format" value for palette)

> Reply from shakotay2 ↑Fri Dec 23, 2022 1:27 pm at Fri Dec 23, 2022 1:27 pm
>
> 
Sadly gimp has only 5 RGB types for this feature.
I usually used PVRTexTool 
[https://i.imgur.com/2ZWrlBd.png](https://i.imgur.com/2ZWrlBd.png)

> Reply from shakotay2 ↑Fri Dec 23, 2022 1:27 pm at Fri Dec 23, 2022 1:27 pm
>
> 
Having a slider for the width at least would be cool.
I am for complete freedom in specifying values))
i added a custom UpDownNumeric as well as a DropDown for permission etc. but all values can still be changed manually.
(update in first post)

Slider for width.   
I added two Scrolls just for testing for editing width and height. (I will attach this version to this post)

*(for some reason I also considered it necessary not to add UpDownNumeric for Width and Height)
[tool_TextureFinder(Scroll).zip](https://xentaxbackup.github.io/file/23191_tool_TextureFinder(Scroll).zip)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-25T13:52:32+00:00
- Post Title: TextureFinder (Noesis)

Hi Durik,
thanks for the sliders.

What I meant, was a live sizing (dunno whether it's possible in an easy way with python).

It's when you have no clue about the size and try to find picture elements. It's a "ping-pong" between changing the width and displaying the resulting picture:
.



live_sizing.jpg (164.93 KiB) Viewed 405 times
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-25T19:56:57+00:00
- Post Title: TextureFinder (Noesis)

> Reply from shakotay2 ↑Sun Dec 25, 2022 9:52 pm at Sun Dec 25, 2022 9:52 pm
>
> 
was a live sizing
I originally wanted to add real time change. but I thought that pressing the button to render would be enough.   
here is a test, every time the value changes(UpDownNumeric, Manual, Slider), the image is updated. with this implementation (the file is opened every time), the sliders will work slower  



 tool_TestTx.zip
(2.58 KiB) Downloaded 37 times
## Post #7
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-12-25T23:52:13+00:00
- Post Title: TextureFinder (Noesis)

(image embeds removed due to Imgur's recent ToS changes about inactive photos)

Hi Durik, indeed, very interesing concept, along i have seen your mobile model researcher too which was also cool

Tested out both the available versions, unfortunately TestTx doesn't support the DXT groups so i couldn't get a exact experience of how the slider would work but i could test it out the real time update still. otherwise the other versions works great with DXT, despite some slight suggestions i would give to it, the offset at the moment it works more or less like a "palette change" on the DXT textures, despite i noticed inputting higher values, the image would scroll down


Using the MUA's TextureFinder, which i think is one of the inspirations to it, the palette change works by tweaking the Shift region, which allows you to nagivate into the whole offset using one of the palettes fixed, when the offset function in general it works by loading the entire texture block, which you could scroll using the sidebar by the button or doing jumps on the wide spaces. and this is useful when checking large raw container textures like the one i showcased, as a lot of the textures bundled are headerless DDS, which makes things a bit harder to determine their starting point, but finding the correct offset, comfirming it with HxD, then inputting on Rawtex which automatically isolates the single texture, is the perfect toolset combination to my workflow, and i think it would be one of the examples of what Shatokay said of "live sizing" research


[https://i.imgur.com/jporsfH.mp4](https://i.imgur.com/jporsfH.mp4)

Looking forward for the future updates, due with those functions added, indeed it'll be the best tool to recommend to the recent times, as despite MUA's TextureFinder is still useful, the main negative point of it turns into the constant false positive flagging on Windows Defender because of a common flaw of Delphi developed apps, and despite i didn't had any issues, trying to convince paranoid users to use TextureFinder in a tutorial wouldn't be a easy task to do, as i agree major download sites started this infamous aspect to keep a eye of what you download on the internet to avoid major troubles
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-27T00:58:26+00:00
- Post Title: TextureFinder (Noesis)

> Reply from RythusOmega ↑Mon Dec 26, 2022 7:52 am at Mon Dec 26, 2022 7:52 am
>
> 
the offset at the moment it works more or less like a "palette change"
"offset" is the offset from the beginning of the file, the same as "Shift" in the TextureFinder you provided. it has nothing to do with the palette.
in the "TextureFinder MUA" you provided, the height of the image is calculated automatically.
it's a slider, it's just scrolling the image.

I have added a "max" option for the height value. this will automatically calculate the max height. (you need to be careful with very large files). or enter a large value manually. after which you can move texture in the Noesis viewport.
video with example: [https://i.imgur.com/KJTagAj.mp4](https://i.imgur.com/KJTagAj.mp4)

in addition to the "run" button, also now the result will be displayed when opening the file and when pressing any UpDownNumeric.
**(all updates in the first post.)

> Reply from RythusOmega ↑Mon Dec 26, 2022 7:52 am at Mon Dec 26, 2022 7:52 am
>
> 
"mobile model researcher"/ "Looking forward for the future updates"
thank you for message. also write about errors and bugs if you notice them. 
Feedback is a very important thing.
## Post #9
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-12-27T13:21:51+00:00
- Post Title: TextureFinder (Noesis)

(image embeds removed due to Imgur's recent ToS changes about inactive photos)

Thanks Durik, downloaded the recent version

Indeed, with the "max" value, it now shows the entire raw section of the file instead of croping to a fixed region when using the doubles(1024x, 512x, etc...), seen on the new sample video, the example file took 8 minutes in total to load, which is expected from a 38MB file which aside of headerless DDS textures contains other types of non-image data
[https://streamable.com/qazcgy](https://streamable.com/qazcgy)

Giving more information of my points with the MUA TextureFinder, yeah the height/width part is correct, isn't exactly palettes, but the current offset read as the starting point does play a role on DXT textures, due some additional bytes could change how the same texture is displayed(like inserting bytes of a DXT1 on a DXT3)

About the width box, using the arrow buttons you can decrease/increase the resolution value by 1 which will also result in a automatic skew change that could be tweaked separately on the 1.3.2 version of MUA(and skew control is already separated by default on your plugin) the buttons is what i used before when i had a clear notion the texture wouldn't be one based on doubles, the good thing of your Noesis plugin is both can be edited compared to MUA, so i could double check what exact value the width would be

Now about the scroll, i understood you first emulated based on scrolling a raw container, which is good, one only thing went missing, when i scrolled the image on the example gif, there's two red boxes below the preview and the camera icon, the first show the file size in bytes, when the second shows the current file hexadecimal offset in decimals, exemplified by a very little black arrow that is on the top left of the border of the preview. so when you load a raw container, it will always starts on 0, and scrolling down it would be following byte-by-byte of the offset of the image, don't worry that i included also a sample video of how my current workflow of ripping those containers are based
[https://streamable.com/jixxpm](https://streamable.com/jixxpm)

Rewriting the whole offset mechanism wouldn't be the ideal, but i guess like, create something that ressembles the arrow, and could be controlled and shows the offset of the file in hexadecimal would be already useful, and the last remaining part of the important functions of MUA TextureFinder that i wanted and couldn't be emulated well on other programs
