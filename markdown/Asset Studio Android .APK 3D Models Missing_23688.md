## Post #1
- Username: DragonKris
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 06, 2018 8:24 am
- Post datetime: 2021-04-05T00:50:01+00:00
- Post Title: Asset Studio Android .APK 3D Models Missing

Hey does anyone know the reason as to why when I decompile a mobile .apk Android game that I only see a very few of the 3D models when I import the .Assets files or the whole game folder into Asset Studio and I don’t see any other 3D models except for 3 character 3D models but every other 3D model in the game is missing in the Assets tab of the Asset Studio? (The game is made on the Unity mobile engine)
## Post #2
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-05T10:06:42+00:00
- Post Title: Asset Studio Android .APK 3D Models Missing

Either your data is being stored in the .obb or in a cache folder. Thats why your missing assets.
## Post #3
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-04-05T11:02:22+00:00
- Post Title: Asset Studio Android .APK 3D Models Missing

> Reply from DragonKris ↑Mon Apr 05, 2021 8:50 am at Mon Apr 05, 2021 8:50 am
>
> 
Hey does anyone know the reason as to why when I decompile a mobile .apk Android game that I only see a very few of the 3D models when I import the .Assets files or the whole game folder into Asset Studio and I don’t see any other 3D models except for 3 character 3D models but every other 3D model in the game is missing in the Assets tab of the Asset Studio? (The game is made on the Unity mobile engine)

I suggest you to install the .apk ( especially if it this to small for containing data), also for getting latest update.

Then there are different way the assets could be stored:
if the downloaded .apk is small then you need to find in cache or .obb 
if the downloaded  .apk is big , the assets are inside it ( a lot of chinese mobile game use this method). 

Sometimes games combine these types of storage so for example you got the base version in one big .apk and updates in .obb or in cache(data), so I suggest you to look in every path I mention below.

Generally you will find assets in one of those paths :

-SdCard/Android/Data
-SdCard/Android/OBB
-Data/app ( generally game storing assets in big .apk use this path)
-Data/data ( very uncommon) .
## Post #4
- Username: DragonKris
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 06, 2018 8:24 am
- Post datetime: 2021-04-05T22:09:41+00:00
- Post Title: Asset Studio Android .APK 3D Models Missing

Thanks that’s where they were at.
