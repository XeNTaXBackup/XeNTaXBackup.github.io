## Post #1
- Username: JeffLee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 05, 2020 9:24 pm
- Post datetime: 2023-01-18T17:39:36+00:00
- Post Title: Extracting and Converting Voice files for Prey (2017)

Hi,

I'm trying to extract and convert (+repackage) Voice files for Prey (2017).
I've extracted BNK and WEM files from Prey/Localization/english.pak using PreyConvert ([viewtopic.php?t=16241#p130356)](https://forum.xentax.com/viewtopic.php?t=16241#p130356%29)).
The game uses wwise, and I've tryied using Bnkextr([https://github.com/eXpl0it3r/bnkextr](https://github.com/eXpl0it3r/bnkextr)), This script([https://github.com/rickvg/Wwise-BNKExtract](https://github.com/rickvg/Wwise-BNKExtract)) & Ravioli Game Tools ([https://www.scampers.org/steve/sms/other.htm#ravioli](https://www.scampers.org/steve/sms/other.htm#ravioli)); to extract BNK files, but to no avail. Bnkextrct exits with "No WEM files discovered to be extracted" and Ravioli Game Tools doesn't list any files.

I've also tryied to use ww2ogg([https://github.com/hcs64/ww2ogg](https://github.com/hcs64/ww2ogg)) with the "--pcb packed_codebooks_aoTuV_603.bin" argument, but that didn't work either, it prints "Parse error: expected 0x42 fmt if vorb missing" and exits.

According to file([https://github.com/file/file](https://github.com/file/file)), WEM files are "RIFF (little-endian) data, WAVE audio, Microsoft ADPCM, mono 44100 Hz" and bnk files are "Wwise SoundBank (little-endian), version 113, id <ID>, english (US)".

Does anybody here know how to extract and repack such files?
Thanks in advance.
