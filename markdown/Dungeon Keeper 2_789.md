## Post #1
- Username: Viruzz
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-07-05T14:48:15+00:00
- Post Title: Dungeon Keeper 2

I know its old now, but what about the other files of Dungeon Keeper 2 like Meshes, Sprites and so on?
The only format supported by MultiEx Commander is .sdt...
## Post #2
- Username: DemonS_HorizoN
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 14, 2004 2:21 am
- Post datetime: 2004-07-14T06:14:06+00:00
- Post Title: Dungeon Keeper 2

Dungeon Keeper rockz   

EA-Games and Bullfrog don't want to make a third Game 

but modding is a good way to revive it
## Post #3
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2004-07-18T06:39:05+00:00
- Post Title: Dungeon Keeper 2

> Reply from Viruzz
>
> I know its old now, but what about the other files of Dungeon Keeper 2 like Meshes, Sprites and so on?

There is an official tool for .WAD files in DK2 and even a way for the game to use external files instead of .WAD. 

You can get it here:
[http://dk2.ea-europe.com/dk2/content/su ... index.html](http://dk2.ea-europe.com/dk2/content/support/wadtool/index.html)

Here is what I know about DK2 .WAD format:
- There is a header :

```
       ID: array[0..3] of char;
       Version: integer;
       Filler: array[0..63] of byte;
       Dirnum: integer;
       NameOffset: integer;
       NameSize: integer;
       Unknown: integer;
     end;
```

ID is "DWFB"
- Just after the header is the index (Dirnum times DWFBEntry) :

```
       Unknown: integer;
       NameOffset: integer;
       NameSize: integer;
       Offset: integer;
       Size: integer;        // Compressed size in bytes
       CompMethod: integer;  // Compression method: 0 = None
                             //                     4 = Unknown compression method
       UncompSize: integer;  // Decompressed size in bytes
       Filler: array[0..11] of byte;
     end;
```

Entries with CompMethod = 4 are compressed with something that looks like Huffman compression (but I haven't had time to have a deeper look at it).

Hope this helps.
## Post #4
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-03-04T07:58:38+00:00
- Post Title: Dungeon Keeper 2

Can I change the original sound (.mp2) files with my own translated files?

We'd like to translate this game into hungarian, but first of all, we should know if it works.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-04T13:58:18+00:00
- Post Title: Dungeon Keeper 2

There are various MP2 encoders around, to convert from wav to mp2 to mp3 etc. That will work. You chould check what type of MP2 the game uses and then make sure your mp2s are like that.
## Post #6
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-03-04T14:10:00+00:00
- Post Title: Dungeon Keeper 2

Sorry, I wasn't clear enough before.

The sound files are compressed into a lot of *.sdt files that can be read with MultiEx Commander I saw that the Import option doesn't work  so I'd like to know if I need a plug-in to make it work, or it just can read them, and there's no way to replace the orig. files within the *.sdt file with my own ones.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-07T07:37:50+00:00
- Post Title: Dungeon Keeper 2

Sorry for the late reponse, but I'm swamped in work and family matters. I will see if I can fix file replacement for you.
## Post #8
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-03-13T06:51:47+00:00
- Post Title: Dungeon Keeper 2

Thank you, and please, let me know if you figure it out.
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-21T23:28:32+00:00
- Post Title: Dungeon Keeper 2

Any updates here?
no?
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-20T22:01:40+00:00
- Post Title: Dungeon Keeper 2

Started to figure out mesh format.
[viewtopic.php?t=2546](http://forum.xentax.com/viewtopic.php?t=2546)
