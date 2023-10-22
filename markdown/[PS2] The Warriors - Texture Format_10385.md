## Post #1
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2013-05-02T22:42:11+00:00
- Post Title: [PS2] The Warriors - Texture Format

Edit: This question / problem has been solved by shakotay2   

Hi there!

Could someone please have a look at the files inside this zip:


 warriors_skybox.zip
(144.24 KiB) Downloaded 43 times

skybox_ecny is a resource from the game (some kind of RenderWare txd file) = input,
skybox_ecny.png is the texture which I ripped from an emulator = output.

The big question is, how can I convert the input into the output file?
I first tried to copy the bytes from 0x118-0x20117 and from 0x20168-0x20567 (color palette) to create a simple bmp, but I didn't get the desired result.

Thanks in advance for any suggestions!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-03T08:24:06+00:00
- Post Title: [PS2] The Warriors - Texture Format

> Reply from herbert3000
>
> The big question is, how can I convert the input into the output file?Small answer:
use steve's TXD viewer: [http://www.steve-m.com/downloads/tools/txdviewer/](http://www.steve-m.com/downloads/tools/txdviewer/)

rename skybox_ecny to skybox_ecny.txd, open it in viewer,
then extract - actual image
bmp (jpg/tga) will be created in specified path
## Post #3
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2013-05-03T15:39:25+00:00
- Post Title: [PS2] The Warriors - Texture Format

Wow! Thank you very much!  

Actually I feel very stupid right now because some time ago I already tried to extract the file with the TXD Viewer - but I used the PC version which didn't work
