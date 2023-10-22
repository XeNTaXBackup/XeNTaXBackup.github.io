## Post #1
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2018-12-28T02:51:46+00:00
- Post Title: Monsters Inc Scare Island (PC) YYZ and XA sound file

I have these two files that I'm trying to export in order to import back another file, I send here two examples in order to see if is possible to manage an import and export.

YYZ file somehow is possible to open on audacity as a Raw file, Signed 16-bit PCM, Big-Endian, 1 channel Mono,  0 bytes, 100% of Quantity, 44100hz and then slow down the speed of the sound.

The XA file is not like the PS1 XA files, this XA is basically a stand alone file with one audio attached. Basically is a port to PC with some obfuscated attributes.


Samples: [https://www.mediafire.com/file/qh8a0hc5 ... s.zip/file](https://www.mediafire.com/file/qh8a0hc5vwz8rzt/Samples.zip/file)
## Post #2
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2020-07-24T14:23:20+00:00
- Post Title: Monsters Inc Scare Island (PC) YYZ and XA sound file

About this question I had it figured it out.
For the .xa files (This also applies for these PC games ports: Bugs Bunny Lost in Time/Bugs Bunny Taz Time Busters/Grinch/Jersey Devil) they are encoded in adpcm. In the attachment you will find the Encoder/Decoder. Just place the .xa files there and run the decode.bat to decode them to wav. To encode, place your wav files (Stereo, 44100Hz) and run the encode.bat


The YYZ files are just cryptographed AIFF sounds.
Use 010 editor to open the YYZ and then Binary Invert it, Signed Byte FF and save it.  Now you have your AIFF file and you can open with audacity.

To convert back to a YYZ cryptographed file, go to Tools > Operations, Binary XOR, unsigned Byte, operand FF Hex.
[adpcmdec.zip](https://xentaxbackup.github.io/file/18510_adpcmdec.zip)
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-24T22:02:10+00:00
- Post Title: Monsters Inc Scare Island (PC) YYZ and XA sound file

Nice! Are there any sources for this imaenc tool?
## Post #4
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2020-07-25T00:05:13+00:00
- Post Title: Monsters Inc Scare Island (PC) YYZ and XA sound file

The only source I got was from this russian site: [http://we.easyelectronics.ru/Soft/szhat ... adpcm.html](http://we.easyelectronics.ru/Soft/szhatie-zvuka-v-ima-adpcm.html)
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-25T09:33:36+00:00
- Post Title: Monsters Inc Scare Island (PC) YYZ and XA sound file

Ok, thanks.
## Post #6
- Username: DaedraMurderer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 25, 2021 7:59 am
- Post datetime: 2021-01-25T00:11:25+00:00
- Post Title: Monsters Inc Scare Island (PC) YYZ and XA sound file

THANKS!!!!!!!!! I was searching for this!!!! I'm redoing BBLIT from scratch because I love this game, and this saved me, THANKS!!!
When the game is released I will make sure to put your contribution in the credits
