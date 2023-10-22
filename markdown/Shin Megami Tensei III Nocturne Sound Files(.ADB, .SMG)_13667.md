## Post #1
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2015-12-13T02:26:55+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

So, I stumbled across two sound formats: .ADB(streamed ADPCM) and .SMG(sequenced music).

The .ADB format is tricky enough if you don't know th exact values while using vgmtoolbox - as for .SMG format - my guess is that they contain psf2 data, but I simply don't know how to handle them.

Oh and here are the samples just in case:
[https://mega.nz/#!lUElXRDK!OvnyZFyL2PBo ... AmlU0nyFIs](https://mega.nz/#!lUElXRDK!OvnyZFyL2PBoRhndO1INYVjVUar3IeyC7AmlU0nyFIs) - .ADB file
[https://mega.nz/#!ANlEkIrI!JM_XXAI1c9g5 ... 5sKcDNLAZM](https://mega.nz/#!ANlEkIrI!JM_XXAI1c9g5uOt9vqpuLqJ_FUZ_BBOTt5sKcDNLAZM) - .SMG file

Any ideas?
## Post #2
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2015-12-20T16:33:35+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

Bump.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-24T17:23:01+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

This ADB file contains some cut parts of textures, 3d-coordinates, and scripts. Didn't find any sound here.

Did you look into the file?

```
DEVIL_0x5C_PATH=$(REMOTE_BASE)/shirou/t3/damy0z
DEVIL_0x5C_BASE=$(DEVIL_0x5C_PATH)/damy0z
0x50/0x5c/0x5c_b.MB 0x50/0x5c/0x5c_b.TB: \
		$(wildcard $(DEVIL_0x5C_PATH)/*.tmx) \
		$(DEVIL_0x5C_BASE)t.T3
	$(MDLCNV) $(MDLCNV_FLAGS) --tex-path $(DEVIL_0x5C_PATH) $(DEVIL_0x5C_BASE)t.T3 0x50/0x5c/0x5c_b.MB

DEVIL_0x5C_MOTION_SRC= \
		$(DEVIL_DUMMY_BASE)t.T3 \
		$(DEVIL_DUMMY_BASE)k.T3 \
		$(DEVIL_DUMMY_BASE)m.T3 \
		$(DEVIL_DUMMY_BASE)d.T3 \
		$(DEVIL_DUMMY_BASE)h.T3 \
		$(DEVIL_DUMMY_BASE)i.T3 \
		$(DEVIL_DUMMY_BASE)s.T3 \
		$(DEVIL_DUMMY_BASE)u.T3 \
		$(DEVIL_DUMMY_BASE)n.T3
0x50/0x5c/0x5c_b.AB: $(DEVIL_0x5C_MOTION_SRC)
	$(MOTCNV) $(MOTCNV_FLAGS) -o $@ $^
```
## Post #4
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2015-12-26T13:51:55+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

> Reply from daemon1
>
> This ADB file contains some cut parts of textures, 3d-coordinates, and scripts. Didn't find any sound here.

Did you look into the file?
Ahh, maybe I was wrong then...

Anyways, got any sings of the SMG file?
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-29T19:44:11+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

> Reply from AnonBaiter
>
> Anyways, got any sings of the SMG file?

I'm not an expert on PS midi
## Post #6
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2015-12-29T23:41:34+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

> Reply from daemon1
>
> AnonBaiter wrote:Anyways, got any sings of the SMG file?

I'm not an expert on PS midi
Ah, I see... Thanks for the help anyway.
## Post #7
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2016-01-27T19:22:15+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

Whatever extractor you're using is not functioning properly. The actual adb files are just vag streams.
## Post #8
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-01-27T21:36:49+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

> Reply from TGE
>
> Whatever extractor you're using is not functioning properly. The actual adb files are just vag streams.
Really? If so, what can I do to convert them?
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-29T15:52:11+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

> Reply from AnonBaiter
>
> TGE wrote:Whatever extractor you're using is not functioning properly. The actual adb files are just vag streams.
Really? If so, what can I do to convert them?

You must extract them properly. Only then you can convert them.
## Post #10
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-01-29T23:20:20+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

> Reply from daemon1
>
> AnonBaiter wrote:TGE wrote:Whatever extractor you're using is not functioning properly. The actual adb files are just vag streams.
Really? If so, what can I do to convert them?

You must extract them properly. Only then you can convert them.
I'm a bit fuzzy about which tool should I use to extract the .adb files properly(being that I have never extracted them in the first place) so should I start using a BMS script or something?


EDIT: I found an unseen tool on aluigi's site(vagguess). Maybe I should try that one.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-30T09:47:39+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

You can get "shin_megami_tensei.bms" script and it will extract sound files for you. After that, vgmstream will work properly with all ADB & SMG files, I just tried that and it works.

EDIT some files are stereo, like 15MB "stuff" you tried. These have interleave of 0x100
## Post #12
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-01-30T14:24:15+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

Got it. The .adb I converted is garbled though, but I doubt if it can support these files...
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-30T15:38:06+00:00
- Post Title: Shin Megami Tensei III Nocturne Sound Files(.ADB, .SMG)

All files can be converted perfectly
