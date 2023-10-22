## Post #1
- Username: Nariom
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 04, 2018 6:31 am
- Post datetime: 2018-03-04T20:47:20+00:00
- Post Title: Secret of Mana remake sab files

Original [post](http://forum.xentax.com/viewtopic.php?f=17&t=17779) here but i realised it was a code thing more than a audio thing.

So I'm working on making binary files to inject alternative music in the game, specifically [Secret of Mana: Resonance of the Pure Land](https://ocremix.org/album/84/secret-of-mana-resonance-of-the-pure-land) from OC ReMix.

There is a [tool](https://github.com/Thealexbarney/VGAudio) for the encoding, and VGMstream is reading the file somehow. I didnt find any documentation on the sab structure, but VGMstream [code](https://github.com/kode54/vgmstream/blob/master/src/meta/sqex_sead.c) gives some insight. One guy is attempting a reverse engineneering. My hope is maybe someone from hcs64 may have information on the format since they writed the code. So far we now it's a binary with a Square-Enix SAB header containing the HCA encoded music, it also has some information about header size, file size, ... and it's close to the mabf format, for which someone wrote a template [here](https://gist.github.com/Thealexbarney/698664af1aed7122a33f591f96498f30).

Any idea on how to achieve that please? I can read and write some code but this is a bit over my head.
