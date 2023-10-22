## Post #1
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-02-22T16:19:54+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

I have no idea why this file is encrypted but for most people all they want to do is change bsmoothframerate from from true to false and increase MaxSmoothedFrameRate= from 62 to 100 or so and just play the game.  But the file isn't accessible just using a notepad.  Does anyone have a method of accessing this file?
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-22T16:26:12+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

providing the file is the first step
## Post #3
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-02-22T21:54:49+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

Does anyone else have the game that can upload the stormengine/etc.ini files.  I'm not able to do so yet. 
I would really appreciate your help.

Edit:
Here you go:
[http://dl.dropbox.com/u/10044418/ini_files.rar](http://dl.dropbox.com/u/10044418/ini_files.rar)

What do you make of it?
## Post #4
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-02-22T22:39:41+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

Look's like AES EBC, or it could be a simple XOR. We would need the executable to get the key and method.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-22T22:55:50+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

it's for sure not a block cipher algorithm due to the lack of alignment and for stormgame.ini that doesn't show the same 8/16 bytes blocks, for example they vary each 2 bytes (in a block cipher the blocks are identical or completely different, not half).
I don't have other ideas
## Post #6
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-02-23T00:45:21+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

Will this be of any use?
## Post #7
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-23T02:49:14+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

This should be it, untested.

```
if (*(unsigned int *)&input[0] == 0x474831A6)
{
    output = malloc(length - 4);
    unsigned char *key = { 0x01, 0x02, 0x03, 0x04, 0x0A, 0x0B, 0x0C, 0x0D, 0x1A, 0x2B, 0x3C, 0x4D, 0xDB, 0xCA, 0x43, 0x21 };
    unsigned char magic = (length - 4) % 256;
    for (int i = 0; i < length - 4; i++)
    {
        output[i] = input[4 + i] - key[i % 16] - magic;
    }
}
else
{
    output = malloc(length);
    memcpy(output, input, length);
}
```
## Post #8
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-02-23T03:09:36+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

Thanks for the info.  I assume that was directed at Caboose or Aluigi?
## Post #9
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-23T08:32:19+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

[http://mod.gib.me/bulletstorm/inicrypt.exe](http://mod.gib.me/bulletstorm/inicrypt.exe)

(I was too tired to open Visual Studio when I posted the crypto snippet )
## Post #10
- Username: cocococo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 23, 2011 10:02 pm
- Post datetime: 2011-02-23T14:04:59+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

hello everybody.

how do i use this file to decrypt the config files?

greetings
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-23T15:14:21+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

well done Rick.
to keep me in exercise with the bms language and for who is interesting in its syntax I have made a simple commented script:

```
get SIZE asize                  # get the size of the file
math SIZE -= 4                  # skip 4 bytes
log MEMORY_FILE 4 SIZE          # load in memory from offset 4
set KEY binary "\x01\x02\x03\x04\x0A\x0B\x0C\x0D\x1A\x2B\x3C\x4D\xDB\xCA\x43\x21"   # the key
for i = 0 < SIZE                # start the cycle for each byte
    getvarchr B MEMORY_FILE i   # get the current byte (B)
    math T = i                  # these...
    math T %= 16                # 3 operations...
    getvarchr T KEY T           # are only needed for T = KEY[i % 16]
    math B -= T                 #
    math B -= SIZE              # B = B - T - SIZE
    putvarchr MEMORY_FILE i B   # replace the current byte
next i
get NAME basename               # the following is needed only
get EXT extension               # to add _decrypted before
string NAME += "_decrypted."    # the file extension
string NAME += EXT
log NAME 0 SIZE MEMORY_FILE     # copy everything in the file
```
obviously full credit to Rick.
## Post #12
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-02-23T19:43:39+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

Thank you very much for time and effort in resolving this.  I also want to point out that the bms script does work.  However, I don't know how to encrypt the corrected StormEngine.ini file once the changes are made.  Can anyone be of assistance?
## Post #13
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-23T19:58:02+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

You can use my inicrypt to reencrypt, just click+drag unencrypted file onto inicrypt again.
## Post #14
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-23T20:43:57+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

@Rick - own curiosity with encrypted formats - how did you find the key? did you reverse any of the game client or figure the key bytes from just the format?
## Post #15
- Username: Paft
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Feb 24, 2011 4:48 am
- Post datetime: 2011-02-23T21:02:34+00:00
- Post Title: [PC]BulletStorm's engine.ini, etc is encrypted

GREAT! So, I tried to increase FPS to 100. Changed the value and decrypted, but still at 62.

What are the ones to disable mouse smoothing, acceleration and sensitivity?
## Post #16
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-02-23T21:06:42+00:00
- Post Title: Re: [PC]BulletStorm's engine.ini, etc is encrypted

> Reply from Paft
>
> GREAT! So, I tried to increase FPS to 100. Changed the value and decrypted, but still at 62.

What are the ones to disable mouse smoothing, acceleration and sensitivity?
Look for vsync also.
## Post #17
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-23T21:23:46+00:00
- Post Title: Re: [PC]BulletStorm's engine.ini, etc is encrypted

You can toggle vsync in the game options just fine though.
## Post #18
- Username: Paft
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Feb 24, 2011 4:48 am
- Post datetime: 2011-02-23T21:25:59+00:00
- Post Title: Re: [PC]BulletStorm's engine.ini, etc is encrypted

Thanks.

Also: [http://arstechnica.com/gaming/news/2011 ... our-pc.ars](http://arstechnica.com/gaming/news/2011/02/bulletstorm-and-you-how-to-get-it-playing-nice-with-your-pc.ars)
## Post #19
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-02-23T22:42:39+00:00
- Post Title: Re: [PC]BulletStorm's engine.ini, etc is encrypted

I want to thank everyone for the help.
## Post #20
- Username: Paft
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Feb 24, 2011 4:48 am
- Post datetime: 2011-02-23T22:52:44+00:00
- Post Title: Re: [PC]BulletStorm's engine.ini, etc is encrypted

bEnableMouseSmoothing=false feels much better but it still feels like there's acceleration going on.

I edited "storminput.ini. is that right?

edit: Scratch what I said. I lowered my sens some more, feels ok now. Think I just needed to get used to the game.
## Post #21
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2011-02-26T01:48:28+00:00
- Post Title: Re: [PC]BulletStorm's engine.ini, etc is encrypted

Does anyone know what kind of DRM is used for this game?
## Post #22
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-02-26T07:52:57+00:00
- Post Title: Re: [PC]BulletStorm's engine.ini, etc is encrypted

Depends on where you bought it, my Steam copy has Steam DRM and GFWL.
## Post #23
- Username: fuzion
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 25, 2010 2:05 pm
- Post datetime: 2011-04-14T01:22:46+00:00
- Post Title: Re: [PC]BulletStorm's engine.ini, etc is encrypted

Crimecraft (F2P) also encrypts the ini files.
I was looking at the technique used here but I'm not sure its applicable to Crimecraft's ini files (and I couldn't find a key in the binary).
Anyone wanna take a look?

[http://localhostr.com/files/WpFX6QH/CrimeCraft_ini.zip](http://localhostr.com/files/WpFX6QH/CrimeCraft_ini.zip)
Thanks!
## Post #24
- Username: sneddy78
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 31, 2022 12:51 am
- Post datetime: 2022-10-30T17:04:46+00:00
- Post Title: Re: [PC]BulletStorm's engine.ini, etc is encrypted

hi guys, can anyone help me to decrypt this .ini file please ? [https://www.mediafire.com/file/r7pgn379 ... e.ini/file](https://www.mediafire.com/file/r7pgn379nxn3wqm/DefaultGame.ini/file)
i tried some ini decrypt stuff but they looks out dated.
