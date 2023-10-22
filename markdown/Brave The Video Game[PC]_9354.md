## Post #1
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-07-26T22:30:11+00:00
- Post Title: Brave: The Video Game[PC]

Hello!
The game stores everything in PC_DX9 files. The coding doesn't looks like hard. Can someone please make a converter for it?
(i can give sample)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-26T23:29:21+00:00
- Post Title: Brave: The Video Game[PC]

send me some samples... i had  a look at the PS3 version and couldn't do anything with it. i ain't buying the game again unless it comes out really cheap for PC (like say less than $10).
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-27T12:04:18+00:00
- Post Title: Brave: The Video Game[PC]

thanks for the samples... looks workable... the ps3 data was totally different. found DDS textures in some of the samples, but haven't found any geometry though. dx9_pc files seem to be an archive type that can even contain more dx9_pc files. format reminds me of AFS a little bit, offsets at top to filenames at the bottom. i will buy the game soon to look more into it as i will need a lot more than those sample to figure more out.
## Post #4
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-07-27T12:09:10+00:00
- Post Title: Brave: The Video Game[PC]

Great, i'll wait for it, anyway i'm intrested in the lang files mostly. Thanks for your research.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-27T12:23:26+00:00
- Post Title: Brave: The Video Game[PC]

ah, then under the localization forum you might want to repost this and give those that are interested files like games_en.pc_dx9 that contain language information. under games directory, are those the only files that contain language information?
## Post #6
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-07-27T13:32:14+00:00
- Post Title: Brave: The Video Game[PC]

No, there are other language files in other folder(s) (i didn't checked all folders) but they are in .pc_dx9 format too. I didn't posted this thread in localization, because every file of the game is in this format. (except a 26kb dat file, and some dlls, and bik videos) If the unpacked .pc_dx9 contains a file which needed further research i'll post in localization too.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-30T08:08:10+00:00
- Post Title: Brave: The Video Game[PC]

ok, $20, wasn't that bad... models look extractable, even quite easy; i will know in a couple days when I have some free time to code. in the meantime, maybe AlphaTwentyThree can write a BMS script to unpack these files... AlphaTwentyThree... where are youuuuuuuuu he he he?
## Post #8
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-07-31T02:41:18+00:00
- Post Title: Brave: The Video Game[PC]

Lol is it even possible to like inject new models once we crack the geometry format? Might as well mod that game for the lulz.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-31T03:35:21+00:00
- Post Title: Brave: The Video Game[PC]

actually, the thought did cross my mind after looking at it. definitely texture mods at least seam possible. anyone up for a nude brave mod lol? there's some unknown stuff before the list of textures so i dunno about model mods but maybe....
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-31T04:25:12+00:00
- Post Title: Brave: The Video Game[PC]

anyone want to try to modify textures?

in outfit01.pc_dx9, at offset 0x12E0 is a simple 1024x1024 DXT1 texture with mipmaps.
## Post #11
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-07-31T23:33:04+00:00
- Post Title: Brave: The Video Game[PC]

I might but I have to get my copy of the game first. But I do hope that custom models will be possible.
## Post #12
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-08-01T07:42:06+00:00
- Post Title: Brave: The Video Game[PC]

> Reply from howfie
>
> anyone want to try to modify textures?

in outfit01.pc_dx9, at offset 0x12E0 is a simple 1024x1024 DXT1 texture with mipmaps.

OK, I'm in. Got an unpacker or repacker for me to test? Game uses FMOD FSBs like Tangled; sound files from Mafia II could probably work on Brave as well (I did successfully swap the menu music in Tangled with the one from Mafia II, lulz).
## Post #13
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-01T08:15:36+00:00
- Post Title: Brave: The Video Game[PC]

no, not yet. i've been just hardcoding some stuff from the armours... game uses multiple vertex buffers, most vertex formats are 0x40 bytes, standard floats and stuff... a few things I don't understand yet but once i get some models out of the game i'll work on an unpacker.
## Post #14
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-08-01T09:31:11+00:00
- Post Title: Brave: The Video Game[PC]

> Reply from howfie
>
> no, not yet. i've been just hardcoding some stuff from the armours... game uses multiple vertex buffers, most vertex formats are 0x40 bytes, standard floats and stuff... a few things I don't understand yet but once i get some models out of the game i'll work on an unpacker.

And a repacker as well. And like what I said it'll be 'swell if we come up with an import/export tool for models.
## Post #15
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-10T11:34:40+00:00
- Post Title: Brave: The Video Game[PC]

Problem... hair is nowhere to be found!
## Post #16
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-08-11T11:03:22+00:00
- Post Title: Re: Brave: The Video Game[PC]

> Reply from howfie
>
> Problem... hair is nowhere to be found!

A separate mesh, maybe? BTW, can I contact you through Skype or some other service? Might as well help you do some tinkering with this and a few other games that I'd like to mod.
## Post #17
- Username: shrek
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 14, 2012 3:07 pm
- Post datetime: 2012-08-21T13:22:12+00:00
- Post Title: Re: Brave: The Video Game[PC]

Any news on this?

I'd like to print some characters from the game in 3D, tried to rip it with 3D Ripper but it didn't work due to the securom protection.

An unpacker would really be nice here...
## Post #18
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-09-26T05:19:03+00:00
- Post Title: Re: Brave: The Video Game[PC]

Any progress on the file formats?
## Post #19
- Username: Eradicon
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Feb 11, 2011 1:20 am
- Post datetime: 2014-07-19T23:54:09+00:00
- Post Title: Re: Brave: The Video Game[PC]

All this, and yet no clear answer on what program to view or unpack this file type.
