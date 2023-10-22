## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-09-14T13:05:09+00:00
- Post Title: PC Darkness II (2012) maxscript

Hi guys! Here's maxscript to import PC Darkness models with bones (3ds max 2009-2012)

1. Load Darkness_II_Bones.ms
2. Point it to a H.misc.cache file like Angelus_skel.fbx
3. A new dialogue shows up, this time choose Angelus_skel.fbx in B.misc.cache
Bones will be loaded

4. Load Darkness_II.ms
5. Point it to H.misc.cache file Angelus_skel.fbx
6. A new dialogue shows up, this time choose Angelus_skel.fbx in B.misc.cache
Model will be loaded above bones

Done


[Darkness_II.7z](https://xentaxbackup.github.io/file/7810_Darkness_II.7z)
## Post #2
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-09-16T19:54:37+00:00
- Post Title: PC Darkness II (2012) maxscript

Thank you so much!
## Post #3
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2014-09-17T09:48:13+00:00
- Post Title: PC Darkness II (2012) maxscript

Great work, thank you!
## Post #4
- Username: Gopher86
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 24, 2015 9:45 pm
- Post datetime: 2016-12-30T23:50:48+00:00
- Post Title: PC Darkness II (2012) maxscript

Hello there!
First of all: thanks for the script. Works perfectly.   

I know it's quite late to ask for some further help, but I would want to extract some models without any bones (environments, props etc.).

Everytime I want to use the script on something different than characters, it doesn't work. I get the error message (MaxScript FileIn Exception): "--Unable to convert: undefinied to type: Integer".
It guides me to the following code:

```
(
	local str = ""
	for i = 1 to fixedLen do
	(
		str += bit.intAsChar (ReadByte bstream #unsigned)
	)
	str
)	
```


Since I'm a newbie I don't know what to change, if changing anything would help anyways..

Thanks for your help in advance!
