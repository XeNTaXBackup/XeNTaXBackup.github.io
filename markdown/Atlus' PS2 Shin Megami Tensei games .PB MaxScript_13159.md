## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-08-06T14:22:18+00:00
- Post Title: Atlus' PS2 Shin Megami Tensei games *.PB MaxScript

The first model format I ever started working on, and it took me a damn long time to finish it, lol.
Even now it's not 100% done, the material importing is still a bit sketchy and relies on an enormous switch case.
There's a handful of models that have a flag set and I don't know why those don't import properly.. If I ever do figure it out I'll update the script.
Another note, the script seems to error the first time it's run, but running it a second time makes it run as it should.

This script supports:
- Importing bones, weights
- Importing vertex colors
- Importing morphers
- Converting embedded textures and output them to DDS
- Auto-texture importing

What it doesn't support:
- Import vertex normals (some weird shenanigans going on with that part, due to how the models are stored)
- A handful of models that deviate from the norm, causing them to form an uncomplete mesh

If there's any specific issues while using the script, feel free to post a reply in this thread.

As far as extracting these games goes, you can use aluigi's quickbms script to extract the IMG file
[http://aluigi.altervista.org/papers/bms ... tensei.bms](http://aluigi.altervista.org/papers/bms/others/shin_megami_tensei.bms)

[http://www.mediafire.com/download/6m05h ... B_bak_7.7z](http://www.mediafire.com/download/6m05hgdhsrpi9bb/Atlus_PB_bak_7.7z)
[Atlus_PB_bak_7.7z](https://xentaxbackup.github.io/file/9488_Atlus_PB_bak_7.7z)
## Post #2
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2016-10-24T19:10:36+00:00
- Post Title: Atlus' PS2 Shin Megami Tensei games *.PB MaxScript

Like you said some of them do not import at all...I've discovered a few that DO import, but not properly. Here's two of them that have this weird quirk. I assume these are the models of the 'final boss' of Digital Devil Saga 2.

[https://www.dropbox.com/s/ri4l1xs2f1zimpk/on.zip?dl=0](https://www.dropbox.com/s/ri4l1xs2f1zimpk/on.zip?dl=0)
