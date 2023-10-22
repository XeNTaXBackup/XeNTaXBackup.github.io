## Post #1
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-05T16:43:10+00:00
- Post Title: EVOLVE Stage 2 PAKs extraction

Hey all.

Was wondering if any of you, that has knowledge in CryEngine PAKs archives, can please take a look in making the updated EVOLVE Stage 2 archives extract, ever since they re-relased this version and updated it with new content, files can no longer be extracted, the RSA key is the same, just structure seems changed for either how are being decrypted/extracted.

In the link below I included an OLD sample that can be extracted, and a NEW one that can no longer be extracted for comparison as well as a monster and character smaller samples, also the exe tool with its required KEY is included, as well as the old source code that everything was based on regarding this decryption/extraction tool.

[https://mega.nz/#F!q8VChI4C!lll1OHNVULRrhHqLDDCc4A](https://mega.nz/#F!q8VChI4C!lll1OHNVULRrhHqLDDCc4A)

Thank you.
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-07-27T16:52:41+00:00
- Post Title: EVOLVE Stage 2 PAKs extraction

Just a nudge, hoping it may get noticed by someone experienced.
## Post #3
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2021-10-18T16:24:37+00:00
- Post Title: EVOLVE Stage 2 PAKs extraction

I modified the tool decrypt to export the CDRInfoDecrypt.
The old SAMPLE is the "Central directory" (in zip structure) but the new one is not.
So the key or algo is wrong.
[pakDecrypt__.zip](https://xentaxbackup.github.io/file/21040_pakDecrypt__.zip)
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-10-18T22:23:05+00:00
- Post Title: EVOLVE Stage 2 PAKs extraction

> Reply from dzika ↑Tue Oct 19, 2021 12:24 am at Tue Oct 19, 2021 12:24 am
>
> So the key or algo is wrong.
Thank you for looking in to it, appreciated.

There are only two keys stored in the executable, only one of the keys is working with OLD assets, but not the NEW ones, and since the structure of the archive has been changed, it cant be a wrong key.

```

30818902818100A2D11F0C51FA6B451D7E05FE3F06725610A9A77B674FB665F4A12BCF07CD944F6EBF9DF30FCC7B63EB3DA5E659523AA7D854AC389D5922693BBA599E82951272D71F1F55434B7BBC9CDDE60507714CE53D8411F91AB0C124905ADE7B249E988606351AEF2C59F5F4CA28CA3C7ACBE77AA55691E0984E16433624A15BE375B0530203010001

```

also [signsrch](http://aluigi.altervista.org/mytoolz.htm#signsrch) shows the following, unfortunately no clue how to use this info beyond this:

```

Signsrch 0.2.4
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
  optimized search function by Andrew http://www.team5150.com/~andrew/
  disassembler engine by Oleh Yuschuk

- open file "Evolve.exe"
- 57009728 bytes allocated
- load signatures
- open file \steamapps\common\EvolveGame\bin64_SteamRetail\signsrch.sig
- 3075 signatures in the database
- WARNING:
  the file loaded in memory is very big so the scanning may take many time
- start 12 threads
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
...

  428d15fe 2545 anti-debug: IsDebuggerPresent [..17]
  4365cc76 917  SSH RSA id-sha1 OBJ.ID. oiw(14) secsig(3) algorithms(2) 26 [..15]
  43b4c620 1038 padding used in hashing algorithms (0x80 0 ... 0) [..64]

- 3 signatures found in the file in 45 seconds
- done
```

And this does not work either in same manner, as the DLL specified does NOT exist in this game, the key is stored inside the executable.
[https://zenhax.com/viewtopic.php?f=4&t=9233](https://zenhax.com/viewtopic.php?f=4&t=9233)
[http://atom0s.com/forums/viewtopic.php?f=11&t=223](http://atom0s.com/forums/viewtopic.php?f=11&t=223)
