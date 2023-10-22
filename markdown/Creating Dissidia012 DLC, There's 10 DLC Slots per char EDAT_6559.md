## Post #1
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-05-04T23:25:47+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

So I'm currently on the quest to figure out what information is in the decrpyted edat files in Dissidia Duodecim's DLC addons that you can get. The free Warrior of Light costume came with 2 GMO and 1 GIM these are the normal character model, the assist model, and the artwork portrait. Along side these though also included 4 other files labeled as .edat, I know that there are up to 10 DLC costume slots accessible via cwcheat but obviously choosing an empty one just loads the default costume because there is no model to load for that. But I believe that these other 4 edat files have information that adds the costume as a playable costume.

Here is what I have found so far; There are 4 extra edat files they are as follows: 3fb967fe.edat, ee40dfcd.edat, 3d566b6e.edat, 10bfa4e2.edat

The string data for the first two seems easy enough to read:

3fb967fe.edat:

```
........â...¿....#ÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿP_ONE100_4P.....p_one100........
```

&
ee40dfcd.edat

```
........ã...ÿÿ...$ÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿP_ONE100_4P_A...p_one100_a......
```


What I have found so far is that the "ONE" at the front means that it's a character from FF1 which in this case is Warrior of Light. The 100 that follows seems to indicate that it is a character from the Cosmos side as Chaos characters have 200 instead of 100. The "_4P" indicates that it's the 4th costume aka DLC1 because there are 3 other normal non DLC outfits. The "_A" indicates the assist form of the character instead of the normal.

I haven't tried playing with those values yet but they sound fruitful possibly.

The other two edat's also included that are probably just as important if not more so don't seem to have anything but gibberish to me in them as far as what is readable in the strings:

3d566b6e.edat

```
........{...FPÿÿš™™>®Gá>q=.?¤p=?ffæ>ÍÌL?3<øl.gøQ.…ë>ÍÌÌ?...?&÷Ð.....”øø.....)\.>v»ÿ.....
```


10bfa4e2.edat

```
..........................................ÿÿÿÿÿÿ..ÿÿÿÿÿÿ...._00.....
```


If anyone has isolated DLC that is decrpyted as in all the edats that came with a character but not mixed with the rest of the DLC this could prove quite helpful.

I've got my DLC in one folder and it's impossible for me to redownload them separately as the PSN is down. If you could pm me them that'd help.

Because as I look at my other DLC's I'm seeing this:

1e2f01ee.edat:

```
........ê.Ø......+......ÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿP_EHT110_4P.....p_eht110........
```


02a2ba93.edat:

```
........Å...À.....0ÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÎ.ÿÿÿÿÿÿP_NIN100_4P.....p_nin100........
```


P_EHT110_4P.....p_eht110 ; The 10 in it makes it the second Character from FF8 4th costume (DLC Laguna)
P_NIN100_4P.....p_nin100 ; Character from FF9 4th Costume (DLC Zidane)

The 100 seems to indicate whether it's Cosmos or Chaos. I'm not sure why Squalls is 110 though.

I found this too which I believe to be identifying my Kuja DLC: 

8c7dbef4.edat

```
........Õ...ÿÿ....ÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿP_NIN200_4P_A...p_nin200_a......
```


P_NIN200_4P_A...p_nin200_a ; Character from FF9 with a 200 value indicating it's for Chaos not Cosmos, and _A to say it's pointing to him as an assist. (DLC Kuja)


Just a little progress but if I could get isolated DLC's I could probably get more on this. I'm sure there has to be information in the edats that point to which model is and that's why they have to be named specific things. In the case of WoL I have 2 edats that identify his normal 4th costume and then the other for his 4th assist. But this leaves 2 edat files that are unaccounted for that aren't a gim, or gmo file. That must mean that in these two it specifies where the target model etc is that should be loaded.

This would be helpful to figure out because if I/we can figure out how to add other GMO's to the remaining 9 DLC slots then we could add our own custom textured GMOs (no custom models now if ever since no one wrote a GMO exporter of any sort) as DLC to extra DLC slots without replacing existing stuff. We could even do DLC for characters that don't have any yet.
## Post #2
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-05-07T06:50:01+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

Maybe it was foolish to post this in such a dead section instead of 3D Models. After all this is related to them heavily just not the model format.

Anyway I've been looking at some of the edat files and they seem to be exactly identical on lots of them every single byte. There was only 1 that broke that pattern that was that file size. This is with the 68 byte files. I'm gonna guess though that it's the 88 byte edat that has the information we need to add our own DLC, even though the other two 76 byte files they have easy to read identifier information.


This is what I think is one of Sephiroth's DLC files:
5d8406c7.edat

```
........Ô...ÿÿ....ÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÍ.ÿÿÿÿÿÿP_SEV200_4P_A...p_sev200_a......
```

Another added 100 to make it Chaos instead of Cosmos. I'm pretty sure that much is at least set it stone.

I've also found that for the DLC's that use more than 1 GMO to make the outfit such as KH Cloud or Sephiroth that the coding is different in these readable strings. For example here's one of KH Cloud's:
3b3e0760.edat

```
........Á.f.ÿÿ....ÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿG_SEV101........g_sev101........
```

Laguna's DLC was 110 but see how this one is 101 instead and even more strange is it has G_ instead of P_? It's because it's a part of P_SEV100 still aka KH Cloud. This is linking to one of the external GMO files it attaches and references it with 10.1 if you will. There's others just like it for the characters that also have this such as Zidane's cape.


Am I the only one who has any interest in figuring this out? Because if I am I don't know how useful it is to post my findings so far. I started posting this in hopes that someone perhaps more experienced would come to assist me. I can provide more example files if you wish, but since PSN is down WoL is the only DLC I have isolated.
## Post #3
- Username: codestation
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jan 18, 2011 3:52 am
- Post datetime: 2011-05-08T14:58:11+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

> Reply from Zerox
>
> 
Am I the only one who has any interest in figuring this out?
You are not alone but i am trying to find a different route: removing the obfuscation of the file name. Since i can't get a dissasembly of the 012 EBOOT with prxtool (it crashes) i started to check the filenames of other games to see if i could find a pattern.

As an example: in Patapon 3 i found the the real edat names are CRC32("dlf%d"), where %d is a number from 0 to n (e.g.: dlf8 -> CF68F9B3, so the real name of CF68F9B3.edat is dlf8.edat (bald cap). If you check the 012 EBOOT (search for "dlc") you will find interesting strings who can help to figure out the real names.

To put it in short: i believe that the filenames are the result of a hash function (crc32 or another) and by cracking them we can add custom models (and songs too).
## Post #4
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-05-08T15:57:54+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

Glad to not be alone anymore on this. So you think the file names hold some significant value then huh? I suppose a good test would to be trying to rename the files of the WoL DLC and testing to see if they still work. If they don't work then obviously the name's hold value. But if they still work then there is something else at play.

Still I believe the other 4 edats included that aren't gmo or gim hold some value because if they didn't do anything they wouldn't be there.

Edit: Okay names appear to be a very big factor in this. I renamed the two 68 byte files that come with WoL that seem to identify his 4th costume's model and his assist's model. And the game crashed because it didn't know where to find the model I guess.
## Post #5
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-20T13:38:38+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

so can those gmo's be previewed in noesis?
## Post #6
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-20T22:57:56+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

If you give the decrypted EDATs the right filetypes, they can be viewed in Noesis or heard as AT3s.
## Post #7
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-21T01:50:55+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

I see..so I need a real psp to decrypt those edat files right?
Could there be an alternate way to decrypt them since my psp isn't custom firmware.
## Post #8
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-21T02:53:30+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

Sure, if you could get the pbp file signed.
## Post #9
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-21T04:03:29+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

And how does the pbp get signed?
## Post #10
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-21T05:02:14+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

I don't know.
## Post #11
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-21T06:42:16+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

Now that's a problem
## Post #12
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-06-20T03:24:49+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

So if I posted my decrpyted DLC folder would anyone be willing to try investigating?
## Post #13
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-06-21T10:11:40+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

Holy wow
Nice thread zerox im looking forward for this
## Post #14
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-08-29T14:41:13+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

I looked into this a while ago as well. I lost most of it after I updated the DLC :/

You can disable the attachments to the models like Cloud's cape. Inside it's GMO, it says g_sev101 a few times. If you were to replace every single one of them with something like g_ten101, it would disable Cloud's cape. BUT it wouldn't be attached to either Tidus or Yuna. Going by what Codestation said earlier, it probably has something to do with the name of the edat as well.

I'm gonna try some messing about to see if I could attach it to Tifa or something.

EDIT: these are the names of all of Cloud's edats:

026a4453.edat - Cape
16540e48.edat
3b3e0760.edat
40d84704.edat
47c49958.edat
5cec9420.edat
6c0e4346.edat - Main Model
6d318888.edat
719483a8.edat
74696f71.edat
90708b49.edat - Bandage on bottom of Sword
9c0c6ab1.edat
d97decc4.edat - Wing
de92d6c0.edat - Assist
eac7bf53.edat
f4294eff.edat - Portrait

Inside 40d84704.edat is just this:
(010000000100000000000000000000000000000000000000000000000000000000000000000000000800FFFFFFFFFFFF0800FFFFFFFFFFFF080000005F30300000000000)

However I compared it with 5397bac3.edat, and they are identical, the only difference is the two 08's that I have in bold. In 5397bac3, the first 08 is replaced with 0F, and the last with 00.

It would be much easier if we could get each DLC individually rather than in one big clump.

EDIT: I think I'm gonna drop it, it's too confusing
## Post #15
- Username: Dissidia World
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 05, 2021 8:25 am
- Post datetime: 2021-08-05T00:33:30+00:00
- Post Title: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

Oigan estan vivos digo ya han pasado más de 10 años de está publicación y la verdad me encantaría saber más sobre el tema porque soy fan del juego y de la saga final fantasy y siempre me gustó la idea de modearlo, osea hacer mis propios costumes, cambiar la música, hacer un mod cosas asi y hasta ahora el único buen tutorial que encontré fue este asique si están ahi les ruego su ayuda.
## Post #16
- Username: Dissidia World
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 05, 2021 8:25 am
- Post datetime: 2021-08-05T04:02:21+00:00
- Post Title: Re: Creating Dissidia012 DLC, There's 10 DLC Slots per char EDAT

In english:
Hey, they are alive, I say more than 10 years have passed since this publication and the truth is, I would love to know more about the subject because I am a fan of the game and the final fantasy saga and I always liked the idea of ​​modeling it, I mean to make my own costumes, change the music, make a mod things like that and so far the only good tutorial I found was this so if you are there I beg your help.
