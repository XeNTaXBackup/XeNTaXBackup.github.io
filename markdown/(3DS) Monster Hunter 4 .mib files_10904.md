## Post #1
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2013-10-24T13:08:47+00:00
- Post Title: (3DS) Monster Hunter 4 *.mib files

Hey everyone,

sadly nobody was interested or able to help with the MH3U quest files but maybe I'm more lucky with MH4, Capcoms latest 3DS MonHun title.

The .mib format has been used to store quest data in previous games already but same as with the MH3U .quest files there seems to be an extra layer of encryption or something.

Here are some examples that I dumped. Mainly interested in the Eventquest\ and Challengequest\ files but maybe the other text files share the same encryption and can help to crack the encryption more easily.

Thank you very much.
[MH4_online.zip](https://xentaxbackup.github.io/file/6730_MH4_online.zip)
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-10-25T20:28:53+00:00
- Post Title: (3DS) Monster Hunter 4 *.mib files

It's probably still encrypted since no one's publicly leaked the 3ds ROMFS decryption keys, the only methods currently for decrypting involve CTRtool and a debug 3ds (there are less than a half dozen of these in the hands of hackers)
Edit: wait, those txt files came from it inside the ROMFS too right? How did you manage that?
Double edit: is questlist.txt yours or from inside the .3ds rom?
## Post #3
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2013-10-26T07:35:08+00:00
- Post Title: (3DS) Monster Hunter 4 *.mib files

They don't come from inside the ROM, Capcom offers free DLC and I just dumped these files using a proxy tool. These are however the legit files since I can remap i.e. Quest A for Quest B and the game accepts it. Once I change a single byte tho, the game spits out an error message. So there is probably some checksum on the files (maybe the second to last 4 bytes since the last 4 bytes seem to describe the actual file length).

questlist.txt is mine ^^
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-10-26T16:52:14+00:00
- Post Title: (3DS) Monster Hunter 4 *.mib files

Oh. derp. I feel stupid didn't know that.
## Post #5
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2013-11-02T15:59:24+00:00
- Post Title: (3DS) Monster Hunter 4 *.mib files

*push*

According to Falo, an 8-bit XOR encryption is used. At first glance he thought it would be 0x2E 0x48 0x4C 0x12 0x10 0x0E 0xF0 0x38 but obviously this doesn't seem to fully decrypt the files but at least makes them look more structered.

In the included txt you can find the japanese name of the quests or the name of the content stored in the odt files. Maybe it helps to find the right key...
## Post #6
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-08-24T09:21:39+00:00
- Post Title: (3DS) Monster Hunter 4 *.mib files

> Reply from Pepper
>
> It's probably still encrypted since no one's publicly leaked the 3ds ROMFS decryption keys, the only methods currently for decrypting involve CTRtool and a debug 3ds (there are less than a half dozen of these in the hands of hackers)
Edit: wait, those txt files came from it inside the ROMFS too right? How did you manage that?
Double edit: is questlist.txt yours or from inside the .3ds rom?

There's NO KEYS FOUND YET. The 3ds is using a keyscrambler, the 3ds itself contains the keyX and the game contains the keyY. Then the 3ds is using the keyscrambler for decrypt the game. a.k.a. the key is different for every 3ds game, you have to have the keyX. And she can't be reversed easily b\c hardware keyscrambler
