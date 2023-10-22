## Post #1
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-03-26T02:24:05+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

No information about this game and how to dump it, any help? thanks! samples: [https://www.mediafire.com/file/u08ke904 ... A.zip/file](https://www.mediafire.com/file/u08ke9043pitoq8/DATA.zip/file)
## Post #2
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-03-28T19:02:43+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

Any help? QuickBMS script? anything related.
## Post #3
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-03-31T18:00:07+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

found out that this game uses Vicious Engine which Ben 10 Ultimate Alien: Cosmic Destruction and Robotech Battlecry uses, Is there a script for Ben 10 or Robotech to unpack the .PAK? maybe shakotay2 knows?
## Post #4
- Username: techtechi
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-31T20:55:13+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

There is one script (listed on the wiki), but it probably won't work for you, because
file format for this game seems to be different than other games I have seen so far.
[http://wiki.xentax.com/index.php/Vicious_Engine_Archive](http://wiki.xentax.com/index.php/Vicious_Engine_Archive)

Edit: I've found some more games using this "data.pak" format, so I've updated the article.
## Post #5
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-04-01T01:38:35+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

I take a look superficialy, and did not find a logical offset.

my finds



00000000.png (25.07 KiB) Viewed 113 times





there has 3 pngs files in the pak, so i get all size of them separetely and search in the pak.

and i found the size of them here



Maybe someone can understand how it works the chunk math to get the offsets and filenames.
## Post #6
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-04-01T04:45:10+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

> Reply from ikskoks ↑Fri Apr 01, 2022 4:55 am at Fri Apr 01, 2022 4:55 am
>
> 
There is one script (listed on the wiki), but it probably won't work for you, because
file format for this game seems to be different than other games I have seen so far.
http://wiki.xentax.com/index.php/Vicious_Engine_Archive

Edit: I've found some more games using this "data.pak" format, so I've updated the article.

I have used the Spy vs Spy script didn't work that well.
## Post #7
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-01T18:34:12+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

It's because this file has different format - a little more complex ... more like VHD (files and directory structure). Dunno how to write Bms, but everything you need is in SubHeader (files names, folder names, sizes, offsets etc.). File Header holds basic info about SubHeader. Also, I don't think this file is compressed.
## Post #8
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-04-01T20:11:42+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

> Reply from VendorX ↑Sat Apr 02, 2022 2:34 am at Sat Apr 02, 2022 2:34 am
>
> 
It's because this file has different format - a little more complex ... more like VHD (files and directory structure). Dunno how to write Bms, but everything you need is in SubHeader (files names, folder names, sizes, offsets etc.). File Header holds basic info about SubHeader. Also, I don't think this file is compressed.

its not compressed.

Need to understand the pattern of chunks math of offset, size seems to be easy and not math on it.
## Post #9
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-02T11:23:53+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

... that's why iv'e posted some basic info.

- Header
    - SubHeader Size
    - Name List Relative Offset (Names of Files/Folders in Base Directory)
    - Dunno (Boolean?)
    - SubHeader Offset

- SubHeader
    - Info Block (numbers of files/folders structs)
        - Files Info (holds file size)
        - Foldes Info (holds number of structs ( files / folders))

- Names (SubHeader Offset + Name List Relative Offset)
- Folders Data Info (depends what holds Info Block, content can differ. Each directory can hold info about files/subdirectories)

- Data (SubHeader Offset + SubHeader Size + padding)
    Note: Padding is used for some blocks if the data size is smaller than multiple of min sector size (probably 1024 in this case)
## Post #10
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-04-18T18:44:55+00:00
- Post Title: Dead Head Fred (PSP) [.PAK] [Vicious Engine]

Anyone found anything yet? I've yet to find an unpacker for .pak
