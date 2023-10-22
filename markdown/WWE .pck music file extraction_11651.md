## Post #1
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-02T22:38:09+00:00
- Post Title: WWE .pck music file extraction

I'm trying to figure out the proper procedure to unpack the contents of some of the newer WWE video games which are stored in a .pck file. From searching previous threads on HCS, it seems some people found luck using QuickBMS, however I'm not sure which script they might have used to do so.

Some example pcks to look at are uploaded here: [https://mega.co.nz/#F!vckzCCSb!LfRnJDj233NGMb57HmnyOA](https://mega.co.nz/#F!vckzCCSb!LfRnJDj233NGMb57HmnyOA)
## Post #2
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T23:09:29+00:00
- Post Title: WWE .pck music file extraction

Audiokinetic WWise .PCK files are pretty common really. Just use Ravioli Game Tools, it's simple and it works for BNKs as well. 
Although you may need to use a QuickBMS script to get the filenames.
## Post #3
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-02T23:15:57+00:00
- Post Title: WWE .pck music file extraction

> Reply from SergeantJoe
>
> Audiokinetic WWise .PCK files are pretty common really. Just use Ravioli Game Tools, it's simple and it works for BNKs as well. 
Although you may need to use a QuickBMS script to get the filenames.

Could you tell me a little more about what QuickBMS script I would need?
## Post #4
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-02T23:27:10+00:00
- Post Title: WWE .pck music file extraction

Honestly I don't remember where I got it from, but I've [rehosted it here](http://puu.sh/9UjC8/b1baa4513e.txt). What it does is scan the extracted file for any embedded text strings, then appends it to the filename.

Pretty useful when dealing with PCK archives, since all extracted file have random numbers as their filenames.
## Post #5
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-02T23:34:51+00:00
- Post Title: WWE .pck music file extraction

Ran 'em through the script, same names. Oh well that's okay, I can rename them manually. More happier that Ravioli was able to extract them.
## Post #6
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-03T00:23:14+00:00
- Post Title: WWE .pck music file extraction

Looks like I spoke too soon. I am trying to extractor two other pck files and Ravioli is throwing me a message saying 'illegal characters in path'.
## Post #7
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-03T00:31:54+00:00
- Post Title: WWE .pck music file extraction

Well that's just bizarre. Never heard of that error before.

EDIT: Well [here's another thread about WWE sound files](http://forum.xentax.com/viewtopic.php?p=93910#p93910), the guy said you need to install a plugin, you could try that.
## Post #8
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-03T03:51:23+00:00
- Post Title: WWE .pck music file extraction

I've uploaded the two problem files here to see if this is just happening to me, or it's a re-producible bug:

[https://mega.co.nz/#!owwgSSZL!xeeDFJ3Yz ... 532Cy2d4qs](https://mega.co.nz/#!owwgSSZL!xeeDFJ3Yz-xIUpi_Fld5idZZ5geuFWUKH532Cy2d4qs)

[https://mega.co.nz/#!5wZ1hCKR!vBtkjmfrn ... YFq1Ha30SY](https://mega.co.nz/#!5wZ1hCKR!vBtkjmfrnhIsO6BTxfwtOS8U_Lax9bYQUYFq1Ha30SY)
## Post #9
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-04T02:59:01+00:00
- Post Title: WWE .pck music file extraction

That patch helped a bit, I can at least see inside the archive with Ravioli now, however they all show as 0 bytes. 



Trying to extract them gives the same results.
## Post #10
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-04T07:09:40+00:00
- Post Title: WWE .pck music file extraction

[I found the BMS script](http://forum.xentax.com/viewtopic.php?p=80192#p80192), you could try that.
## Post #11
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-04T09:15:57+00:00
- Post Title: WWE .pck music file extraction

I figured it out, if it helps someone out in the future, in Ravioli Extractor, I had to set the Archive Type to Wwise Sound Bank in the drop down.
## Post #12
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-07T07:46:36+00:00
- Post Title: WWE .pck music file extraction

I'm actually dealing with the pkg file from the Wii version of WWE '12. Ravi Extractor is not liking whatever it is.

I tried the 'Wwise sound engine *.pck/AKPK extractor' BMS script from here ([viewtopic.php?p=80192#p80192](http://forum.xentax.com/viewtopic.php?p=80192#p80192)) and it spit out a bunch of wavs, however I've sure they need to be properly converted to something else.

Here's one of the outputted wav files: [LINK](https://mega.co.nz/#!11pAGaYJ!J-GaJBOMFS-UyJoL_lglEgfbAFAX_b2oxwXmC98FJL4)

Let me know if you'd like me to just upload the original Wii pck file.
## Post #13
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-07-07T10:13:22+00:00
- Post Title: WWE .pck music file extraction

When you extract wavs from the Wwise engine, you need to then follow up and convert them to playable .ogg files with ww2ogg.

EDIT: Oh wait, that's not a normal wav file, that's an Lwav file. That's totally different. No clue what that is or how to convert it.
## Post #14
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-07-07T23:50:42+00:00
- Post Title: WWE .pck music file extraction

Unfortunately VGMStream is not enjoying it either. Via Foobar2000 it does show the duration, filesize, and filetype, but immediately attempting to play the file, it says '
Decoding failure at 0:00.000 (Unsupported format or corrupted file):'

Here's what VGMS has to say about it via WinAmp's Info Window:
