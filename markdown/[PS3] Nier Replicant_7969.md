## Post #1
- Username: Dorigon
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2012 3:04 am
- Post datetime: 2012-01-01T20:32:21+00:00
- Post Title: [PS3] Nier Replicant

Hello, first I want to apologize for my bad English,I'll do my best to explain my problem and you can understand xD
I'm trying to adapt a Spanish translation of the game  nier for xbox360 to the ps3 version. As I understand it in the xbox360 version the files are uncompressed but in the PS3 version the files are compressed an encrypted in a SDATA.
Using the tool "descrsdat" of Asmodean  I decrypted the SDATA but now I don´t know the next step, I have tried using the "cpkd" tool obtained here but I get error message "this is not a cpk file" so I've also tried with the tools "extttdpk_v1" and "extttdpk_v2"
but windows gives me an error message "The application has unexpectedly finished"
As I said before at this point I'm totally lost. I need to unpack and future repackage this file.
I leave the hex code from the beginning of the file (Stable.SDATA) decrypted
I would upload the file to megaupload but weighs more than 4 gb

```
#.|....V........ V...)V...7V...CV...M....UV...\V...g....p....{....„V...ŒV...
—.... V...¨V...º....Ê....ØT...ÝT...ãT...ê....ð....û.....R....R....R... R...&....
-T...1Z...9....?T...GT...M..............x......Y˜...............`€.....^........
3Ð......p........ø.....È¦*.....Û‹a...¡.......................U........

<NULL>.CpkHeader.UpdateDateTime.FileSize.ContentOffset.ContentSize.
TocOffset.TocSize.TocCrc.EtocOffset.EtocSize.ItocOffset.ItocSize.ItocCrc.
GtocOffset.GtocSize.GtocCrc.EnabledPackedSize.EnabledDataSize.TotalDataSize.
Tocs.Files.Groups.Attrs.TotalFiles.Directories.Updates.Version.Revision.Align.Sorted.
EID.CpkMode.Tvers.Comment.Codec.DpkItoc.CPKMC2.10.00, DLL2.73.00........uK¥‰............
```
## Post #2
- Username: Dorigon
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2012 3:04 am
- Post datetime: 2012-01-03T12:09:41+00:00
- Post Title: [PS3] Nier Replicant

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Dorigon
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2012 3:04 am
- Post datetime: 2012-01-03T18:01:16+00:00
- Post Title: [PS3] Nier Replicant

Well I've been trying with cripackedfilemaker tool and I can see the file content.
But during the extraction it fails, I've also tested with the bms and this script [http://pastebin.com/VCQcKkwD](http://pastebin.com/VCQcKkwD)
but the program stops  "the program has unexpectedly finished" having extracted 3.49 gb, the complete file weighs 4.06gb
