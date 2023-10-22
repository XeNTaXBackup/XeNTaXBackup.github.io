## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-05-24T02:52:09+00:00
- Post Title: Call Of Juarez Gunslinger XWB

Hello is it possible to modify xactextract to work with version 44 of xwb archive little endian?

I can access the source code but not sure what to change.

Thanks.
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-05-25T21:28:39+00:00
- Post Title: Call Of Juarez Gunslinger XWB

unxwb works fine for me. just need to use the dead island vlc batch file afterwords.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-05-25T22:48:14+00:00
- Post Title: Call Of Juarez Gunslinger XWB

But unxwb doesn't extract the files with there names from the table.
## Post #4
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-06-01T19:03:29+00:00
- Post Title: Call Of Juarez Gunslinger XWB

> Reply from OrangeC
>
> But unxwb doesn't extract the files with there names from the table.

Yeah we need a .xsb file to at least list the names of the sounds ( according to unxwb help ) but I don't know how to do that. I'm downloading XACT just by curiosity but I wonder why there is no .xsb files with .xwb ones. If anyone have a better idea, tell us please.
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-06-02T01:19:49+00:00
- Post Title: Call Of Juarez Gunslinger XWB

if you look in a hex editor in a xwb file there is a table with there names. I thought the XSB has been merged with the xwb file.
## Post #6
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-06-02T08:41:12+00:00
- Post Title: Call Of Juarez Gunslinger XWB

> Reply from OrangeC
>
> if you look in a hex editor in a xwb file there is a table with there names. I thought the XSB has been merged with the xwb file.

I know I already try this and it didn't work. Now, maybe I made a mistake in the offset: "-b N OFF, N is the name of the XSB containing the names of the XWB audio files and OFF is the offset where these names start"
## Post #7
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-06-22T19:08:50+00:00
- Post Title: Call Of Juarez Gunslinger XWB

> Reply from Vosvoy
>
> OrangeC wrote:if you look in a hex editor in a xwb file there is a table with there names. I thought the XSB has been merged with the xwb file.

I know I already try this and it didn't work. Now, maybe I made a mistake in the offset: "-b N OFF, N is the name of the XSB containing the names of the XWB audio files and OFF is the offset where these names start"
Because that assumes an xsb file with files at that offset. this is a new custom xwb, same as dead island uses, that stores the file names in the xwb in a method not like that of the xsb. I'd just extract the xwb with unxwb using the decimal names option (instead of hex names) and then go down the list and copy paste the names onto the files. it's the same order. (unless you use the hex option default, which means you'll have to know the order of the hex valued names)
## Post #8
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-06-22T21:14:02+00:00
- Post Title: Call Of Juarez Gunslinger XWB

> Reply from Pepper
>
> Because that assumes an xsb file with files at that offset. this is a new custom xwb, same as dead island uses, that stores the file names in the xwb in a method not like that of the xsb. I'd just extract the xwb with unxwb using the decimal names option (instead of hex names) and then go down the list and copy paste the names onto the files. it's the same order. (unless you use the hex option default, which means you'll have to know the order of the hex valued names)

Thanks for the tip mate, it helps.



I have a last little question: Somebody know how is written a .XSB file? I mean, can we convert this part of the .XWB into a .XSB file to make the renaming simpler?

Cordialy.
