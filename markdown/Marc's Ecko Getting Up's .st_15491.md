## Post #1
- Username: DarkJoney
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2016 6:23 am
- Post datetime: 2016-11-13T22:36:22+00:00
- Post Title: Marc's Ecko Getting Up's *.st

Hello, guys.

I would like to do retexturing of this game, to receive better overall look of it, Reshade works fine with it, but I completely stuck with it's texture format.
At the beggining of my idea, I thought that it's custom DDS, and I used HxD to edit the header. I received image with artifacts, but visible.
Later, I found NOTHING, except one guy novocoine, who did ST modding tool, but it seems to be so unfinished to work. It works correctly only with alpha-based textures, but with non-alpha I get gliched image. I found out, that if I save this glitched image in Paint.net as X8R8G8B8 or R5G6B5, it looks absolutely fine. 

Unfortunately, replacing of ST with edited DDS also causes glitches, and it's unusable.

I tried to edit source code to get compartibility with DXT1, because it seems to be DXT3 or DXT5, but no luck - I just receive different glitch looks   

There is github of this tool - [https://github.com/Asbra/GettingUpTool](https://github.com/Asbra/GettingUpTool)

Maybe someone could  help with fixing of this tool, or create another one? 

There are samples of *.st - [https://mega.nz/#!HpVykD4S!-wW7t4xdt71M ... 7FwlMOFJQ8](https://mega.nz/#!HpVykD4S!-wW7t4xdt71MGKolM0KqyRo998gNNnFlj7FwlMOFJQ8)

This is one of my favorite games, I have completed it several times, but in 2016, it looks not so good, as I wish.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-14T01:47:10+00:00
- Post Title: Marc's Ecko Getting Up's *.st

i see this game was made for PC, PS2 and Xbox, which platform did these samples come from?
[https://en.wikipedia.org/wiki/Marc_Eck% ... r_Pressure](https://en.wikipedia.org/wiki/Marc_Eck%C5%8D%27s_Getting_Up:_Contents_Under_Pressure)

made a Noesis python script to open your samples  


 tex_MarcEckosGettingUp_st.zip
(727 Bytes) Downloaded 47 times


supports dxt1 and dxt5 
you only had one dxt5 sample to check against, so the imgFmt integer being read might not be the correct one.
## Post #3
- Username: DarkJoney
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2016 6:23 am
- Post datetime: 2016-11-14T07:55:52+00:00
- Post Title: Marc's Ecko Getting Up's *.st

Of cource, it's pc  
I will try it right now, will this script convert texture back to St?
## Post #4
- Username: DarkJoney
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2016 6:23 am
- Post datetime: 2016-11-14T08:28:26+00:00
- Post Title: Marc's Ecko Getting Up's *.st

Well, it works, but how do I replace original tex with my own? 

I haven't found funcitonality for this.
## Post #5
- Username: DarkJoney
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2016 6:23 am
- Post datetime: 2016-11-14T22:31:31+00:00
- Post Title: Marc's Ecko Getting Up's *.st

Well, any ideas?
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-15T02:24:46+00:00
- Post Title: Marc's Ecko Getting Up's *.st

> Reply from DarkJoney
>
>  will this script convert texture back to St?
no, you'll just have to overwrite the 128 byte dds header with the original
388 byte st header and change the extension to st to change it back.
## Post #7
- Username: DarkJoney
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2016 6:23 am
- Post datetime: 2016-11-15T08:33:31+00:00
- Post Title: Marc's Ecko Getting Up's *.st

Using HxD as I understand?
## Post #8
- Username: DarkJoney
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2016 6:23 am
- Post datetime: 2016-11-15T08:53:58+00:00
- Post Title: Marc's Ecko Getting Up's *.st

Well, I copied header - image is glitchy now. Tried to edit another bytes - adds height or corrupts file.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-15T11:46:44+00:00
- Post Title: Marc's Ecko Getting Up's *.st

your brickwall01.st shows the size as 653 kb when it should be 33 kb.
i don't know what you did to the image but if you reuse the original
st header then you must keep the same size, format and dimensions
or you may have to modify the st header data, problem there is we
don't know what each byte in the header data represents and this
might require a full format analysis.
modding games is not really my thing so i can't help much further.
## Post #10
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2018-11-16T16:36:38+00:00
- Post Title: Marc's Ecko Getting Up's *.st

Hey you guys helped out alot!
thx for that
Are you able to create a noesis-script to view the models, too?
