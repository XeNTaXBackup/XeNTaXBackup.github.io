## Post #1
- Username: ArtFromCode
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 21, 2011 9:20 am
- Post datetime: 2011-04-25T23:37:42+00:00
- Post Title: Metal Gear Solid 4 stage.dat files

Hello.  I've been trying to figure out the format of Metal Gear Solid 4's stage.dat files so that I could, maybe, find the files (mainly models) within.  Here's what I know so far:

Inside these dats are a bunch of gibberish and a lot of "segs" structures.  They look like this:

```
size description
4    "segs"
2    0x0004 (4) //identifier?
2    Number of Table Entries
8    unknown

TABLE ENTRY FORMAT
2    unknown
2    0x4000 //another identifier?
4    offset //offset from the beginning of the header
```


In each of the entries, I ran STUNS (stupid uncompressor), and sure enough, it came up with compressed data for each one, but none of them came up with anything meaningful, so I'm thinking there's some basic encryption going on.  I know from the main executable that MGS4 uses Zlib, so that narrows compression methods down.

Can anyone help me out?  I've posted an 80 MB portion of a dat to sendspace ([http://www.sendspace.com/file/2oc9ui](http://www.sendspace.com/file/2oc9ui)).  I've also posted the output from STUNS to [http://www.sendspace.com/file/k9ivx4](http://www.sendspace.com/file/k9ivx4).  I tried to attach it, but it wouldn't attach for some reason.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-26T00:11:39+00:00
- Post Title: Metal Gear Solid 4 stage.dat files

the "segs" files aren't a problem because I have a script for them:
[http://aluigi.org/papers/bms/arcsys.bms](http://aluigi.org/papers/bms/arcsys.bms)

the problem is the archive file because it doesn't have a visible file information table, maybe it's encrypted in some way don't know.
so I have opted for a very stupid solution, the following script should be able to dump all the segs files:

```

get FULLSIZE asize
findloc OFFSET string "segs"
for OFFSET = OFFSET < FULLSIZE
    goto OFFSET
    get DUMMY long
    for
        findloc SIZE string "segs" ""
        if SIZE == ""
            break
        elif SIZE % 0x800
            goto SIZE
            get DUMMY long
        else
            break
        endif
    next
    if SIZE == ""
        math SIZE = FULLSIZE
    endif
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math OFFSET += SIZE
next
```
so you can unpack the extracted files with the arcsys.bms script, remember to select the folder as input file/folder so that you don't need to do the job manually with each file
## Post #3
- Username: ArtFromCode
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 21, 2011 9:20 am
- Post datetime: 2011-04-26T03:00:13+00:00
- Post Title: Metal Gear Solid 4 stage.dat files

Thanks for the scripts.  I did run it on an isolated seg (the dumper is taking a while) and it did seem to come up with something, but it's still gibberish.  Maybe once they're all dumped I can find something.

edit: Also, the dumper script doesn't seem to be working.  I tried it on an extracted part of the file where a seg was first, and it didn't report or dump anything.
## Post #4
- Username: ArtFromCode
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 21, 2011 9:20 am
- Post datetime: 2011-04-26T22:00:31+00:00
- Post Title: Metal Gear Solid 4 stage.dat files

I've decided to post the headers of all six of the stage.dat files, since they look very similar.  This may help in figuring out the format.

```
48 06 48 45 45 49 06 49 46 EF 33 1E 23 E7 6C EC    

Stage01.dat
48 06 48 65 65 49 06 49 C6 B6 55 7B 83 67 08 D0    

Stage02.dat
48 06 48 9B 9B 49 06 49 3A EF 7E 18 7D 7C C8 4E    

Stage03.dat
48 06 48 DA DA 49 06 49 5C 86 D9 CF 96 7E C6 C7

Stage04.dat
48 06 49 19 19 48 06 49 7E 38 34 87 AF 32 1F 81

Stage05.dat
48 06 49 3E 3E 48 06 49 54 51 E3 F2 52 91 7E 32
```


If you need me to post any more example files, I'll do so.  Also, here is a list of supported file types in MGS4 listed in the executable in case that helps, too:

dar, qar, rdv, far, mds, row, dld, rat, mtfa, at3, vab, rvb, eqpp, csr, psq, gcx, cvd, ico, gsp, tri, nv2, sds, fpo, rpd, vlm, var, phs, pdl, ptl, bpef, spu, la2, dbd, octl, rcm, ola, lt2, mtsq, vfp, raw, mdh, fcv, bin, cnp, lt3, img, mdc, octt, vib, zon, octs, nav, png, mdn, pam, abc, txn, cv4, cpef, mtra, geom, phpr, dlp, sfp, vpo, cv2, mcl, lh4, mtar, jpg, eft, ssp, mdl, mtcm, phes, mdb, van
## Post #5
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-04-29T09:33:10+00:00
- Post Title: Metal Gear Solid 4 stage.dat files

The stage.dat encryption is already known for mostly all MGS games, 2 - 4, TTS and a number of the psp titles.

If you would like to get better acquainted with the unencrypted format, investigate the slot files for now.  They are basically stage.dat files without the directory tree.  They have a definite structure, just keep the alignment of 0x800 in mind when looking at things.

More to come soon hopefully.
## Post #6
- Username: ArtFromCode
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 21, 2011 9:20 am
- Post datetime: 2011-04-29T14:53:20+00:00
- Post Title: Metal Gear Solid 4 stage.dat files

Thanks for the tip, revelation.  Any tool available to decrypt the stage.dat files?
## Post #7
- Username: ArtFromCode
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Apr 21, 2011 9:20 am
- Post datetime: 2011-05-21T22:53:06+00:00
- Post Title: Metal Gear Solid 4 stage.dat files

Still working on the stage.dats and the .slot files.  The decompressed segs only raise new questions, but with all the repeating data in the decompressed data, it's no wonder they were compressed.  Searching the Internet didn't give me anything on the encryption format of the dats/slots of any of the Metal Gear games.  I do remember coming across a quote by chrrox saying that the headers were encrypted, and he's most likely right.

I've also found a lot of "Mtar" file headers within the slot files.  Don't know if they're an image type or another type of archive, but it's something I thought was of note.
