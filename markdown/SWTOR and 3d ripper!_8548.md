## Post #1
- Username: crispycat
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 14, 2012 5:53 pm
- Post datetime: 2012-03-14T11:13:48+00:00
- Post Title: SWTOR and 3d ripper!

Hi 
I need some help working out how to fix what i think is texture miss alignment when using 3d ripper dx with SWTOR and 3dsmax..
I am fairly new to 3d modelling but have a good background of photoshop and 2d applications.

this is a normal print screen of a random scene i am currently playing with:


however this is how it turns out after using 3d ripper dx and importing to 3dsmax 2010 :


as you can see the actual scene is perfectly captured but the textures are a total mess!
changing the uv chanel didnt work and messing with w,u,v positions made the mess worse! 

looking at the .dds file for the texture on example the jawa (hooded creature in the scene) it appears to be a normal layout and mesh 
(well from what i have seen of layouts when half life modding a long time ago) :
 

im really hopping someone can advise me on maybe a setting that i could change or a plugin to correct this problem but fear i will have to learn to remap the whole model   

also if you want to know how to get 3d ripper dx to work with swtor ill post how to do it..
cheers
## Post #2
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2012-03-14T13:17:16+00:00
- Post Title: SWTOR and 3d ripper!

It 's not the problem of 3D Ripper DX. Some game has extra security or the model file have some strange structure that 3D Ripper DX cannot rip the model perfectly.

Did you tried to assgin texture again into the model ? And if you got same result =>> you need to re UV mapping this model again 

I can see the UV problem in your picture 

Another way, if you import .obj file from 3D Ripper into 3ds max, just change to .3dr, maybe you will get better result
## Post #3
- Username: DarkPhoenix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 14, 2012 12:58 am
- Post datetime: 2012-03-14T16:55:15+00:00
- Post Title: SWTOR and 3d ripper!

> Reply from crispycat
>
> Hi 
I need some help working out how to fix what i think is texture miss alignment when using 3d ripper dx with SWTOR and 3dsmax..
Have you applied Unwrap UVW Modifier?
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-03-14T17:11:42+00:00
- Post Title: SWTOR and 3d ripper!

I dont remember where I saw it but there is a script for max fixing these UV issues from 3r dripper rips. It is a small popup with some buttons and you basically click on a couple of them until it works 

Worked for me on Dragon nest, looked really weird but with script it turned to normal again.

Check 3d ripper forum. I can check this script when I get home

Here it is:

[http://www.deep-shadows.com/hax/forum2/ ... 2&t=101232](http://www.deep-shadows.com/hax/forum2/viewtopic.php?f=2&t=101232)

Made by Tosyk who is a member here and on umodel forum alot
## Post #5
- Username: crispycat
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 14, 2012 5:53 pm
- Post datetime: 2012-03-15T13:34:26+00:00
- Post Title: SWTOR and 3d ripper!

thanks everyone for the replies its really appreciated  

> Reply from goder2910
>
> Another way, if you import .obj file from 3D Ripper into 3ds max, just change to .3dr, maybe you will get better result
unfortunately i get the same problem with .obj and .3dr  

> Reply from DarkPhoenix
>
> Have you applied Unwrap UVW Modifier?
I have to admit that im very much a noob to 3d.. could you please describe this process further? 

> Reply from pixellegolas
>
> I dont remember where I saw it but there is a script for max fixing these UV issues from 3r dripper rips. It is a small popup with some buttons and you basically click on a couple of them until it works

I really wish this had worked  i found a tutorial and working download from Tosyks blog [http://cgig.ru/2011/07/3d-ripper-uv-repair/#](http://cgig.ru/2011/07/3d-ripper-uv-repair/#)
however it seems to just change the uv channels .. the texture is still not correctly placed  

so i still have the same problem  ...but at least im learning more about 3dsmax
## Post #6
- Username: DarkPhoenix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 14, 2012 12:58 am
- Post datetime: 2012-03-15T15:19:29+00:00
- Post Title: SWTOR and 3d ripper!

> Reply from crispycat
>
> I have to admit that im very much a noob to 3d.. could you please describe this process further?
[](http://piccy.info/view3/2755985/26dd145b5f6c44e580499fe1c356adf4/)
Make sure the model you want is selected.
## Post #7
- Username: crispycat
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 14, 2012 5:53 pm
- Post datetime: 2012-03-15T17:20:17+00:00
- Post Title: SWTOR and 3d ripper!

> Reply from DarkPhoenix
>
> Make sure the model you want is selected.

ok so im guessing the green dots are the uv alignment points on the model: 



they look alot clearer on the back of the model: 



now if i go down the options that apear after selecting unwrap uvw and click edit
 i get this mess that looks like the texture file tiled multiple times and a big messy ball of coordinate points?: 



thanks again for all your help
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-16T01:09:01+00:00
- Post Title: SWTOR and 3d ripper!

crispycat, can you give me 3dr file of your rip with textures you want to apply?
## Post #9
- Username: crispycat
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 14, 2012 5:53 pm
- Post datetime: 2012-03-16T17:47:00+00:00
- Post Title: SWTOR and 3d ripper!

Hi Tosyk
hope you can help me with this and teach me how to fix swtor models!   

here is the texture  .dds 
[http://www.2shared.com/file/_xiLWZ_7/6e0567f0.html](http://www.2shared.com/file/_xiLWZ_7/6e0567f0.html)
and the scene .3dr 
[http://www.2shared.com/fadmin/26777233/ ... 7.3dr.html](http://www.2shared.com/fadmin/26777233/370e1f75/frame_03032012_175517.3dr.html)

the model comes up in 3dsmax 2010 as drawcall_0406 for me at X:0.02, Y:0.07, Z:0.01

cheers
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-18T05:16:32+00:00
- Post Title: SWTOR and 3d ripper!

> Reply from crispycat
>
> Hi Tosyk
hope you can help me with this and teach me how to fix swtor models!your 3dr is not contain uv for characters, for some reason '3d ripper dx' does not ripping correct uv, but you should try other rippers like 3dripper from black_ninja or GA, they can also rip t-posed models
also, i've downloaded official swtor client (25gb  ) and research info about formats, after assuming all information i can tell you:
- you can convert models, even jawa from swtor BETA only
- you can't convert models from swtor release version

so when you find a BETA you can use [this](http://forum.xentax.com/viewtopic.php?p=61493#p61493) or [this](http://forum.xentax.com/viewtopic.php?p=61587#p61587) for converting all that you want
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-03-18T07:07:59+00:00
- Post Title: SWTOR and 3d ripper!

The last beta version of the assets is when they modified the gr2 format, i know the two beta versions prior to the last one still had the old format and the extracted gr2 files could be converted to obj with the tool here:
[viewtopic.php?p=62216#p62216](http://forum.xentax.com/viewtopic.php?p=62216#p62216)

If your asset archives look similar to this:
green_main_x.tor
assets_main_x.tor
then these gr2 files can be converted with the tool linked above.


If your asset archives look similar to this:
swtor_main_x_x.tor
then the gr2 files can't be converted yet since new tool development has seemingly come to a halt.
## Post #12
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-03-18T08:31:44+00:00
- Post Title: SWTOR and 3d ripper!

> Reply from AceWell
>
> then the gr2 files can't be converted yet since new tool development has seemingly come to a halt.Don't worry, now that Torhead has 3D models of the weapons, I am very anxious to get the models as well! 

I already have most of the .gr2 format analyzed and am only missing the texture coordinates, so I am about as far as crispycat.
However, reading the original models seems somewhat easier to me, unless you're talking about getting the whole landscape at once. 

Hopefully, someone can code a Noesis plugin since my attempts at that have failed; but I will of course publish an outline of the format once I have the texture coordinates nailed down.
[ald_arch_battleground_turret_tower_01.jpg](https://xentaxbackup.github.io/file/5205_ald_arch_battleground_turret_tower_01.jpg)
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-18T10:29:37+00:00
- Post Title: SWTOR and 3d ripper!

> Reply from SWTOR fan
>
> I already have most of the .gr2 format analyzed and am only missing the texture coordinatesnice progress, thanks
## Post #14
- Username: crispycat
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 14, 2012 5:53 pm
- Post datetime: 2012-03-18T12:55:55+00:00
- Post Title: SWTOR and 3d ripper!

Thanks for trying for me Tosyk 
ill try the other rippers you suggested hopefully ill get more luck 

I have tried to follow the thread of ripping from the swtor files...
I also had problems with the gr2 files as i only have release client 
this is what lead me to remove dx10 + 11  and go for the 3d ripper 

another reason is that id like to be able to rip models of friends and guild members playing in there full gear and lower the polycount till i can use pepekura to unfold a papercraft model  [http://www.tamasoft.co.jp/pepakura-en/](http://www.tamasoft.co.jp/pepakura-en/)

I can imagine trying to position 15 items of armor onto a game files t model and then trying to reposition them all perfectly to be quite difficult  
*but id be interested to try once the gr2 is decoded
## Post #15
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-03-18T14:26:47+00:00
- Post Title: SWTOR and 3d ripper!

I posted a tutorial for EasyMYP [here](http://forum.xentax.com/viewtopic.php?p=69545#p69545); maybe it helps you with extracting files.

You're right, it's definitely easier to rip a whole character than trying to piece 10 .gr2 files for each body part together.
But I do plan to find out how to join them together automatically.

That papercraft program looks very interesting, by the way. It would be great if you could post a .pdf file to fold a SWTOR character when you are done.
## Post #16
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-03-19T19:33:15+00:00
- Post Title: Re: SWTOR and 3d ripper!

> Reply from SWTOR fan
>
> I already have most of the .gr2 format analyzed and am only missing the texture coordinates.

noesis.getFloat16
## Post #17
- Username: Turkish Phantom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 13, 2014 10:20 am
- Post datetime: 2014-02-13T06:32:15+00:00
- Post Title: Re: SWTOR and 3d ripper!

> Reply from crispycat
>
> also if you want to know how to get 3d ripper dx to work with swtor ill post how to do it..
cheers

Can't really believe no one asked yet when there aren't any tutorials on how to do it.

If anyone knows how to make 3D Ripper/Ninja Ripper work on SWTOR that would be awesome. Been trying for a month and a half and no luck on my end.
## Post #18
- Username: kibasennin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 16, 2016 11:26 pm
- Post datetime: 2016-05-16T15:41:36+00:00
- Post Title: Re: SWTOR and 3d ripper!

> Reply from Turkish Phantom
>
> crispycat wrote:also if you want to know how to get 3d ripper dx to work with swtor ill post how to do it..
cheers

Can't really believe no one asked yet when there aren't any tutorials on how to do it.

If anyone knows how to make 3D Ripper/Ninja Ripper work on SWTOR that would be awesome. Been trying for a month and a half and no luck on my end.

Yeah, seriously, can someone tell us?
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-05-16T18:15:35+00:00
- Post Title: Re: SWTOR and 3d ripper!

The last time i used Ninjaripper with SWTOR there was no trickery or anything special, i just launch Ninjaripper and point it to the SWTOR launcher exe and log into game and capture anything i needed.
## Post #20
- Username: kibasennin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 16, 2016 11:26 pm
- Post datetime: 2016-05-16T19:01:06+00:00
- Post Title: Re: SWTOR and 3d ripper!

> Reply from AceWell
>
> The last time i used Ninjaripper with SWTOR there was no trickery or anything special, i just launch Ninjaripper and point it to the SWTOR launcher exe and log into game and capture anything i needed.
Which keys did you bind for the screenshot taking then  ?! Cuz I been doing this for 2-3 times, and it doesnt work...!
## Post #21
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-05-16T19:31:33+00:00
- Post Title: Re: SWTOR and 3d ripper!

I use the x86 Ninjaripper 1.5.1 with the inject mode on "Intruder inject"
for "Rip keys select"
All F10
Textures F9
Forced F4

"Forced rip interval" set to 5 sec
## Post #22
- Username: kibasennin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 16, 2016 11:26 pm
- Post datetime: 2016-05-18T12:52:34+00:00
- Post Title: Re: SWTOR and 3d ripper!

> Reply from AceWell
>
> I use the x86 Ninjaripper 1.5.1 with the inject mode on "Intruder inject"
for "Rip keys select"
All F10
Textures F9
Forced F4

"Forced rip interval" set to 5 sec

It worked! AHAHAHAHAHH! IT worked! You beautiful genius! I could kiss you like man kisses woman (deadpool reference)!
How do I open the .rip files???
## Post #23
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2016-05-20T16:04:17+00:00
- Post Title: Re: SWTOR and 3d ripper!

> Reply from kibasennin
>
> AceWell wrote:I use the x86 Ninjaripper 1.5.1 with the inject mode on "Intruder inject"
for "Rip keys select"
All F10
Textures F9
Forced F4

"Forced rip interval" set to 5 sec

It worked! AHAHAHAHAHH! IT worked! You beautiful genius! I could kiss you like man kisses woman (deadpool reference)!
How do I open the .rip files???

Noesis ......
## Post #24
- Username: Leeloobastet
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 16, 2016 3:45 am
- Post datetime: 2016-08-15T19:48:24+00:00
- Post Title: Re: SWTOR and 3d ripper!

Hello

I did exactly as you wrote above, but I can't rip anything from SWTOR 
The only thing I got is a .txt file (launcher.exe.log.txt)
have I forgotten something ?

(I have to say that I didn't have any problem to extract GuildWars 2 models with an older version of NinjaRipper)
## Post #25
- Username: Leeloobastet
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 16, 2016 3:45 am
- Post datetime: 2016-08-17T17:54:27+00:00
- Post Title: Re: SWTOR and 3d ripper!

Up !
Knock knock 

If someone can help me ^_^
Thank you in advance
## Post #26
- Username: Leeloobastet
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 16, 2016 3:45 am
- Post datetime: 2016-09-05T21:41:58+00:00
- Post Title: Re: SWTOR and 3d ripper!

Up ^^
## Post #27
- Username: Rudolf123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 29, 2015 6:54 pm
- Post datetime: 2016-10-02T14:50:38+00:00
- Post Title: Re: SWTOR and 3d ripper!

If someone doesn`t know how to rip a scene from SWTOR with Ninjaripper there is a list of the right steps.

1. Download Ninjaripper (I used the last version).

2. Open Ninjaripper x86 and point it to "swtor.exe" in your "Star Wars-The Old Republic\swtor\retailclient\" folder.

3. Select "D3D9 wrapper" injection mode.

4. Press "Run" and the program will add "d3d9.dll" in folder with "swtor.exe".

5. Launch SWTOR as usual and in the game use the keys that are defined in "Settings". (I used the same as AceWell's).

6. In "Output Directory" you can find all ripped meshes *.rip and textures *.dds.

I didn`t manage to make it work with "Intruder injection" mode no matter what AceWell told. My method allows the program to break exactly into "swtor.exe" not "launcher.exe".

After all operations "d3d9.dll" must be deleted MANUALLY.
## Post #28
- Username: esreveR
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Sep 28, 2016 11:52 pm
- Post datetime: 2016-12-12T21:53:35+00:00
- Post Title: Re: SWTOR and 3d ripper!

I know this is old so forgive to bumping, but am curious would I need to launch the actual release of SWTOR or is it still the beta of it with ninjaripper? Just don't wanna download both that are probably 20gb
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-13T11:31:27+00:00
- Post Title: Re: SWTOR and 3d ripper!

well the beta of SWTOR has been offline for 5 years and would be impossible to hook into   
so yes, you would need to download the current client to use NinjaRipper on it.
