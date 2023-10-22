## Post #1
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-06-25T08:13:37+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

Hi there

Recently came across this game. GCFScape and Wally seem to open these files okay, but Xentax has a bit of trouble with them.

I will attach a WAD file for the minute, the PAK files will need splitting.

Could you possibly have a look and see what the problem is?

Cheers for now
[1_C0A0.rar](https://xentaxbackup.github.io/file/314_1_C0A0.rar)
## Post #2
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-06-25T08:16:08+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

...and one from the "Barney" portion (Blue Shift)
[1_BA_CANAL1.rar](https://xentaxbackup.github.io/file/315_1_BA_CANAL1.rar)
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-25T09:32:00+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

You can using WALLY for edit textures...
## Post #4
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-06-25T09:40:25+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

> Reply from KorNet
>
> You can using WALLY for edit textures...

Well, the WADs will open in Wally, but the textures are in a format that Wally cannot display (PVR I think). 

All I was asking for was that MultiEx might be made to open these types properly...
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-25T18:11:48+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

Ok, thanks for the bugreport! I will have a look and try to fix it!
## Post #6
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-06-25T21:25:29+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

Cool. I will try to post the pak files tomorrow from the DC version.

I also have the PS2 version of the game. Some of the PAK files on there are standard Valve ones, but others don't want to open in Xentex or Pakscape.. should I post samples of those too?

Cheers for now

PS - In fact... here they are... the two RAR files are from Dreamcast PAK files and the "decay.pak" is from the PS2 version...

[http://talisman.clift.org/talismanisland/test/multiex/](http://talisman.clift.org/talismanisland/test/multiex/)

Cheers!!!
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-25T22:14:18+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

Thanks. I've fixed the WAD problem. They were actually yet another WAD format (WAD3+ or something, not standard WAD3 or IWAD). 

Here's the MultiEx Commander script

```
IDString 0 WAD3 ;
Get FC Long 0 ;
SavePos TailOffOff 0 ;
Get TO Long 0 ;
GoTo TO 0 ;
For TE = 1 To FC ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
GetDString FN 16 0 ;
Log FN FO FS FOO FSO ;
Next TE ;

```


Will make it available from webupdate tomorrow if time permits.
## Post #8
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-06-28T18:04:29+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

If I add the above as a BMS script, will it mess up if it then comes in an automatic update?

Any luck with the new PAK files too?

Cheers for now
## Post #9
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2005-06-30T07:33:11+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

Dreamcast version????     But it was cancelled!  Wow, how did you get the DC version to explore?
## Post #10
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-06-30T17:22:58+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

<cough>Google<cough>
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-30T19:51:18+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

> Reply from Rusty_le_Cyborg
>
> If I add the above as a BMS script, will it mess up if it then comes in an automatic update?

Any luck with the new PAK files too?

Cheers for now

No, not if you use it in Run Custom Script.
## Post #12
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-07-01T00:04:16+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

Hmm.. looks like I'm doing something wrong again.. 

How do I get this to load as a custom script? Yes, I've read the sticky.. but can't get it to work
## Post #13
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-07-05T19:12:46+00:00
- Post Title: Half Life: Dreamcast WAD & PAK Files

Hey there Mr Mouse!

I notice this didn't get included in latest update? Any chance in the next one?

Did you have any luck with the PAK files?

Cheers for now
