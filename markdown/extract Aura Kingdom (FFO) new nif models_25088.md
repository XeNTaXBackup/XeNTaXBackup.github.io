## Post #1
- Username: mizunegin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 20, 2022 7:55 pm
- Post datetime: 2022-02-25T00:44:45+00:00
- Post Title: extract Aura Kingdom (FFO) new nif models

Hello, guys.
I have made it.
I find to way to read new nifs(20.3.1.2) of aura kingdom.

Though the extracting is no convenient and perfect.

At first, complete the header, new nif has a shorten header without ",Version 20.3.1.2"

add it on a hex editor( I think this step can be optimized by modifying the source of nifskope.

And then, use the new nif.xml ( modified by me), overwrite it on the directory of nifskope
Here is the link:

[https://github.com/Amarillys/010-template](https://github.com/Amarillys/010-template)

Now, you can open it on nifskope.

In addition, I found that the color of texture is not right, how to fix it.
Thanks for reading.



color should be white as follow:
## Post #2
- Username: Airbee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 20, 2021 2:42 am
- Post datetime: 2022-03-17T13:54:46+00:00
- Post Title: extract Aura Kingdom (FFO) new nif models

Woooow epic! I was really surprised to find this new post by accident. Good work! 

The colors are like this because that is how the texture files are saved. The game then uses a shader to recolor the clothes. That way you can recolor every costume to any color you want in the game. However its hard to get it right on your own with external tools, i wish there was an easy way to get the colors like they are ingame D:
## Post #3
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2022-03-17T21:20:17+00:00
- Post Title: extract Aura Kingdom (FFO) new nif models

> Reply from Airbee ↑Thu Mar 17, 2022 9:54 pm at Thu Mar 17, 2022 9:54 pm
>
> 

I've removed your random Discord add request. Don't do that.
## Post #4
- Username: EvelienKN
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 20, 2022 3:19 am
- Post datetime: 2022-12-19T19:37:44+00:00
- Post Title: extract Aura Kingdom (FFO) new nif models

Hay 

i am also looking to extract the new models of the game
i am still missing some models after my old extracting method 
like M214.nif ,M226.nif M227.nif M228.nif  M229.nif   M230.nif  M232.nif  
M888.nif M942.nif M971.nif M970.nif M969.nif M968.nif M966.nif ... 
sorry I'm not sure how to use your files exactly iys just xml file? 
do you mind to help me with it explain it and see if I can get my missing files from it ?

M214.nif : Version ERROR
M226.nif : Version ERROR
M227.nif : Version ERROR
M228.nif : Version ERROR
M229.nif : Version ERROR
M230.nif : Version ERROR
M232.nif : Version ERROR
M888.nif : Version ERROR
M942.nif : Version ERROR
M947.nif : Version ERROR
M952.nif : Version ERROR
M954.nif : Version ERROR
M956.nif : Version ERROR
M961.nif : Version ERROR
M962.nif : Version ERROR
M964.nif : Version ERROR
M965.nif : Version ERROR
M966.nif : Version ERROR
M968.nif : Version ERROR
M969.nif : Version ERROR
M970.nif : Version ERROR
M971.nif : Version ERROR
M974.nif : Version ERROR
M975.nif : Version ERROR
M976.nif : Version ERROR
M977.nif : Version ERROR
M980.nif : Version ERROR
M981.nif : Version ERROR
M982.nif : Version ERROR
M983.nif : Version ERROR
M984.nif : Version ERROR
M985.nif : Version ERROR
M987.nif : Version ERROR
M988.nif : Version ERROR
M989.nif : Version ERROR
M990.nif : Version ERROR
M991.nif : Version ERROR
M992.nif : Version ERROR
M994.nif : Version ERROR
N434.nif : Version ERROR
N581.nif : Version ERROR
N592.nif : Version ERROR
N604.nif : Version ERROR
## Post #5
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-19T22:01:44+00:00
- Post Title: extract Aura Kingdom (FFO) new nif models

Recently, in addition to the version information in the header, a curious NIF format has begun to be adopted that has no hierarchical information about the information; Aura Kingdom 2 and Spirit Fantasia are all in that format, and it seems that Aura Kingdom is slowly changing to that file as well! Aura Kingdom is slowly changing to that file format.
## Post #6
- Username: mizunegin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 20, 2022 7:55 pm
- Post datetime: 2023-04-10T20:57:52+00:00
- Post Title: extract Aura Kingdom (FFO) new nif models

> Reply from EvelienKN ↑Tue Dec 20, 2022 3:37 am at Tue Dec 20, 2022 3:37 am
>
> 
Hay 

i am also looking to extract the new models of the game
i am still missing some models after my old extracting method 
like M214.nif ,M226.nif M227.nif M228.nif  M229.nif   M230.nif  M232.nif  
M888.nif M942.nif M971.nif M970.nif M969.nif M968.nif M966.nif ... 
sorry I'm not sure how to use your files exactly iys just xml file? 
do you mind to help me with it explain it and see if I can get my missing files from it ?

M214.nif : Version ERROR
M226.nif : Version ERROR
M227.nif : Version ERROR
M228.nif : Version ERROR
M229.nif : Version ERROR
M230.nif : Version ERROR
M232.nif : Version ERROR
M888.nif : Version ERROR
M942.nif : Version ERROR
M947.nif : Version ERROR
M952.nif : Version ERROR
M954.nif : Version ERROR
M956.nif : Version ERROR
M961.nif : Version ERROR
M962.nif : Version ERROR
M964.nif : Version ERROR
M965.nif : Version ERROR
M966.nif : Version ERROR
M968.nif : Version ERROR
M969.nif : Version ERROR
M970.nif : Version ERROR
M971.nif : Version ERROR
M974.nif : Version ERROR
M975.nif : Version ERROR
M976.nif : Version ERROR
M977.nif : Version ERROR
M980.nif : Version ERROR
M981.nif : Version ERROR
M982.nif : Version ERROR
M983.nif : Version ERROR
M984.nif : Version ERROR
M985.nif : Version ERROR
M987.nif : Version ERROR
M988.nif : Version ERROR
M989.nif : Version ERROR
M990.nif : Version ERROR
M991.nif : Version ERROR
M992.nif : Version ERROR
M994.nif : Version ERROR
N434.nif : Version ERROR
N581.nif : Version ERROR
N592.nif : Version ERROR
N604.nif : Version ERROR

Add , Version 20.3.1.2 to header


And read it with nifskope(with new nif.xml)
