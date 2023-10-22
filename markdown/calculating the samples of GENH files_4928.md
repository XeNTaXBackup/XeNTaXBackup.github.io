## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-25T20:33:14+00:00
- Post Title: calculating the samples of GENH files

Hi everyone! As the GUI of the Generic Header Creator isn't that user-friendly I decided to write some QuickBMS scripts that create headers. The project started when I realized that it would be neat to automatically add a header to the extracted Playstation ADPCM files of the first old Dead To Rights. However, I have no idea how to calculate the sample count out of the file size! E.g. a file of 0x760000 bytes of Playstation 4-bit ADPCM data has 0x674000 samples - but how do I get there?
Can anone please explain this to me? 
Thanks a lot in advance!
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2010-10-20T03:10:28+00:00
- Post Title: calculating the samples of GENH files

The formula for PS2 Sample Count is as follows:
# of bytes / 16 / channels * 28

So, in your case (assuming 2 channel audio)
0x760000 / 16 / 2 * 28 = 0x674000

You can find this formula, and the formulas for other GENH supported formats in the [source code for VGMToolbox](http://vgmtoolbox.svn.sourceforge.net/viewvc/vgmtoolbox/?view=tar), in the ["vgmtoolbox\format\VGMToolbox\format\util\GenhUtil.cs"](http://vgmtoolbox.svn.sourceforge.net/viewvc/vgmtoolbox/format/VGMToolbox/format/util/GenhUtil.cs?revision=677&view=markup) file. See the BytesToSamples() function.

<spam>You'll also find that VGMToolbox has a GENH creator as well.  Maybe you'll find it more to your liking.</spam>
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-20T03:54:40+00:00
- Post Title: calculating the samples of GENH files

Cool, thanks for the clarification! =)
I've changed my approach to the original format headers now (as far as possible), so for Playstation 2 ADPCM it's a standard *.ss2 header. After all, generic headers have the risk that they won't be supported in ten years, who knows. But the original headers will more likely be supported by various programs. And, additionally, I find them more appealing.
