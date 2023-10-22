## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-06T22:42:44+00:00
- Post Title: MicroVolts Online

This game is using password protected zip files anyone up to finding the password?
[http://www.microvolts.com/](http://www.microvolts.com/)
the client is not that big but if needed i can just post the client exe file.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-05-09T10:52:14+00:00
- Post Title: MicroVolts Online

the zip files are not password protected, they have only:
- a different zip local directory signature
- compressed and uncompressed size xored with 0xffffffff

I have updated zip.bms for supporting these tricks:
[http://aluigi.org/papers/bms/zip.bms](http://aluigi.org/papers/bms/zip.bms)
## Post #3
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2011-05-28T17:31:24+00:00
- Post Title: MicroVolts Online

out of curiosity where exactly are the zip files supposed to be? All I can find are various dat files.
## Post #4
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2011-05-29T12:38:45+00:00
- Post Title: MicroVolts Online

how to read the geometry from the nif file?
## Post #5
- Username: Suppercut
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 01, 2011 9:36 pm
- Post datetime: 2011-07-01T13:42:57+00:00
- Post Title: MicroVolts Online

Help me out here.

Opening model.dat:

```
------------------------------
  00000023 4294967295 Girl/
- SCRIPT'S MESSAGE:

  Error: unknown zip signature 21896 at offset 34
         if the other files have been extracted correctly it's all ok

- 1 files found in 0 seconds

Press RETURN to quit_
```

Nothing got extracted. (Edit: I get this with all other model files, including weapon.dat, rag_doll.dat, etc.)

Also, when trying the sfx file instant.dat:

```
------------------------------
  00000027 4210582478 Model.nif

Error: the requested amount of bytes to allocate is negative <-84384818>

Press RETURN to quit_
```

Again, no files were extracted.

Sorry if the solution is so easy and I'm just being a complete noob.
