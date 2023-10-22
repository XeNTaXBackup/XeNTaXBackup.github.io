## Post #1
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2013-03-23T17:45:50+00:00
- Post Title: Unreal Engine (PS3, X360) .XXX

I'm creating this topic to ask for your help on this extension, as many know, the Unreal Games use this extension *.XXX (ps3/xbox) instead of *.Upk, the PC version, and there is a tool that extracts content (texts) version *.Upk. Then I wonder if there is a tool for extension the PS3/Xbox (xxx), as various games like: Dishonored, Alice Madness Returns, has his texts in these files, I appreciate the help.

@Edit:
I used the decompressor Gildor, but only Alice has more than 100 files .XXX for editing.

I saw that the pointers calculate the same way in every game.
## Post #2
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2013-03-24T13:56:30+00:00
- Post Title: Unreal Engine (PS3, X360) .XXX

Anyone knows? Please, there are so many games to translate, but is complicated with these files.
## Post #3
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2013-03-24T16:14:52+00:00
- Post Title: Unreal Engine (PS3, X360) .XXX

> Reply from xujozer
>
> I saw that the pointers calculate the same way in every game.
Nop.
See this site.
http://wiki.beyondunreal.com/Legacy:Package_File_Format
This information is a thing of old UE. However, the format of UE3 is alike.
UPK has a header and three information tables.It is necessary to read these correctly.
But these formats are customized by the version in many cases.
Information called Export-Table is important.Data position of the contents in a UPK file is indicated here.
Process of unpack and repack is very simple.
In unpack, each contents are written out to the file using this information.
In repack, a file is merged in order and this information is rewritten.

Contents can be replaced by rewriting Export-Table using a Hex editor.
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-24T17:51:46+00:00
- Post Title: Unreal Engine (PS3, X360) .XXX

> Reply from delutto
>
> xujozer wrote:I saw that the pointers calculate the same way in every game.
Nop.
See this site.
http://wiki.beyondunreal.com/Legacy:Package_File_Format
This information is a thing of old UE. However, the format of UE3 is alike.
UPK has a header and three information tables.It is necessary to read these correctly.
But these formats are customized by the version in many cases.
Information called Export-Table is important.Data position of the contents in a UPK file is indicated here.
Process of unpack and repack is very simple.
In unpack, each contents are written out to the file using this information.
In repack, a file is merged in order and this information is rewritten.

Contents can be replaced by rewriting Export-Table using a Hex editor.

Every UDK build on every game is different, only compression is same all the time...
