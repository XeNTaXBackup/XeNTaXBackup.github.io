## Post #1
- Username: elybelbely
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 05, 2018 9:27 pm
- Post datetime: 2018-07-14T19:34:46+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

Hi. I translated hellblade: senua's sacrifice. there was a .pak file in the game. so I unpacked that file and paste the unpacked to game directory and removed .pak file completely. and then translated the subtitle file in localization folder. everything is working fine but in unpacked version of the game, the game is much slower in loading and there is lag in game. beside that I want to give the translated version of the game to my friends. but now I have to give the unpacked version that is too big. is there any way to solve these problems?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-07-14T21:24:14+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

Only by packing everything to pak file.
## Post #3
- Username: elybelbely
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 05, 2018 9:27 pm
- Post datetime: 2018-07-15T05:53:11+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

> Reply from ikskoks
>
> Only by packing everything to pak file.

Is there any tool for packing the files?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-07-15T07:02:21+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

Maybe reimport option for this script will work fine [http://aluigi.org/bms/unreal_tournament_4.bms](http://aluigi.org/bms/unreal_tournament_4.bms)
## Post #5
- Username: elybelbely
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 05, 2018 9:27 pm
- Post datetime: 2018-07-15T08:21:56+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

> Reply from ikskoks
>
> Maybe reimport option for this script will work fine http://aluigi.org/bms/unreal_tournament_4.bms

I have no idea how to use .bms script! as u can see in my profile: ultra-noob xD
is there any help for me?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-07-15T09:24:46+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

There are some tutorials about that. For example [https://www.youtube.com/watch?v=xZONf5fXEOg](https://www.youtube.com/watch?v=xZONf5fXEOg)

It is also good idea to read quickbms readme [http://aluigi.altervista.org/papers/quickbms.txt](http://aluigi.altervista.org/papers/quickbms.txt)
In section 3 you have information about reimporting.
## Post #7
- Username: elybelbely
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 05, 2018 9:27 pm
- Post datetime: 2018-07-15T11:22:07+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

i found a way to reading my edited localization file outside the .pak file.
I paste just my language file in the gamedirectory/HellbladeGame/Content/Localization/Game/xentax
then i went to Engine.ini in drive C and wrote this:

```
Culture=xentax

```


now the game is reading my texts without any problem except the font. i want to load my own font but i dont know what to write in Engine.ini or sth like this to load my new font that I want to load exactly like i did for texts.
## Post #8
- Username: elybelbely
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 05, 2018 9:27 pm
- Post datetime: 2018-07-15T16:48:55+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

> Reply from ikskoks
>
> There are some tutorials about that. For example https://www.youtube.com/watch?v=xZONf5fXEOg

It is also good idea to read quickbms readme http://aluigi.altervista.org/papers/quickbms.txt
In section 3 you have information about reimporting.

I extracted the pak file now I want to import it but I dont know what to do now:

```
  - remember to select the SAME script, file and folder you selected during
    the previous extraction
  - it's highly suggested to leave only the edited files in the folder, it's
    faster and less prone to errors with compressed files

- open input file H:\Games\Hellblade Senuas Sacrifice\HellbladeGame\Content\Paks\HellbladeGame-WindowsNoEditor.pak

- the file is bigger than 4 gigabytes so it's NOT supported by quickbms.exe,
  I suggest you to answer 'n' to the following question and using
  quickbms_4gb_files.exe that doesn't have such limitation.
  are you sure you want to continue anyway (y/N)?
  y
- open script C:\Users\TRACE\Desktop\unreal_tournament_4.bms
- set output folder E:\New folder

  offset   filesize   filename
--------------------------------------
The archive is encrypted, select the number of the key to use or type yours:
0: KIWIKIWIKIWIKIWIKIWIKIWIKIWIKIWI
1: _aS4mfZK8M5s5KWC2Lz2VsFnGKI7azgl
2: bR!@nbR0wnc@rychR!$d@nd@v3d3R3kj!mj0$hk3v!nm!ch@3lm!k3s3@nst3v3t!m
3: casd#55@#$%323!$^#b%05sa5W|hhaf4365s52ss51|55m!|{55s^@@36f233|-|0w@%3g8hssDk35/!Nm|_|%ds23%a32d5&23as3%12p|-|y$t3ds562d23fav3c@dyw38#49
4: C8C4847F3B4FA52D4AAD57A52358CDBC
5: k14z0ZLR8a7jNm49uyBzxXYY9LpTHcehLSNiC3jAkzBsffPuy8YsTa72RLD9KWIn
6: E7@[dZfoYCW;+YWR;0JK^{9tt:yU0_T&
7: E1A1F2E4AA066C54BD5090F463EDDF58D01684243672B3CE809FF47FF473B04A
8: I0vV6wr0TFbg3m23QuSIwnYC1sI0AIDq
9: y298qjSb115NqQ3Agad30DWn2QYrTI8CT6aP05l2PBV9Qe92S94PdoVCCy06A38L
10: b9uW0RKNY91be8HN3Lemi68j6Xsi2l7fQJYsp5oR4al4C4c9kY5E0l90411l9P3L
11: 45DD15D6DD2DA50AEB71CE7A5284CF8EA498B2EC3D52B7E336F3EA0071CE44B3
12: MRZpemumg6t2AXExrMQs6TSoZRG+YSABK338oc6F8kTXu4k6QffJgYAzKl65Tk2L
13: 0x9D8C9A4A4FA082F213EED604B6E756237181685EEDA82216437617D7AA5231AF
14: press RETURN for no encryption (Lineage 2 Revolution)

- please insert the content for the variable KEY:

```
## Post #9
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-07-15T19:00:29+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

As you can see, there is message "please insert the content for the variable KEY:"
You have 13 keys implemented inside this script, so if you are lucky one of them should be the right one. Just type the number of the key, for example "5".
## Post #10
- Username: elybelbely
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 05, 2018 9:27 pm
- Post datetime: 2018-07-16T06:35:18+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

> Reply from ikskoks
>
> As you can see, there is message "please insert the content for the variable KEY:"
You have 13 keys implemented inside this script, so if you are lucky one of them should be the right one. Just type the number of the key, for example "5".

tnx. Actually the problem was that the importer was working with under 4g version of the quickbms. I deleted that file and renamed the more than 4g version to formal name of under 4g version. and tried again. everything was ok and worked. tnx for your helps my friends.
## Post #11
- Username: kamtesel17
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 05, 2019 6:33 am
- Post datetime: 2019-09-25T09:33:41+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

hi
any update for gears 5 (gears of war 5)?
it gave you the error.
## Post #12
- Username: Aneh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 01, 2020 6:33 pm
- Post datetime: 2020-10-01T10:35:48+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

> Reply from ikskoks ↑Mon Jul 16, 2018 3:00 am at Mon Jul 16, 2018 3:00 am
>
> 
As you can see, there is message "please insert the content for the variable KEY:"
You have 13 keys implemented inside this script, so if you are lucky one of them should be the right one. Just type the number of the key, for example "5".

If i have tried 13 keys but the all keys is not work, then how to open that file? Sorry for my bad english
## Post #13
- Username: Aneh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 01, 2020 6:33 pm
- Post datetime: 2020-10-01T10:39:12+00:00
- Post Title: Unreal Engine 4: Read files outside the pak file

> Reply from elybelbely ↑Mon Jul 16, 2018 2:35 pm at Mon Jul 16, 2018 2:35 pm
>
> 
ikskoks wrote:As you can see, there is message "please insert the content for the variable KEY:"
You have 13 keys implemented inside this script, so if you are lucky one of them should be the right one. Just type the number of the key, for example "5".

tnx. Actually the problem was that the importer was working with under 4g version of the quickbms. I deleted that file and renamed the more than 4g version to formal name of under 4g version. and tried again. everything was ok and worked. tnx for your helps my friends.

What do you mean bro ? Please help me, i'm have the same problem too . Sorry for my bad english
