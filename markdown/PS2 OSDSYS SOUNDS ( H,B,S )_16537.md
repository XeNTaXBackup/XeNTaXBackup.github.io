## Post #1
- Username: XenianAlpha
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 15, 2017 4:21 am
- Post datetime: 2017-07-14T22:00:17+00:00
- Post Title: PS2 OSDSYS SOUNDS ( H,B,S )

Hi XeNTax Community,

I'm a bit new to Reverse Engineering however recently I've been trying to extract the samples that play whilst running OSDSYS, The PS2's Browser.

Now I'm aware that this is REALLY old news and the samples can be extracted via PSound using an older version of the BIOS. But from a technical perspective I'd just like to learn a bit more about it.

Here's what I've done so far; 

* Extracted a personal BIOS dump from a SCPH-77003 using ROMDIR
* Extracted 'SNDIMAGE' using ROMDIR
* Analysed the files SNDBOOTH, SNDBOOTB, SNDBOOTS using HxD
* Preformed a HELL of a lot of Extensive Research (Some sources from this very site!)

-> Found a 'SShd' header @ offset 0x12 within SNDBOOTH and a 'SSsq' header @ offset 0x10 in SNDBOOTS.
--> Analysing SNDBOOTB resulted in no headers to speak of and It doesn't seem to follow a general ADPCM standard.
---> Initial Splicing / Layout Tweaking via HxD, to no avail. Continued analysing for many days.
----> On a further Inspection beyond those days, It appeared to be similar to either a Compressed or Uncompressed 'PSX' PCM Stream.
-----> Tried using Audacity; PSX Stream = 4-Bit, Standard PCM was 8 - 16 Bit. Messing around with various settings resulted in 'Impossibly noisy' audio.
------> Preformed an edit on SNDBOOTB using Audacity. Applied a basic low pass filter, reduced the noise but only sounds reliant on bass were noticable.

So far, It seems I've tried everything and to no avail. If anyone could help me in my task to extract these samples It would be much appreciated.

Thanks for Reading.
