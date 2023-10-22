## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-03T18:01:30+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

Hi all,

I just trying to repack texts in UPK, basically im done but i have a huge problem in text files are mixed 2 text encoding 1 is normal ASCII and other one is Unicode, i need add texts in unicode to make game support my language, however EN texts has only ASCII support and i cannot see special chars in game, I would like to replace is with unicode mark but game is crasing because of something what i missing, Can anyone please have a look??? I spend 3 days on this and i have no idea what is gets check if text is ASXII or unicode, but sure the is some check element in upk archive, just dont know what.. UPK is not that complicated format, i can really easy repack them, but problem is this stupid  lang string they are all the time mixed like unicode or ASCII not even every lang is on same level and sometimes EN is Lng nr.6 and smt. number7 it is very strange 


On the screen i maked blue unicode string, above is also many languges in normal ASCII, on the fron of each unicode string is some mark and i dont know what it is  And also it always different value on every string, very strange... If i use any of them for EN text game crashing coz i guess there is some check mechanism somewhere in UPK what is telling the game how to read it
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-03T19:33:05+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

Yeah found the solution for it, that first byte will deduct it from real size. Coz it is unicode pather will be Size / 2 - 2 bytes = first Unicode id hash, was really hard for me
## Post #3
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-04T05:32:24+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

Hello michalss.

Are you translating the game? If that is it, what is the process you are following? I am trying to force the game play english voices with any subtitles language; that way i can save size, and also, english voices are much much better than localized ones.
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-04T06:55:05+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

> Reply from montcer9012
>
> Hello michalss.

Are you translating the game? If that is it, what is the process you are following? I am trying to force the game play english voices with any subtitles language; that way i can save size, and also, english voices are much much better than localized ones.

Hi yes we are doing CZ localization. There is no proccess to follow, i simply made Text Unpacker and now im working on packer and Fonts as well. UPK is not so complicated format if you dealing with texts only, but it is paint if comes to ID's and many different checks in upk files. Same is for X360 version of game
## Post #5
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-04T07:15:38+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

Can you recommend me a work around to do what i want? If you have worked some text unpacker maybe i can change the english subtitles for desired language and that way i can have english voices with X language.

Like 3 years ago i was doing something similar with Batman Arkham Asylum, but for that one i need to Hex edit file by file and that way i will take weeks to translate the full game. Will save lot of time if i extract the strings for main UPK files, replace it and then repack the UPK file! That is what you are doing, isn't?

In case i am right on what are you doing, can you please gave your tools? That way maybe i can get what i want with Batman AO and AA
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-05T11:13:52+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

> Reply from montcer9012
>
> Can you recommend me a work around to do what i want? If you have worked some text unpacker maybe i can change the english subtitles for desired language and that way i can have english voices with X language.

Like 3 years ago i was doing something similar with Batman Arkham Asylum, but for that one i need to Hex edit file by file and that way i will take weeks to translate the full game. Will save lot of time if i extract the strings for main UPK files, replace it and then repack the UPK file! That is what you are doing, isn't?

In case i am right on what are you doing, can you please gave your tools? That way maybe i can get what i want with Batman AO and AA

Im working on packer now, fonts are done and unpacker as well. Packer will be a bit problematic but not impossible....
## Post #7
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-05T11:36:13+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

A guy on Gildor's forum make a .upk repacker but it seems that only works for certain games. At least doesn't work for BAA. I already try to contact him, waiting for response.

Here is the post:
[http://www.gildor.org/smf/index.php/top ... l#msg13432](http://www.gildor.org/smf/index.php/topic,267.msg13432.html#msg13432)
## Post #8
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-13T09:15:14+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

Sorry for interput.
FF FF FF/ xx FF FF in SoundNodeWave means, that string is in Little Endian, it's reversed bytes, similiar to other codings. 
FF FF FF in Hex means minus. You need to calculate absolute value and multiply by 2, because it take more space to place a one char. In ASCII you will have for example 7A, in Little Endian it will be 7A 00, but remember, it's revered, so for example char "ż" 01 7C will be 7C 01 (you can see in hex). But everyone prefers to calculate real size from previous pointer, if I remember correctly it will be 94 in your file.
To calculate new size, you can simply write Python script like out.write(struct.pack("<i", -len(txt[e])/2)).
Rember, ASCII only have 255 chars and only strings in that range will be placed as ASCII in SoundNodeWave. Any others will be in Little Endian.
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-13T10:55:44+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

> Reply from GimmyBreaker
>
> Sorry for interput.
FF FF FF/ xx FF FF in SoundNodeWave means, that string is in Little Endian, it's reversed bytes, similiar to other codings. 
FF FF FF in Hex means minus. You need to calculate absolute value and multiply by 2, because it take more space to place a one char. In ASCII you will have for example 7A, in Little Endian it will be 7A 00, but remember, it's revered, so for example char "ż" 01 7C will be 7C 01 (you can see in hex). But everyone prefers to calculate real size from previous pointer, if I remember correctly it will be 94 in your file.
To calculate new size, you can simply write Python script like out.write(struct.pack("<i", -len(txt[e])/2)).
Rember, ASCII only have 255 chars and only strings in that range will be placed as ASCII in SoundNodeWave. Any others will be in Little Endian.

Well it is already done and if you would read the my second post it is there, but thank you for input  BTW i'm converting all my strings from ASCII to Unicode as standart all works as expected
## Post #10
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-13T11:32:27+00:00
- Post Title: Batman Arkam Origins TEXT **HELP**

That is why I say "Sorry for interput."   
I deduct from your post, that you don't really know all, because Unicode have a lot of implementations.
In case of Unreal Engine, we have to be precisely, utf-16le is not not utf-8, but both are Unicode. 
And yes, changing all strings to little endian is a perfect way to do this. It's doesn't matter for Engine what type of coding is used (ASCII or Little Endian).
I only wanted to clear everything.
So, good luck, if you will have any problems, contact with me via PM, I've once wrote Python script for American McGee's Grimm, but never had enough time to finish
