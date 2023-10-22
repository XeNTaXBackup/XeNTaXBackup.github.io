## Post #1
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-02-17T10:32:26+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

Can anyone help me how to open a file with a .bof extension and a game data archive to extract game resources.
[](https://fastpic.ru/view/114/2021/0217/1ef0d5c7023208ba010e328812d37c2d.jpg.html)
[](https://fastpic.ru/view/114/2021/0217/6bad211cbd0db5187729cf4cb59d59e0.jpg.html)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-17T11:59:10+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

Can you upload some samples?
## Post #3
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-02-26T07:27:17+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

> Reply from ikskoks ↑Wed Feb 17, 2021 7:59 pm at Wed Feb 17, 2021 7:59 pm
>
> 
Can you upload some samples?

Download Link :[https://disk.yandex.ru/d/2796SbpWyQwcUw](https://disk.yandex.ru/d/2796SbpWyQwcUw)
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-26T08:50:53+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

As for gamedata it has many files compressed with ZLIB.
You can get the data with offzip [https://aluigi.altervista.org/mytoolz/offzip.zip](https://aluigi.altervista.org/mytoolz/offzip.zip)

```
offzip.exe -a gamedata out_directory
```


As for BOF file, data are not compressed, you can edit text by hex editor
or write a simple extractor for this
[https://i.imgur.com/HmZFmlX.png](https://i.imgur.com/HmZFmlX.png)
## Post #5
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-02-26T10:16:45+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

> Reply from ikskoks ↑Fri Feb 26, 2021 4:50 pm at Fri Feb 26, 2021 4:50 pm
>
> 
As for gamedata it has many files compressed with ZLIB.
You can get the data with offzip https://aluigi.altervista.org/mytoolz/offzip.zip
Code: Select alloffzip.exe -a gamedata out_directory

As for BOF file, data are not compressed, you can edit text by hex editor
or write a simple extractor for this
https://i.imgur.com/HmZFmlX.png
Thank you unpacked. I got such files below I reinforced. How can I unpack each file so that it is in an understandable format like jpg to edit and pack back. Any ideas?
[Screenshot_6.jpg](https://xentaxbackup.github.io/file/19605_Screenshot_6.jpg)
## Post #6
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-02-26T10:27:09+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

In general, the idea is to translate the game into Russian, but I understand that the text cannot be translated through the hexadecimal editor.
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-26T14:00:54+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

As for graphics, there is a way to view them in rawtex
[https://i.imgur.com/SEziBFz.png](https://i.imgur.com/SEziBFz.png)
[https://i.imgur.com/egZJfGI.png](https://i.imgur.com/egZJfGI.png)
But to edit them, you would need to know file format of those VAP files and also have a custom tool for that.

As for packing gamedata, you could use reimport mode of offzip

```
-r       reimport mode that works EXACTLY like in QuickBMS
```

So please read quickbms documentation to know how to use this mode.

As for texts, you have two options here, translate in hex editor or write a custom text exporter and importer.
## Post #8
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-03-01T06:45:16+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

> Reply from ikskoks ↑Fri Feb 26, 2021 10:00 pm at Fri Feb 26, 2021 10:00 pm
>
> 
As for graphics, there is a way to view them in rawtex
https://i.imgur.com/SEziBFz.png
https://i.imgur.com/egZJfGI.png
But to edit them, you would need to know file format of those VAP files and also have a custom tool for that.

As for packing gamedata, you could use reimport mode of offzip
Code: Select all-r       reimport mode that works EXACTLY like in QuickBMS
So please read quickbms documentation to know how to use this mode.

As for texts, you have two options here, translate in hex editor or write a custom text exporter and importer.

Thank you very much for your help. When dragging a file onto Rawtex, the texture is automatically converted to dds. As I understand it, in theory, dds can be driven back into vap format
## Post #9
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-01T08:23:27+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

Yeah, but that would probably require some manual work like recreating VAP header.
Also, you must be 100% sure that file format is correct.
## Post #10
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-03-01T08:58:55+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

> Reply from ikskoks ↑Mon Mar 01, 2021 4:23 pm at Mon Mar 01, 2021 4:23 pm
>
> 
Yeah, but that would probably require some manual work like recreating VAP header.
Also, you must be 100% sure that file format is correct.

Thank you. Another question - I will translate the text through a hex editor from English into Russian. Will the game see the Russian font or will it be necessary to do some manipulations?
## Post #11
- Username: DENver666
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-01T10:15:15+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

That depends. If default font supports cyryllic characters, then game will show them properly.
But if it doesn't  then you would need to modify game font first.
## Post #12
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-03-21T09:02:08+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

> Reply from ikskoks ↑Mon Mar 01, 2021 6:15 pm at Mon Mar 01, 2021 6:15 pm
>
> 
That depends. If default font supports cyryllic characters, then game will show them properly.
But if it doesn't  then you would need to modify game font first.

As expected, the game does not see the cyrillic when I replace the text in the game with question marks. How can the game be friends with the cyrillic?
## Post #13
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-21T09:55:32+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

I told you that you need to modify game font if your characters aren't supported by default.
## Post #14
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-03-21T10:08:44+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

> Reply from ikskoks ↑Sun Mar 21, 2021 5:55 pm at Sun Mar 21, 2021 5:55 pm
>
> 
I told you that you need to modify game font if your characters aren't supported by default.

Can I change the font of the game through notepad ++ or do you need to write some special utility?
## Post #15
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-21T10:13:33+00:00
- Post Title: Scott Pilgrim vs. The World (PC) - Help Extracting?

That depends on the game. Some games are using standard formats like TTF or DDS and you can edit them with tools that already exists
[https://ikskoks.pl/poradnik-8-edycja-cz ... -oraz-dds/](https://ikskoks.pl/poradnik-8-edycja-czcionek-w-formacie-ttf-oraz-dds/)

But some games are using custom fonts and to edit them you need to reverse engineer file format and then write a custom tool.
Here are some tuts explaining whole process [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #16
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-03-21T11:50:22+00:00
- Post Title: Re: Scott Pilgrim vs. The World (PC) - Help Extracting?

> Reply from ikskoks ↑Sun Mar 21, 2021 6:13 pm at Sun Mar 21, 2021 6:13 pm
>
> 
That depends on the game. Some games are using standard formats like TTF or DDS and you can edit them with tools that already exists
https://ikskoks.pl/poradnik-8-edycja-cz ... -oraz-dds/

But some games are using custom fonts and to edit them you need to reverse engineer file format and then write a custom tool.
Here are some tuts explaining whole process viewtopic.php?f=29&t=22266

And what is the fnt resolution and how to open it. Opened dds through photoshop. There the font is normal and in some places not. As I understand it, if I replace everything there with Russian, will it work for me?
[Screenshot_3.jpg](https://xentaxbackup.github.io/file/19765_Screenshot_3.jpg)
## Post #17
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-21T13:27:02+00:00
- Post Title: Re: Scott Pilgrim vs. The World (PC) - Help Extracting?

> As I understand it, if I replace everything there with Russian, will it work for me?

If you'll do it correctly and also adjust characters in the text files, then yes.
## Post #18
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-03-22T03:56:28+00:00
- Post Title: Re: Scott Pilgrim vs. The World (PC) - Help Extracting?

> Reply from ikskoks ↑Sun Mar 21, 2021 9:27 pm at Sun Mar 21, 2021 9:27 pm
>
> 
As I understand it, if I replace everything there with Russian, will it work for me?

If you'll do it correctly and also adjust characters in the text files, then yes.

Thanks for the help. What I figured out to do with dds. But next to them with the same name are files with the extension .fnt. How can I open them?
## Post #19
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-22T08:15:41+00:00
- Post Title: Re: Scott Pilgrim vs. The World (PC) - Help Extracting?

You need to upload some samples, because there are a lot of games usinng FNT extension and each file can be different.
In most cases it should  contain mapping for characters (ID, width, height, PosX, PosY etc.)
## Post #20
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2021-03-22T09:53:48+00:00
- Post Title: Re: Scott Pilgrim vs. The World (PC) - Help Extracting?

> Reply from ikskoks ↑Mon Mar 22, 2021 4:15 pm at Mon Mar 22, 2021 4:15 pm
>
> 
You need to upload some samples, because there are a lot of games usinng FNT extension and each file can be different.
In most cases it should  contain mapping for characters (ID, width, height, PosX, PosY etc.)

Downloaded. You may be able to open. Only these files are left.
[https://disk.yandex.ru/d/ROFn-RP6kSzZrg](https://disk.yandex.ru/d/ROFn-RP6kSzZrg)
## Post #21
- Username: skies
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 24, 2021 7:49 am
- Post datetime: 2021-11-23T23:54:05+00:00
- Post Title: Re: Scott Pilgrim vs. The World (PC) - Help Extracting?

What's the conclusion to all of this? I want to reskin some of the characters, is this thread the answer?
## Post #22
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2022-02-15T10:09:00+00:00
- Post Title: Re: Scott Pilgrim vs. The World (PC) - Help Extracting?

It didn't work out
