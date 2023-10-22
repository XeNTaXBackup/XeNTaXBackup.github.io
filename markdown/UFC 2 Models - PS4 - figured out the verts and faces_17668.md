## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2018-02-06T06:28:51+00:00
- Post Title: UFC 2 Models - PS4 - figured out the verts and faces

Hi guys.

Need help with the models for the UFC 2 game on the ps4. The model extension is MCD and the header is RSF. 

Here's a sample of the file:

MCD Model: [http://www74.zippyshare.com/v/f2E614jW/file.html](http://www74.zippyshare.com/v/f2E614jW/file.html)
## Post #2
- Username: gr8oblivion
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 05, 2018 12:03 am
- Post datetime: 2018-11-07T14:49:15+00:00
- Post Title: UFC 2 Models - PS4 - figured out the verts and faces

i know this is like 9 month old thread... but any luck with MCD files? it seems like it might be the same file format as NHL 18 for PS4, and i'm trying to extract models from that game...

Thanks.
## Post #3
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2019-05-09T11:22:29+00:00
- Post Title: UFC 2 Models - PS4 - figured out the verts and faces

Had some spare time to look into the model format again. It seems like there are hard coded text values indicating the start of the verts and faces instead of offset references. Using this assumption, I wrote code to the view the models in an existing application I've coded. The code seems to work with the models I have tested:



I haven't figure out the UV format as yet. Using @shakotay2 's hex2obj, I determined that the UV's are half float values but I don't know how to convert these hex values into float using C#. With the UV's exported from hex2obj, the model looks like this:



I'm not the best at maxscript, but I can try to write an import script once the uv format is figured out, that's if anyone is interested in these models?
## Post #4
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2019-05-10T08:23:33+00:00
- Post Title: UFC 2 Models - PS4 - figured out the verts and faces

Spend the entire day reading up on half float values and managed to code support for the UV's. The code is still rough but it seems to work on all the head models in the game.



texture_preview.jpg (243.32 KiB) Viewed 159 times
## Post #5
- Username: SomeExtraDamage
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 03, 2020 2:54 pm
- Post datetime: 2020-06-27T18:20:45+00:00
- Post Title: UFC 2 Models - PS4 - figured out the verts and faces

> Reply from plodtrew ↑Fri May 10, 2019 4:23 pm at Fri May 10, 2019 4:23 pm
>
> 
Spend the entire day reading up on half float values and managed to code support for the UV's. The code is still rough but it seems to work on all the head models in the game.

 texture_preview.jpg

@plodtrew

I'm interested in this, how can I do the same thing and mod textures and models?
