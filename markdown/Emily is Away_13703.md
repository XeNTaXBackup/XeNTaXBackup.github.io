## Post #1
- Username: LuanXD99
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 19, 2015 6:38 am
- Post datetime: 2015-12-18T22:43:43+00:00
- Post Title: Emily is Away

Hello! I'm Brazilian and I speak English fluently, but I am new in games translations, I'm trying to translate the game Emily is Away, but I can not find the texts, please help me! OBS: i'm using Unity Asset Editor

Update: Using the Unity Asset Editor i was able to catch those 5 files (Rar Compressed):
[Emily Is Away.rar](https://xentaxbackup.github.io/file/10167_Emily Is Away.rar)
## Post #2
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-19T14:06:28+00:00
- Post Title: Emily is Away

Any one?
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-20T03:54:46+00:00
- Post Title: Emily is Away

most of those samples are just shaders. although its text it doesn't need translating.

other other "Localization.txt" is interesting. the developers may have used NGUI to make their interfaces in Unity. what languages does the game support?
## Post #4
- Username: LuanXD99
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 19, 2015 6:38 am
- Post datetime: 2015-12-20T05:28:19+00:00
- Post Title: Emily is Away

Only English
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-20T23:50:05+00:00
- Post Title: Emily is Away

> Reply from LuanXD99
>
> Only English

okay. now read my post again. i said the files you posted were only shaders, so post the language files and i can take a look
## Post #6
- Username: LuanXD99
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 19, 2015 6:38 am
- Post datetime: 2015-12-21T03:36:41+00:00
- Post Title: Emily is Away

That is the problem man, i can't find them ;-;
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-21T15:38:07+00:00
- Post Title: Emily is Away

unity studio doesn't support importing/saving assets either - how would you get the translations into the game?
## Post #8
- Username: LuanXD99
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 19, 2015 6:38 am
- Post datetime: 2015-12-21T19:59:04+00:00
- Post Title: Emily is Away

Mine supports, I can export and import assets [http://prntscr.com/9gxlzw](http://prntscr.com/9gxlzw)
## Post #9
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-12-21T20:37:42+00:00
- Post Title: Emily is Away

I saw some texts from menu in level0 file.
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-21T22:05:28+00:00
- Post Title: Emily is Away

> Reply from merlinsvk
>
> I saw some texts from menu in level0 file.

there are a few strings here:

> [000000]Are you sure you want
>
> to reset the game?
>
> [-][616058]
>
> All of your progress 
>
> will be lost[-]

does anyone know how ngui in unity deals with localisation?
## Post #11
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-12-22T10:30:59+00:00
- Post Title: Emily is Away

I think that devs used NGUI, but not it's localization feature. That's why are texts in level* files and not in Localization.txt.

BTW: All other texts (chat messages) are in Assembly-CSharp.dll.
## Post #12
- Username: LuanXD99
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 19, 2015 6:38 am
- Post datetime: 2015-12-22T17:09:24+00:00
- Post Title: Emily is Away

But how can i open the Assembly-CSharp.dll?
## Post #13
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-22T17:14:45+00:00
- Post Title: Emily is Away

> Reply from merlinsvk
>
> I think that devs used NGUI, but not it's localization feature. That's why are texts in level* files and not in Localization.txt.

BTW: All other texts (chat messages) are in Assembly-CSharp.dll.

ngui supports localisation. it sounds like the translations are serialized as part of the c# scripts. good spot  


edit

yeah you can just download any .net decompiler and open the dll file to get the full game source. why anyone would use unity i have no idea:

```
        instance.AddOfflineOnlyBuddyRow("BrookHorse7");
        instance.AddOfflineOnlyBuddyRow("Isaac666");
        instance.AddOfflineOnlyBuddyRow("JobBot");
        instance.AddOfflineOnlyBuddyRow("H3RST0RY");

```


all buddy icons:

> public enum BuddyIconType
>
> {
>
>     None,
>
>     LogoWhite,
>
>     LogoBlack,
>
>     LogoBlue,
>
>     LogoGreen,
>
>     DaysLater,
>
>     TheRing,
>
>     HarryPotter,
>
>     LordoftheRings,
>
>     Blink182,
>
>     RedHotChiliPeppers,
>
>     Eminem,
>
>     Avril,
>
>     Dog,
>
>     Cat,
>
>     Monkey,
>
>     Koala,
>
>     Matrix,
>
>     Nemo,
>
>     Pirates,
>
>     KillBill,
>
>     Beyonce,
>
>     Britney,
>
>     FiftyCent,
>
>     LinkinPark,
>
>     Bear,
>
>     Rabbit,
>
>     Panda,
>
>     Tiger,
>
>     EminemEncore,
>
>     BlackEyedPeas,
>
>     Usher,
>
>     GreenDay,
>
>     MeanGirls,
>
>     EternalSunshine,
>
>     Incredibles,
>
>     Saw,
>
>     Frog,
>
>     Hamster,
>
>     Octopus,
>
>     Pig,
>
>     Gorillaz,
>
>     MariahCarey,
>
>     SystemOfADown,
>
>     Coldplay,
>
>     VForVendetta,
>
>     SinCity,
>
>     WeddingCrashers,
>
>     Batman,
>
>     Elephant,
>
>     Penguin,
>
>     Snake,
>
>     Whale,
>
>     RedHotChiliPeppers2,
>
>     GnarlesBarkley,
>
>     JustinTimberlake,
>
>     DanielPowter,
>
>     HighSchoolMusical,
>
>     ThreeHundred,
>
>     Borat,
>
>     Cars,
>
>     EmilySnowPatrol,
>
>     EmilyColdplay,
>
>     EmilyMuse,
>
>     EmilyDeathCab,
>
>     EmilySnowPatrol2,
>
>     SecretEmily,
>
>     SecretJulie,
>
>     SecretTravis,
>
>     SecretBrad,
>
>     SecretRobotLovesKitty,
>
>     SecretHJTenchi,
>
>     SecretChilledChaos,
>
>     SecretKappa,
>
>     SecretIsaac,
>
>     SecretZelda,
>
>     SecretMinecraft,
>
>     SecretHalflife,
>
>     SecretFallout,
>
>     SecretBorderlands,
>
>     SecretDota,
>
>     SecretBioshock,
>
>     SecretCibele,
>
>     SecretSunlight,
>
>     SecretWalkingDead,
>
>     SecretStanley,
>
>     SecretDodgeball,
>
>     SecretElegy,
>
>     SecretJobSim,
>
>     SecretMushroom11,
>
>     SecretGrimecraft,
>
>     SecretRadiohead,
>
>     SecretNIN,
>
>     SecretDFA1979,
>
>     SecretProdigy,
>
>     SecretDaftPunk,
>
>     SecretInterpol,
>
>     SecretStrokes,
>
>     SecretModestMouse,
>
>     SecretSnowPatrol,
>
>     SecretArcadeFire,
>
>     SecretSigurRos,
>
>     SecretFNAF,
>
>     SecretElderScrolls,
>
>     SecretHotlineMiami,
>
>     SecretUndertale,
>
>     SecretCrash,
>
>     SecretKingdomHearts,
>
>     SecretKindaFunny,
>
>     SecretJackSepticEye,
>
>     SecretDoge,
>
>     SecretKreygasm,
>
>     SecretPokemon,
>
>     SecretDeathCab,
>
>     SecretRust,
>
>     SecretTF2,
>
>     SecretPortal,
>
>     SecretGTA,
>
>     SecretDodger,
>
>     SecretSSundee,
>
>     SecretPewDiePie,
>
>     SecretSqueezie,
>
>     SecretClippy,
>
>     SecretNyanCat,
>
>     SecretJohnCena,
>
>     SecretASevenfold
>
> }
## Post #14
- Username: LuanXD99
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 19, 2015 6:38 am
- Post datetime: 2015-12-22T21:57:02+00:00
- Post Title: Emily is Away

ok, I Got It the source of the dll file, but I'm not finding the game dialogs [http://prntscr.com/9hemmu](http://prntscr.com/9hemmu)
## Post #15
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-12-22T22:01:50+00:00
- Post Title: Emily is Away

> Reply from LuanXD99
>
> But how can i open the Assembly-CSharp.dll?

(paid) Redgate .NET Reflector  + (open-source) Reflexil addon

or

(free) Telerik JustDecompile + Reflexil

or

(open-source) ILSpy + Reflexil

> Reply from LuanXD99
>
> ok, I Got It the source of the dll file, but I'm not finding the game dialogs...

You really didn't search it, did you?

```
Chapter2ScriptBehavior.cs
Chapter3ScriptBehavior.cs
Chapter4ScriptBehavior.cs
Chapter5ScriptBehavior.cs
```
## Post #16
- Username: LuanXD99
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 19, 2015 6:38 am
- Post datetime: 2015-12-22T23:45:00+00:00
- Post Title: Re: Emily is Away

There is no text to translate inside those files [http://prntscr.com/9hfyly](http://prntscr.com/9hfyly)
## Post #17
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-23T00:31:37+00:00
- Post Title: Re: Emily is Away

> Reply from LuanXD99
>
> There is no text to translate inside those files http://prntscr.com/9hfyly

I think you've opened them all. isn't in any of them?
## Post #18
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-12-23T10:58:06+00:00
- Post Title: Re: Emily is Away

> Reply from LuanXD99
>
> There is no text to translate inside those files

I used NET Reflector to decompile whole .dll and I got text in that files.
[Emily.7z](https://xentaxbackup.github.io/file/10194_Emily.7z)
## Post #19
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-24T04:00:03+00:00
- Post Title: Re: Emily is Away

> Reply from merlinsvk
>
> LuanXD99 wrote:There is no text to translate inside those files

I used NET Reflector to decompile whole .dll and I got text in that files.

I found it, but how I will repack it
## Post #20
- Username: LuanXD99
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 19, 2015 6:38 am
- Post datetime: 2015-12-24T17:05:35+00:00
- Post Title: Re: Emily is Away

Yeah, i found it too, but how we repack it?
## Post #21
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-12-25T12:05:29+00:00
- Post Title: Re: Emily is Away

I would use Reflexil addon to directly edit that text and then save it as "patched" .dll. But I have no idea if it's possible to replace the whole code.
## Post #22
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2015-12-25T12:56:01+00:00
- Post Title: Re: Emily is Away

ilasm and ildasm [https://yadi.sk/d/sTTy3mLvmUpjJ](https://yadi.sk/d/sTTy3mLvmUpjJ)

Unpack.bat:
ildasm.exe Assembly-CSharp.dll /out=Assembly-CSharp.il

Edit Assembly-CSharp.il and save as 0Assembly-CSharp.il

Pack.bat:
del Assembly-CSharp.dll
ilasm.exe 0Assembly-CSharp.il /dll /resource:Assembly-CSharp.res /output:0Assembly-CSharp.dll
ren 0Assembly-CSharp.dll Assembly-CSharp.dll
del 0Assembly-CSharp.il
## Post #23
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-12-25T18:24:23+00:00
- Post Title: Re: Emily is Away

> Reply from makcar
>
> ilasm and ildasm https://yadi.sk/d/sTTy3mLvmUpjJ

Unpack.bat:
ildasm.exe Assembly-CSharp.dll /out=Assembly-CSharp.il

Edit Assembly-CSharp.il and save as 0Assembly-CSharp.il

Pack.bat:
del Assembly-CSharp.dll
ilasm.exe 0Assembly-CSharp.il /dll /resource:Assembly-CSharp.res /output:0Assembly-CSharp.dll
ren 0Assembly-CSharp.dll Assembly-CSharp.dll
del 0Assembly-CSharp.il

Edit2: Thank you buddy. It worked

And subtitle files here, but where the menu files?
