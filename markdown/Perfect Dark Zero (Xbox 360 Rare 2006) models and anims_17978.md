## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-04-15T17:49:26+00:00
- Post Title: Perfect Dark Zero (Xbox 360 Rare 2006) models and anims

Hey, everyone! I was looking through the files of an old classic for the 360 and was wondering if there was any way, shape or form to extract the models, textures and possibly animations of the characters, weapons, vehicles and props. All this data must be stored in the .pkg files from within ASSETS\PackageData. I'll upload some samples for use here:
[https://www.dropbox.com/s/3zffkwpkcowko ... s.rar?dl=0](https://www.dropbox.com/s/3zffkwpkcowkoes/Perfect%20Dark%20Zero%20.pkg%27s.rar?dl=0)
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-04-17T08:42:49+00:00
- Post Title: Perfect Dark Zero (Xbox 360 Rare 2006) models and anims

*bump* Help, please
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-17T14:28:32+00:00
- Post Title: Perfect Dark Zero (Xbox 360 Rare 2006) models and anims

At least this BMS script can help you decompress the files:

```
get Zsize asize
set Size long Zsize
math Size * 20
get Name basename
string Name + ".bin"
clog Name 0 Zsize Size
```

Two heads from 389823538.pkg:



heads.jpg (199.78 KiB) Viewed 222 times


Problem is getting the UVs.
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-04-17T14:38:13+00:00
- Post Title: Perfect Dark Zero (Xbox 360 Rare 2006) models and anims

> Reply from Bigchillghost
>
> At least this BMS script can help you decompress the files:
Code: Select allcomtype zlib
get Zsize asize
set Size long Zsize
math Size * 20
get Name basename
string Name + ".bin"
clog Name 0 Zsize Size
Two heads from 389823538.pkg:
heads.jpg
Problem is getting the UVs.

Thank you so much! I'm looking forward to a follow-up in getting the textures and other content! You're a life saver!
## Post #5
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-04-20T22:26:12+00:00
- Post Title: Perfect Dark Zero (Xbox 360 Rare 2006) models and anims

Anything new lately? Could you explain how to get the models and textures extracted step by step when you figure it out?
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-21T04:12:21+00:00
- Post Title: Perfect Dark Zero (Xbox 360 Rare 2006) models and anims

> Reply from Pepsee
>
> Anything new lately?
I wouldn't say so.  

> Reply from Pepsee
>
> Could you explain how to get the models and textures extracted step by step when you figure it out?
Sorry but I have no time teaching every newbie step by step every time they put a new request. You have to learn things yourself. Check the tutorial from the link of my signature.
## Post #7
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-01-17T03:10:08+00:00
- Post Title: Perfect Dark Zero (Xbox 360 Rare 2006) models and anims

Someone ripped Joanna's default outfit on Facepunch some years ago apparently but now the forums have closed, so would anyone here still happen to have it here? It would be really appreciated if anyone still did, thanks!
## Post #8
- Username: SSBMagy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 22, 2021 6:09 pm
- Post datetime: 2021-07-22T10:24:14+00:00
- Post Title: Perfect Dark Zero (Xbox 360 Rare 2006) models and anims

Updates? If not I guess I'll have to read those guides and spend a good year learning how to do this myself. Lmfao
## Post #9
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-07-24T16:42:56+00:00
- Post Title: Perfect Dark Zero (Xbox 360 Rare 2006) models and anims

> Reply from SSBMagy ↑Thu Jul 22, 2021 6:24 pm at Thu Jul 22, 2021 6:24 pm
>
> 
Updates? If not I guess I'll have to read those guides and spend a good year learning how to do this myself. Lmfao

Sadly, I don't think much insight will be given on this. Maybe one day tho..
