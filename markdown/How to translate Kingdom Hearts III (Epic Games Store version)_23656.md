## Post #1
- Username: Khrn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 30, 2021 10:03 pm
- Post datetime: 2021-03-30T14:06:50+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

Hey everyone.

Is there a known way to translate Kingdom Hearts III? I know it just got released, but as it's an Unreal Engine 4 game, I'm wondering if there's any method that we could already try.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-30T17:38:48+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

What files do this game have? Can you attach some samples?

Did you try to search for texts using total commander method?
[https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)


There are some quickbms scripts for UE4, did you try them?
## Post #3
- Username: Khrn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 30, 2021 10:03 pm
- Post datetime: 2021-03-30T23:21:33+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

> Reply from ikskoks ↑Wed Mar 31, 2021 1:38 am at Wed Mar 31, 2021 1:38 am
>
> 
What files do this game have? Can you attach some samples?

Did you try to search for texts using total commander method?
https://ikskoks.pl/searching-text-strin ... commander/


There are some quickbms scripts for UE4, did you try them?

I don't know what I can attach to avoid piracy, so I'll list a few of them below. I'm avoiding a few that are obviously not text, like images. I tried Total Commander but it didn't find anything. I don't know anything about quickbms, though, so would you mind sharing more?

> pakchunk0-WindowsNoEditor.pak
>
> other similar pak files
>
> mv_memory_ep1.usm (and other similar ones, seem like movie files)
>
> initial_player.bin
>
> conditional_load.bin
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-31T07:11:14+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

Here are some scripts and tools [https://zenhax.com/viewtopic.php?f=9&t= ... 251#p56251](https://zenhax.com/viewtopic.php?f=9&t=1005&p=56251#p56251)

And here is quickbmms page [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)


Also you will probably need a AES key for this PAK file. There are some sites that collects such keys.
You can google it to find it.
## Post #5
- Username: Khrn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 30, 2021 10:03 pm
- Post datetime: 2021-03-31T16:11:28+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

> Reply from ikskoks ↑Wed Mar 31, 2021 3:11 pm at Wed Mar 31, 2021 3:11 pm
>
> 
Here are some scripts and tools https://zenhax.com/viewtopic.php?f=9&t= ... 251#p56251

And here is quickbmms page http://aluigi.altervista.org/quickbms.htm


Also you will probably need a AES key for this PAK file. There are some sites that collects such keys.
You can google it to find it.
Alright, so it seems the text is inside some locres files. Do you know how to open them?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-31T16:17:48+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

Yeah, there are some locres tools on zenhax, for example [https://zenhax.com/viewtopic.php?t=1022](https://zenhax.com/viewtopic.php?t=1022)
## Post #7
- Username: Khrn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 30, 2021 10:03 pm
- Post datetime: 2021-03-31T18:31:24+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

> Reply from ikskoks ↑Thu Apr 01, 2021 12:17 am at Thu Apr 01, 2021 12:17 am
>
> 
Yeah, there are some locres tools on zenhax, for example https://zenhax.com/viewtopic.php?t=1022

Thank you! Last question: according to [this](https://cs.rin.ru/forum/viewtopic.php?f=30&t=103030) (not sure if it's the best way to reimport, so please let me know if there's another one), I need to know the specific UE4 version the game is using. However, the Details tab doesn't show it. Do you know how I can find it?
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-31T20:41:06+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

I have never done it this way. Some games are working fine with unpacked files or in some cases you can probably use reimport mode from quickbms (read more here [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt))

But your method can also work, maybe someone else will know how to help you find version number.
## Post #9
- Username: Khrn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 30, 2021 10:03 pm
- Post datetime: 2021-03-31T21:13:56+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

> Reply from ikskoks ↑Thu Apr 01, 2021 4:41 am at Thu Apr 01, 2021 4:41 am
>
> 
I have never done it this way. Some games are working fine with unpacked files or in some cases you can probably use reimport mode from quickbms (read more here http://aluigi.zenhax.com/papers/quickbms.txt)

But your method can also work, maybe someone else will know how to help you find version number.

I tried using the reimport.bat file and got this error right at the beginning:

> Error: incomplete input file 0: E:\Games\KH_3\KINGDOM HEARTS III\Content\Paks\test\Engine\Config\Android\AndroidEngine.ini
>
>        Can't read 1986886205 bytes from offset 6f427567.
>
>        Anyway don't worry, it's possible that the BMS script has been written
>
>        to exit in this way if it's reached the end of the archive so check it
>
>        or contact its author or verify that all the files have been extracted.
>
>        Please check the following coverage information to know if it's ok.
>
> 
>
>   coverage file 0     3%   57         1739       . offset 6f427567
>
> 
>
> Last script line before the error or that produced the error:
>
>   103 log MEMORY_FILE10 OFFSET SIZE
I never opened "AndroidEngine.ini" though. What can I do? I used the same BMS file to export the file.
## Post #10
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-31T23:02:43+00:00
- Post Title: How to translate Kingdom Hearts III (Epic Games Store version)

I'm not sure how to help you with error to be honest, sorry.
You have to make some investigation on this.
