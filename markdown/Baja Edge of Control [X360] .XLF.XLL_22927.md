## Post #1
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-10-31T13:48:58+00:00
- Post Title: Baja: Edge of Control [X360] *.XLF/*.XLL

Hello everyone, I'd like to ask you for help with unpacking [this archive](https://mega.nz/file/VVUVwCxS#swi7e1ruuy5-i631tZu5uQ0JbVKRMvtwR4rrpO0H53o). There's a pair of files: 360.XLF and 360.XLL, the latter seems to contain filenames & possibly offsets for every asset stored in its XLF companion.
Actually 360.XLF file is huge, its size is 2,62 GBs; it's the reason I only included the first & last 16 MBs of it.

Goodbye & thanks in advance!
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-31T22:26:36+00:00
- Post Title: Baja: Edge of Control [X360] *.XLF/*.XLL

Did you try to use offzip on this archive?
[https://zenhax.com/viewtopic.php?t=5](https://zenhax.com/viewtopic.php?t=5)
## Post #3
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-11-01T10:22:13+00:00
- Post Title: Baja: Edge of Control [X360] *.XLF/*.XLL

Not yet but wouldn't I get a bunch of nameless IE simply numbered files if I use Offzip? I'd better wait & see if 360.XLF can be unpacked with filenames & extensions contained in 360.XLL.

Best regards!
## Post #4
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-11-06T12:02:22+00:00
- Post Title: Baja: Edge of Control [X360] *.XLF/*.XLL

Hi guys, I hope you're fine with me posting it here because this hardly requires starting an entirely new topic.

Anyway [here you can find PS3 archive samples](https://mega.nz/file/EBF3QA7b#F7aDcRFWfWdPIc9hebcMdw15_-xRuELdwVIgr-RtPPM) from the same game. I wish those prove easier to figure out & unpack...

So long & good luck with this pesky bigfile format!
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-11-06T18:25:57+00:00
- Post Title: Baja: Edge of Control [X360] *.XLF/*.XLL

This BMS script for now can help you unpack the conatiner.


 xllExtractor.zip
Compatible with X360/PS3 (580 Bytes) Downloaded 15 times
## Post #6
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-11-07T09:40:08+00:00
- Post Title: Baja: Edge of Control [X360] *.XLF/*.XLL

Thanks man!
BTW your script seems to work on PS3 archive too, I had to change
idstring "\x01\x00"
to
idstring "\x02\x00"
, however.

Now I've got pairs of *.PAK/*.toc files & I'd love to get a bit of assistance with proper extraction of their contents.
[Here's a bunch of them](https://mega.nz/file/NRtmiDKA#WcH3CiRNw1VBx_UcoCZnSf0dXgnTxOpBYyccU1_K_iE) (samples come from both platforms) for you to inspect & try to figure 'em out.

Thnx in advance!
Best regards, GenericRipper.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-11-07T12:33:13+00:00
- Post Title: Baja: Edge of Control [X360] *.XLF/*.XLL

> Reply from GenericRipper ↑Sat Nov 07, 2020 5:40 pm at Sat Nov 07, 2020 5:40 pm
>
> 
Thanks man!
I always feel such words are pale while a simple click on the thumb button can speak louder. 

> Reply from GenericRipper ↑Sat Nov 07, 2020 5:40 pm at Sat Nov 07, 2020 5:40 pm
>
> I had to change idstring ... however.
Script updated at the same post for compatibility with PS3 files.

> Reply from GenericRipper ↑Sat Nov 07, 2020 5:40 pm at Sat Nov 07, 2020 5:40 pm
>
> 
Now I've got pairs of *.PAK/*.toc files & I'd love to get a bit of assistance with proper extraction of their contents.
Script for the toc files:


 pakUnpacker.zip
Patched (760 Bytes) Downloaded 16 times


Just make sure to keep the pak file in the same path.
## Post #8
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-11-08T17:03:57+00:00
- Post Title: Baja: Edge of Control [X360] *.XLF/*.XLL

Thanks but I have to say that I get an "incomplete input file" error [on this file ](https://mega.nz/file/JMdnHaDL#_HzF0BV4G4jqjT5iXredG14xOX-EJ9scMbbq7OBHcys) (both platforms). Can you please check it & see if it might be fixed?

Later!
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-11-09T11:57:42+00:00
- Post Title: Baja: Edge of Control [X360] *.XLF/*.XLL

> Reply from GenericRipper ↑Mon Nov 09, 2020 1:03 am at Mon Nov 09, 2020 1:03 am
>
> 
I get an "incomplete input file" error on this file (both platforms)
Well, there're 5 files of zero size in both PAKs, which corrupted the script. Patched script is posted at the same post.
