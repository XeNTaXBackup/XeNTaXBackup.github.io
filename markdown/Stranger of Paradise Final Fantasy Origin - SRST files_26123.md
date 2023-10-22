## Post #1
- Username: mamekoski
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 01, 2012 2:03 am
- Post datetime: 2022-12-27T04:25:31+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

i need help with this description because i'm confused with the explanation :

"To determine whether a file is encrypted, the game checks offset 0x20 in the KTSR header which immediately follows the 0x10 byte SRST header. The encryption algorithm is Blowfish in ECB mode."

"The byte value stored in that offset is the encryption key length, with the key itself following from the next byte - if the value is 0, no decryption is performed."

my question within this file is, what is the encryption key? thanks~
[0x272c6efb SRST.png](https://xentaxbackup.github.io/file/23205_0x272c6efb SRST.png)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-27T11:56:35+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

What is name of the game this file comes from?
What is the platform? PC? XBOX?

Also please attach some samples.
## Post #3
- Username: mamekoski
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 01, 2012 2:03 am
- Post datetime: 2022-12-27T15:42:55+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

> Reply from ikskoks ↑Tue Dec 27, 2022 7:56 pm at Tue Dec 27, 2022 7:56 pm
>
> 
What is name of the game this file comes from?
What is the platform? PC? XBOX?

Also please attach some samples.

it's a decrypted audio file(s) from SOPFFO PC which need to be re-encrypted to be played in-game. i couldn't attach a sample because that SRST file is over 500MBs..

i just need to know what is the encryption key based on my screenshot above.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-27T20:14:02+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

> i couldn't attach a sample because that SRST file is over 500MBs..
You can upload it to some hosting site like mega.nz, google drive etc. and then share a public link here.

> i just need to know what is the encryption key based on my screenshot above.
That's NOT how reverse engineering works
## Post #5
- Username: mamekoski
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 01, 2012 2:03 am
- Post datetime: 2022-12-28T05:28:58+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

> Reply from ikskoks ↑Wed Dec 28, 2022 4:14 am at Wed Dec 28, 2022 4:14 am
>
> 
That's NOT how reverse engineering works

sorry i haven't explained before. the description i provide above is from the decryptor's github & that's what he/she provide regarding how to re-encrypt the file. since the repo has been archived, i can't comment to reply & github doesn't have private message feature.

that's why i'm asking here, so i could understand which part of the Hex is the encryption key from the decryptor's phrase: "The byte value stored in that offset is the encryption key length, with the key itself following from the next byte - if the value is 0, no decryption is performed."
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-28T15:37:13+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

Ok, thanks for explanation. Can you send a link to this archived github repositroy? 
I can't find it anywhere.

EDIT: Btw, according to the logic described by you in the first post, key length is 7 and key is "77 45 D6 E5 64 13 ED" (as hex).
## Post #7
- Username: mamekoski
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 01, 2012 2:03 am
- Post datetime: 2022-12-29T14:23:24+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

here's the link i've been forwarded when i asked some people in P5S modding discord regarding SOPFFO archive modding, since both utilize same format & i successfully mod weapon textures in SOPFFO (but haven't got more insight with BGMs).

[https://github.com/yretenai/Cethleann/pull/36](https://github.com/yretenai/Cethleann/pull/36)

btw, should i use openssl or quickbms to execute Blowfish ECB encryption? thanks a bunch~
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-29T20:43:34+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

> btw, should i use openssl or quickbms to execute Blowfish ECB encryption?

You can use quickbms (+ reimport mode)
More info here [http://aluigi.altervista.org/papers/quickbms.txt](http://aluigi.altervista.org/papers/quickbms.txt)

This should be something like this in the script:

```
encryption bf_ecb "\x77\x45\xD6\xE5\x64\x13\xED"
```
## Post #9
- Username: mamekoski
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 01, 2012 2:03 am
- Post datetime: 2023-01-21T16:04:59+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

hello @ikskoks , sorry for the hiatus (have been busy with work). i've successfully encrypt all individual audio files, but i get a bit problem regarding how do i repack these audio files into a KTSR package before putting it into SRST file.

i provide the original KTSR file as reference, and marked the starting lines of the 1st encrypted audio.
.



d66ce491 ktsr.png (50.15 KiB) Viewed 102 times
## Post #10
- Username: mamekoski
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 01, 2012 2:03 am
- Post datetime: 2023-01-21T16:06:15+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

original KTSR file
[https://www91.zippyshare.com/v/4sO9cvvW/file.html](https://www91.zippyshare.com/v/4sO9cvvW/file.html)

encrypted individual audio files
[https://www108.zippyshare.com/v/VbTEsJWB/file.html](https://www108.zippyshare.com/v/VbTEsJWB/file.html)
## Post #11
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-01-21T19:28:25+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

Quickbms has reimport mode (I've already mentioned it earlier).
You can import files back with the same script that was used for export.
## Post #12
- Username: mamekoski
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 01, 2012 2:03 am
- Post datetime: 2023-01-22T14:26:30+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

> Reply from ikskoks ↑Sun Jan 22, 2023 3:28 am at Sun Jan 22, 2023 3:28 am
>
> 
Quickbms has reimport mode (I've already mentioned it earlier).
You can import files back with the same script that was used for export.

actually, i can't because i extracted those audios from this program [https://github.com/yretenai/Cethleann/pull/36](https://github.com/yretenai/Cethleann/pull/36)
i understand the reimport mode, but the script you provided only encrypted back each decrypted audio, so i'm a bit lost regarding to repackage them into KTSR.
## Post #13
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-01-22T16:40:20+00:00
- Post Title: Stranger of Paradise: Final Fantasy Origin - SRST files

I'm not an expert on Koei Tecmo formats, but I think that if encryption method is known and Cethleann source code is public, it should be possible to rewrite it's code as quickbms script (at least small part of it) and then use the same script for reimport.

But first, someone needs to write such script and make it public.
