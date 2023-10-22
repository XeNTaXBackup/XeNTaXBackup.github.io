## Post #1
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2016-09-27T19:50:41+00:00
- Post Title: Silent Hill 2 extractor

I put together a tool to extract the filesystem residing in the main executable of Silent Hill 2. It pertains to all .mgf files in the /data folder.

[https://github.com/Nisto/sh2ex](https://github.com/Nisto/sh2ex)

Currently it only supports the following versions:

- SLPM-65051 (v1.50)
- SLPM-65631 - Saigo no Uta - Konami Dendou Selection (v1.50)
- SLUS-20228 (v1.20)
- SLUS-20228GH - Greatest Hits (v2.01)
- SLES-50382 - Special Edition / The Collection (v1.10)

If there are any another versions that needs support, let me know, and I'll look into it (provided I can find the version). I have not found the original Saigo no Uta release, so I'm not sure it will work, but the executable in SLPM-65631 is named according to that release (SLPM-65098 -> SLPM_650.98), so it's possible they are identical. If anyone has that exact release (preferably physically), please let me know if it works.
## Post #2
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2016-10-01T19:49:33+00:00
- Post Title: Silent Hill 2 extractor

I assume this is PS2. What else are you working on for Silent Hill or Resident Evil?
## Post #3
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2016-10-03T00:16:13+00:00
- Post Title: Silent Hill 2 extractor

Yes, it's for PS2 primarily. It's unlikely I'll ever support the Xbox versions, and if I recall correctly, the PC versions are already "extracted", right?

Apart from adding support for the E3 Demo to the extractor (thus BIN/CD support as well), I don't really have anything else in the pipeline for RE or SH. But if you are looking for something, let me know.

I'm ambitious about creating a PSF/2 set for SH2/3, but resources seem scarce for documentation on PS2 RPC (Remote Procedure Call) programming, and particularly how to use it in conjunction with the modules provided by Neill Corlett. I honestly don't even know how to go about compiling PS2 ELF executables/modules, which I would need to do in order to use sceSifBindRpc and sceSifCallRpc for... stuff.
## Post #4
- Username: Nisto
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Nov 02, 2014 10:39 pm
- Post datetime: 2016-10-22T22:10:58+00:00
- Post Title: Silent Hill 2 extractor

It now supports the E3 demo.
