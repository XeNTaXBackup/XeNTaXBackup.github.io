## Post #1
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2018-07-17T20:08:44+00:00
- Post Title: The Last of Us .bnk sound files

Hi, does anyone know of a way to extract the last of us .bnk sound files?
example file: [https://drive.google.com/open?id=1awpjh ... KC3Mu6UsSp](https://drive.google.com/open?id=1awpjhGxB4Gn6TLth6BlGgUKC3Mu6UsSp)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-07-18T11:48:28+00:00
- Post Title: The Last of Us .bnk sound files

[Download VGMToolbox r1045](https://mega.nz/#!JbIFwCTI!23KT5v1ZOw2kdGRU9fR53oOMEzZGG_EYKIdE-EC5kDI)

Open VGMToolbox and go to VGMToolbox > Misc. Tools > Extraction Tools > Generic > Advanced Cutter / Offset Finder

Use the following settings to extract the ATRAC-3 files.



Use vgmstream to playback/convert them
## Post #3
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-18T22:54:09+00:00
- Post Title: The Last of Us .bnk sound files

Or, you simply use Dragon UnPACKer 5 and will extract them as .wav, then you rename them to .at3, and using foobar2000/vgmstream-plugin you can play/convert them to your hearts content .

Isn't it nice to have options?
## Post #4
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2018-07-21T12:03:25+00:00
- Post Title: The Last of Us .bnk sound files

> Reply from mono24
>
> Or, you simply use Dragon UnPACKer 5 and will extract them as .wav, then you rename them to .at3, and using foobar2000/vgmstream-plugin you can play/convert them to your hearts content .

Isn't it nice to have options?

Neither of the methods worked, dragon unpacker said not recognised, and vgmtoolbox didnt give anything that at3 convertor could read
## Post #5
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-07-21T12:40:28+00:00
- Post Title: The Last of Us .bnk sound files

What AT3 converter are you using?

vgmstream can convert them to WAV and play .AT3 files natively using Winamp or foobar2000.

[Download vgmstream](https://www.dropbox.com/s/ec94ocnkqgofhy7/vgmstream-r1050-1393-gbf8534a-test-u.zip?dl=0)

I included two batch files - Test.bat and Test (No Looping).bat for easy conversion of multiple files.

Put those files in the same folder as vgmstream and run one of the batch files.

Test.bat will loop songs 2x before fading out over 10 seconds. Test (No Looping).bat doesn't loop the file at all/add a fade out.
