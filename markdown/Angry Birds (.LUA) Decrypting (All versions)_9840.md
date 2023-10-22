## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-08T14:06:38+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

So LUA files encrypted with AES 256bit CBC mode and nulled initialization vector.

Here are the keys that I managed to pull out :

Angry Birds

> Str = USCaPQpA4TSNVxMI1v9SK9UC0yZuAnb2
>
> Hex = 55534361505170413454534E56784D49317639534B39554330795A75416E6232
Angry Birds: Rio

> Str = USCaPQpA4TSNVxMI1v9SK9UC0yZuAnb2
>
> Hex = 55534361505170413454534E56784D49317639534B39554330795A75416E6232
Angry Birds: Seasons

> Str = zePhest5faQuX2S2Apre@4reChAtEvUt
>
> Hex = 7A65506865737435666151755832533241707265403472654368417445765574
Angry Birds: Space

> Str = RmgdZ0JenLFgWwkYvCL2lSahFbEhFec4
>
> Hex = 526D67645A304A656E4C466757776B5976434C326C5361684662456846656334
Angry Birds: Star Wars

> Str = An8t3mn8U6spiQ0zHHr3a1loDrRa3mtE
>
> Hex = 416E3874336D6E38553673706951307A4848723361316C6F44725261336D7445

Examples using by OpenSSL

Decrypt

```
openssl enc -aes-256-cbc -d -K 55534361505170413454534E56784D49317639534B39554330795A75416E6232 -iv 0 -in gamelogic.lua -out gamelogic.lua.dec
```

Encrypt

```
openssl enc -aes-256-cbc -e -K 55534361505170413454534E56784D49317639534B39554330795A75416E6232 -iv 0 -in gamelogic.lua.dec -out gamelogic.lua
```


Have fun
## Post #2
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-11-09T01:45:31+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

will this work for the  xbox?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-10T06:23:00+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

Do not know. Maybe
## Post #4
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-11-12T18:58:36+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

damn it doesn't i will post a new angry bids for xbox 360
## Post #5
- Username: TheCrazedGuy
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 26, 2018 11:59 pm
- Post datetime: 2018-10-09T00:24:56+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

The text is a bunch of random jimble jamble. How do i make it readable?
## Post #6
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2018-10-11T15:53:45+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

> Reply from TheCrazedGuy
>
> The text is a bunch of random jimble jamble. How do i make it readable?
What game+file(s) in it are you trying to decrypt? AB Classic gives an LZMA file after decrypting an asset based LUA, a 7z after decrypting a zip and also save data LUAs use a different encryption key that is the same encryption type, giving plain LUAs after decryption, idk about the other games...
## Post #7
- Username: TheCrazedGuy
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 26, 2018 11:59 pm
- Post datetime: 2018-10-13T01:31:59+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

> Reply from LolHacksRule
>
> TheCrazedGuy wrote:The text is a bunch of random jimble jamble. How do i make it readable?
What game+file(s) in it are you trying to decrypt? AB Classic gives an LZMA file after decrypting an asset based LUA, a 7z after decrypting a zip and also save data LUAs use a different encryption key that is the same encryption type, giving plain LUAs after decryption, idk about the other games...
Talking about .lua such as episodes.lua, settings.lua and so on...
## Post #8
- Username: TheCrazedGuy
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 26, 2018 11:59 pm
- Post datetime: 2018-10-13T01:32:42+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

If you can get the encryption key, i'll be grateful.
## Post #9
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2018-10-13T04:41:53+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

settings.lua, bi_data.lua, highscores.lua and highscores_ID.lua are save LUAs, I'm not giving you the keys for that as it could lead to more cheating for Rovio to catch. Episodes.lua and other files in the game asset database are asset LUAs, using the keys above, like I said before, LZMA16'ed 7z's are given from asset files (aside from the ZIPs) after decryption, if you remove the first 9 bytes and only get "]" at the first text, it will open as a 7z.
## Post #10
- Username: TheCrazedGuy
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 26, 2018 11:59 pm
- Post datetime: 2018-10-14T17:12:32+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

Thanks! By the way how do i edit the luas without the game crashing?
## Post #11
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2018-10-16T18:33:30+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

> Reply from TheCrazedGuy
>
> Thanks! By the way how do i edit the luas without the game crashing?

Edit what LUAs? The save LUAs, the asset LUAs or both? If its save LUAs, get the key for those then use that to decrypt to plaintext, edit, then recrypt and copy to save directory. For assets, use the keys above to decrypt, copy the LZMA header to a backup file (if on mobile version), remove it all the way in the decrypted files to "]"(delete the first 9 bytes), open them in 7Zip, extract the LUAs in them to folders where you would plan to modify them, decompile them with java -jar unluac.jar file_dec.lua > file_dec_decompiled.lua, edit it decompiled, recompile it with Lua 5.1, add and replace it into the 7z, add the LZMA header (so the game will read it legitimately, then save, recrypt, rename, inject to correct asset directory and start the game. I think many files have SHA1 checksums in the game executable (for LZMA-7z encrypted LUAs and JSONs), so modify them as well to match (IDK if this has issues if they mismatch, UPDATE: NOTHING HAPPENED, I tried on my device with a cloned copy of the game). I modified the remote_configuration_default ZIP similarly with this method.
## Post #12
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2018-11-12T17:53:43+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

Here's Angry Birds Star Wars II's AES-256-CBC encryption key, ripped right from the game's memory from the v1.5.1 final PC version:

> Str = B0pm3TAlzkN9ghzoe2NizEllPdN0hQni
>
> Hex = 4230706D3354416C7A6B4E3967687A6F65324E697A456C6C50644E3068516E69
## Post #13
- Username: RafBuilder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 04, 2019 2:33 am
- Post datetime: 2019-10-03T18:46:52+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

I try to edit some angry birds star wars bird upgrades by trying to decompile and get also bird upgrades and angry editors i get an error if i decrypt the lua after i try to open with openssl
I need help i have openssl installed so decompile failed garbage
Sorry but i am new on this forum
## Post #14
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2019-10-28T17:51:39+00:00
- Post Title: Angry Birds (*.LUA) Decrypting (All versions)

Send me the file, I'll see if it works fine.
