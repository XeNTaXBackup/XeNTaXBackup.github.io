## Post #1
- Username: AhrimanSefid
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 07, 2011 4:55 pm
- Post datetime: 2011-03-07T08:57:29+00:00
- Post Title: The Incredible Hulk

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AhrimanSefid
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 07, 2011 4:55 pm
- Post datetime: 2011-03-10T12:16:21+00:00
- Post Title: The Incredible Hulk

Hi.
Not Help Me..................
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-10T14:43:47+00:00
- Post Title: The Incredible Hulk

you can extract the ARC archives using the following script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get OFFSET long
goto offset
get FILES long
for i = 0 < FILES
    get DUMMY long
    get OFFSET long
    get SIZE long
    get NAME string
    get TIME longlong
    log NAME OFFSET SIZE
next i
```
instead the USM file looks like a CRI archive enough similar to the CPK ones but not enough for using the cpk.bms script
## Post #4
- Username: AhrimanSefid
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 07, 2011 4:55 pm
- Post datetime: 2011-03-11T08:12:34+00:00
- Post Title: The Incredible Hulk

Hi.
Thanks Plz Help For Step Be Step.
Thank you for this but how do I use?

Not Sound Export.
Shoe In text Editor

```
		<name>big_whoosh</name>
		<guid>{d70ac874-b0b7-4ee0-9141-4e39fd253f61}</guid>
		<type>randomnorepeat</type>
		<spawntime_min>0</spawntime_min>
		<spawntime_max>0</spawntime_max>
		<spawn_max>1</spawn_max>
		<mode>0</mode>
		<pitch>-0.12</pitch>
		<pitch_randmethod>1</pitch_randmethod>
		<pitch_random_min>0</pitch_random_min>
		<pitch_random_max>0</pitch_random_max>
		<pitch_randomization>0.22</pitch_randomization>
		<volume_db>0</volume_db>
		<volume_randmethod>1</volume_randmethod>
		<volume_random_min>0</volume_random_min>
		<volume_random_max>0</volume_random_max>
		<volume_randomization>0</volume_randomization>
		<position_randomization>0</position_randomization>
		<notes></notes>
		<waveform>
			<filename>../../../raw/audio/whoosh_big_1.wav</filename>
			<soundbankname>samples</soundbankname>
			<weight>100</weight>
		</waveform>
		<waveform>
			<filename>../../../raw/audio/whoosh_big_2.wav</filename>
			<soundbankname>samples</soundbankname>
			<weight>100</weight>
		</waveform>
		<waveform>
			<filename>../../../raw/audio/whoosh_big_4.wav</filename>
			<soundbankname>samples</soundbankname>
			<weight>100</weight>
		</waveform>
	</sounddef>
```
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-11T15:11:33+00:00
- Post Title: The Incredible Hulk

eh?
that one is a script for quickbms.
download the program, save that text as script.bms and launch quickbms.exe

if you have doubts read the documentation:
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-15T11:06:18+00:00
- Post Title: The Incredible Hulk

as usual people must waste their time because who makes the request doesn't provide full details... blah

USM are videos ("CRID" signature) so there is nothing to unpack/repack.
for more details:
[viewtopic.php?f=17&t=4956](http://forum.xentax.com/viewtopic.php?f=17&t=4956)

I casually noticed this just now when I was looking to the files extracted from mpdemo/nigel of crysis2
