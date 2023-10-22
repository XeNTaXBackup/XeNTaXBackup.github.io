## Post #1
- Username: Harmonea
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 02, 2021 10:37 pm
- Post datetime: 2021-09-04T19:56:49+00:00
- Post Title: Tears of Themis text file archive

Hi there,

I'm looking to unpack an archive of text config files for Tears of Themis. I'm able to see where to start but uncertain how to proceed.

The folder in question contains a series of unencrypted .wmv containers and one "PBStaticConfigure.xmf" that I can tell shows (1) the order to stitch the wmv containers together, and (2) instructions that I do not yet have the knowledge to read to split them back apart. I was able to find a wmf unpacker on this forum [for another game](https://forum.xentax.com/viewtopic.php?f=16&t=22170), but it didn't work here -- perhaps the file format is slightly different? -- the error message I receive is [here](https://i.imgur.com/6hvPfkC.png).

I've attached here PBStaticConfigure.xmf, the first of the .wmv containers it's looking at, and another person's successful unpack of the first two files (unfortunately the person who did this successfully is neither continuing to update the data nor willing to share scripts, which is why I'm looking to step up to the plate).

I'm usually able to muddle my way through things like this if I have examples to follow like this, so please forgive my having to ask for help here. Would really appreciate any pointers, tips about how to modify that existing script, or other existing scripts anyone might be able to give. T.T

Thanks for your time.
[PBStaticConfigure.7z](https://xentaxbackup.github.io/file/20737_PBStaticConfigure.7z)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-09-05T14:10:02+00:00
- Post Title: Tears of Themis text file archive

> Reply from Harmonea ↑Sun Sep 05, 2021 3:56 am at Sun Sep 05, 2021 3:56 am
>
> I was able to find a wmf unpacker on this forum for another game, but it didn't work here -- perhaps the file format is slightly different?
They're different, just not "slightly" though. Here's a BMS script for this format:


 xmfUnpack.zip
(575 Bytes) Downloaded 25 times
## Post #3
- Username: Harmonea
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 02, 2021 10:37 pm
- Post datetime: 2021-09-05T19:47:35+00:00
- Post Title: Tears of Themis text file archive

Thank you very VERY much. Seriously. Sorry if it was more work than I initially thought, I just assumed it'd be similar since it was the same dev....

Now to poke these bytes files. hup~
