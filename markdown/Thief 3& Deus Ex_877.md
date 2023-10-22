## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-23T20:20:08+00:00
- Post Title: Thief 3& Deus Ex

Hello

Are you can unpack *.csc files from game thief 3?

thank you
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-24T13:52:39+00:00
- Post Title: Thief 3& Deus Ex

No help from me on this one - I have had a look at them before and got nowhere. 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-24T18:33:10+00:00
- Post Title: Thief 3& Deus Ex

me neither
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-25T04:21:34+00:00
- Post Title: Thief 3& Deus Ex

If i had the game, i'd take a look at them
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-25T06:51:48+00:00
- Post Title: Thief 3& Deus Ex


## Post #6
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-26T21:36:10+00:00
- Post Title: Thief 3& Deus Ex

Well I borrowed this game from a friend of mine.  I looked at the files.

.csc files are for sound.

SchemaMetafile_DVD1+2+3.csc are a collection of OGG files.  These are similiar to MP3 files.  The only problem I can see, is that there is no "directory" structure, they are all butted up against one another all the way to the end of the file.

Copying the first 0x5975 bytes of the archive give me this...
## Post #7
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-26T22:27:40+00:00
- Post Title: Thief 3& Deus Ex

The DVD.csc files are nothing more than multiple streamed ogg files, in different pages.  Changing the files to an OGG, will let you listen to EVERY stream in the file, in order. There are programs you can get from vorbis, that can be used to seperate the streams.  We also could write a program to seperate the streams for you.  Unfortunately, there are no original filenames in the file.
## Post #8
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-26T23:13:03+00:00
- Post Title: Thief 3& Deus Ex

this is some good info

```
24564f0: 8180 8008 0808 0900 004c 4953 5446 0000  .........LISTF..
2456500: 0049 4e46 4f49 4352 440b 0000 0032 3030  .INFOICRD....200
2456510: 342d 3034 2d30 3400 0049 454e 470d 0000  4-04-04..IENG...
2456520: 0045 7269 6320 4272 6f73 6975 7300 0049  .Eric Brosius..I
2456530: 5346 5410 0000 0053 6f75 6e64 2046 6f72  SFT....Sound For
2456540: 6765 2034 2e35 00                        ge 4.5.
```


Sound Forge 4.5?  I tried opening it with the trial version of sound forge, but no go.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-27T07:40:01+00:00
- Post Title: Thief 3& Deus Ex

> Reply from Rahly
>
> this is some good info
Code: Select all24564e0: 130b 6702 9909 a8ab 10a8 3a47 a08b 81fb  ..g.......:G....
24564f0: 8180 8008 0808 0900 004c 4953 5446 0000  .........LISTF..
2456500: 0049 4e46 4f49 4352 440b 0000 0032 3030  .INFOICRD....200
2456510: 342d 3034 2d30 3400 0049 454e 470d 0000  4-04-04..IENG...
2456520: 0045 7269 6320 4272 6f73 6975 7300 0049  .Eric Brosius..I
2456530: 5346 5410 0000 0053 6f75 6e64 2046 6f72  SFT....Sound For
2456540: 6765 2034 2e35 00                        ge 4.5.

Sound Forge 4.5?  I tried opening it with the trial version of sound forge, but no go.

Yes, this is what I did as well when I looked at them. I couldn't play them in the full version of Sound Forge (tried and failed in the trial, "borrowed" the full version). So I searched for a way, tried to find possible plugins to play them, compared different saving-formats by Sound Forge to match them with the files I got. To no avail. All of this was the fundament of my 
"me neither   " post above.
## Post #10
- Username: Moon
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 06, 2004 12:08 am
- Post datetime: 2004-08-27T12:03:06+00:00
- Post Title: Thief 3& Deus Ex

I already uninstalled that game, as it's so awful (though at least I got it to run properly under W98 thanks to a small "hack"), but if these are OGGs then any OGG unpacker should extract them.
## Post #11
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-27T15:35:56+00:00
- Post Title: Thief 3& Deus Ex

I am extract ogg from csc package and play ogg with sound forge 7.0
(unknow file name and directory)
## Post #12
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2004-09-22T19:48:33+00:00
- Post Title: Thief 3& Deus Ex

Hi! I'm new italian member.
I found this specification csc guide:
[http://www.deusexgaming.com/deusex2/info/audio/specs](http://www.deusexgaming.com/deusex2/info/audio/specs)

I used that when try to create a conversion patch english to italian language   

I'm italian.. sorry for my little english
