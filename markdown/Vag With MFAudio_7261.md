## Post #1
- Username: Ander0072
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 29, 2011 2:08 pm
- Post datetime: 2011-08-30T05:03:44+00:00
- Post Title: Vag With MFAudio

I know this question may sound a bit "noobish" but I have over 7000 vag files which I wish to convert to wave, now using MFaudio works like a charm, the problem is it only allows 1 file input at a time;
is there a way to do it in bulk (like, select all the files & just show a destination folder, & just wait? & not have to re click an input every minute.)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-08-30T14:16:24+00:00
- Post Title: Vag With MFAudio

mfaudio can convert files on the command line, so you can write a .bat such as:

```
for %%1 in (*.vag) do start /wait MFAudio "%%1" /OTWAVU "%%1.wav"
```

which is what I used for Max Payne.  You could also just run that directly from the command line with %1 instead of %%1.
## Post #3
- Username: Ander0072
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 29, 2011 2:08 pm
- Post datetime: 2011-08-31T02:15:11+00:00
- Post Title: Vag With MFAudio

Thanks ^_^
worked like a charm & as fast as a bullet~
## Post #4
- Username: SlavaVlasov
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:00 am
- Post datetime: 2018-09-23T22:53:29+00:00
- Post Title: Vag With MFAudio

And how i can set parameters from command line, like mono/stereo, khz etc?
## Post #5
- Username: SlavaVlasov
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:00 am
- Post datetime: 2019-07-24T21:28:20+00:00
- Post Title: Vag With MFAudio

I found commands for MFAudio:

```

/IFnnnnn	Input frequency
/ICn		Input channels
/IIxxxx		Input interleave (hex)
/IHxxxx		Input headerskip (hex)
/OTtttt		Output type (WAVU, VAGC,
		 SS2U, SS2C, RAWU, RAWC)
/OFnnnnn	Output frequency
/OCn		Output channels
/OIxxxx		Output interleave (hex)
"InputFile"	Input file to play/convert
"OutputFile"	Output file to convert to
```


Example:

```
for %%1 in (*.vag) do start /wait MFAudio "%%1" /ITRAWC /IF16000 /IC1 /OF16000 /OC1 /OTWAVU "%%1.wav"
```


The only inconvenience: If "RAW Compressed" is determined by mistake as "RAW Uncompressed" by default, then it is impossible to forcibly switch the input format through the batch file. That is, in the output files you will hear noise.
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-24T23:00:24+00:00
- Post Title: Vag With MFAudio

You could also use the convert to WAV feature in Foobar/vgmstream, not just for VAG, but for many other formats.  I've always found that to work perfectly, with no need to mess about with setting output parameters.
