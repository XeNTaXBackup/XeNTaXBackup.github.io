## Post #1
- Username: UmTeam
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 09, 2017 4:22 pm
- Post datetime: 2017-07-09T08:43:38+00:00
- Post Title: Need help pulling Skate 3 user-made videos

Hello,
I'm completely new to this and have no idea what I'm doing so please bear with me.
I tried following this [viewtopic.php?f=13&p=39165#p39165](http://forum.xentax.com/viewtopic.php?f=13&p=39165#p39165) using QuickBMS and copy-pasted the EA *.mus extractor code written by AlphaTwentyThree into a bat file.  It does nothing and I am positive I'm missing something or did it wrong.  If anyone would be willing to walk me through extracting and converting the files to something watchable, or even any tidbit at all would be greatly appreciated.

Extra, maybe useful, Information:
I tried downloading the vids onto a usb off the xbox and then using Modio on PC I extracted the files from the hidden file "REPLY_SKATER".
All of the files pulled end in a .B or .H and have a naming convention like 1.B, 1.H, 1A.B, 1A.H, etc. along with a few files without extensions towards the end named DDATA, INDEX, and RMCDEL.
I used a hex editor after reading that sometimes the type of program needed to open it is written in there but it was just random letters, numbers, and symbols.  I'm assuming encrypted?? I have no clue.
I've also tried using a file joiner to combine like-named files to no luck, it just creates a file with no extension.
Honestly I'm just throwing everything at the wall to see what sticks, to no avail yet.

Edit: Ok I found this tutorial video [https://www.youtube.com/watch?v=xZONf5fXEOg](https://www.youtube.com/watch?v=xZONf5fXEOg), found the skate3 bms script using the bms search and how to use it, the only problem I have is finding how to extract the file itself as trying to run the "1.B" files through the script just brings up an error.  Where do I go from here??

Error Messages:
(File after extracted by Modio)
Error: incomplete input file 0: C:\Downloads\Programs for attempting to extract skate 3 vids\quickbms\Skate 3 Vids\1.B
       Can't read 4 bytes from offset 00f00020.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0    99%   15728646   15728672   . offset 00f00020

Last script line before the error or that produced the error:
  27  get OFFSET long

Or 
(File from hidden folder before being extracted by Modio)
Error: incomplete input file 0: C:\Programs for attempting to extract skate 3 vids\quickbms\00000001\ALIAS_SKATER
       Can't read 4 bytes from offset 00521000.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0    99%   5378022    5378048    . offset 00521000

Last script line before the error or that produced the error:
  27  get OFFSET long
