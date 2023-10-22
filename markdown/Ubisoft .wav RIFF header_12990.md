## Post #1
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-06-24T20:20:32+00:00
- Post Title: Ubisoft .wav RIFF header

Ubisoft's audio wav format wont be read in vgmstream or anything else. The header is RAKI....X360xma2. I've tried to use vgm stream but it wont read it. Can anyone help? I've put a download to the file.

[https://www.mediafire.com/?xbpv26o83973tpj](https://www.mediafire.com/?xbpv26o83973tpj) (Ends in .rak extension)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-06-25T18:25:13+00:00
- Post Title: Ubisoft .wav RIFF header

[Download this zip file](http://www65.zippyshare.com/v/JsUoaB8N/file.html)

It contains the tools necessary to decode the file. Special thanks goes out to Aluigi, Alpha23, HCS and Xplorer.

1. Copy all the .RAK files you have to the QuickBMS folder
2. Run QuickBMS
3. Select the XMA Transform BMS Script first
4. Choose the .RAK files you wish to convert
5. Select where you want the transformed files to be placed
6. When prompted, press Y for XMA Parse to do its thing.

Then after you have the .XMA file/s, use Xplorer's ToWAV tool to convert the XMA into PCM WAV.

Enjoy
## Post #3
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-06-25T19:44:35+00:00
- Post Title: Ubisoft .wav RIFF header

Theres also another type if Ubi RIFF header [http://www.mediafire.com/listen/d3n99mu ... 802332.wav](http://www.mediafire.com/listen/d3n99muzz43hzad/90802332.wav) (Example)

RIFFþí….WAVEfmt this is the header it begins with. It isnt normally read and some wont open.
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-06-26T01:16:23+00:00
- Post Title: Ubisoft .wav RIFF header

What is the game and platform are these files from?
## Post #5
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-06-26T01:46:31+00:00
- Post Title: Ubisoft .wav RIFF header

These are from the Just Dance 2,3, and 4 games on the Wii version. They are extracted from the .wav.bf archive
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-06-26T02:10:04+00:00
- Post Title: Ubisoft .wav RIFF header

Rename from .wav to .sns and vgmstream will play/convert them just fine
## Post #7
- Username: vladik4kides
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 18, 2015 12:36 am
- Post datetime: 2015-06-26T10:40:21+00:00
- Post Title: Ubisoft .wav RIFF header

Just download vgmstream plugin for Winamp and enable export plugin. Then rename .wav files to the .sns and open it with Winamp. It will convert it to the mp3. Enjoy!
## Post #8
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-07-16T16:45:16+00:00
- Post Title: Ubisoft .wav RIFF header

Hi i have another version of the wav mentioned before. This time its the xbox version. I cant convert with XMA and it cant be read by vgm stream. Do you know anything?

Heres an example: [http://www.mediafire.com/listen/ii80w9c ... e0201a.wav](http://www.mediafire.com/listen/ii80w9cuwasot8r/08e0201a.wav)
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-16T18:13:59+00:00
- Post Title: Ubisoft .wav RIFF header

Okay for this file, you need to note down the channels and frequency rate of the file, then scan for the XMA flag manually and delete everything that is 6 bytes before that flag.

The frequency is most likely going to be 44100Hz or 48000Hz. These numbers can be found in the RIFF header, look for the frequency rate first and then a couple of bytes back will show the channels.

The most common frequency numbers are 80BB (48000Hz) and 44AC (44100Hz)

Once you have this information you need to scan for the XMA flag.

The XMA flag is "FC01C001"

Delete everything starting 6 bytes before the XMA flag.

It should look something like this:



Once this is done, open up the XMA Transform BMS Script from AlphaTwentyThree and make sure that the set FREQ_DEFAULT and set CH_DEFAULT are the same as the sample rate and channel you notated down before then save the script.

Run the script, it will give you an XMA file with a proper header and then use ToWAV to convert.
## Post #10
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-07-16T19:26:13+00:00
- Post Title: Ubisoft .wav RIFF header

Im having problems with the bms script. Whenever i type "y" and press enter, it outputs "wrong command-line argument" and i cant seem to fix it.
## Post #11
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-17T09:06:49+00:00
- Post Title: Ubisoft .wav RIFF header

Did you rename the exe from xma_test to xma_parse?
## Post #12
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-07-17T15:50:36+00:00
- Post Title: Ubisoft .wav RIFF header

It was already named that when i extracted the zip file
## Post #13
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-17T17:14:43+00:00
- Post Title: Ubisoft .wav RIFF header

What files are you attempting to run the script on? Post some samples.
## Post #14
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-07-17T21:53:44+00:00
- Post Title: Ubisoft .wav RIFF header

Its anything convertable. So the .wav, .rak files that i have been attempting at
## Post #15
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-17T22:35:49+00:00
- Post Title: Ubisoft .wav RIFF header

Upload all the XMAs and I'll fix them up for you and send them back so you convert them. It's probably quicker at this point
## Post #16
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-07-17T23:09:00+00:00
- Post Title: Re: Ubisoft .wav RIFF header

Ok i fixed it. I delted everything and redownloaded. Thanks for the help anyways.
## Post #17
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-18T00:34:58+00:00
- Post Title: Re: Ubisoft .wav RIFF header

Excellent, glad it worked out
## Post #18
- Username: vladik4kides
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 18, 2015 12:36 am
- Post datetime: 2015-10-03T15:14:33+00:00
- Post Title: Re: Ubisoft .wav RIFF header

> Reply from brendan19
>
> Excellent, glad it worked out

Now help me XD
So I have some .wav files from Just Dance 2 (Wii)
It has weird header and I can't get them to work with vgmstream.



Снимок.PNG (1.82 KiB) Viewed 99 times


[Here's](https://mega.nz/#!Dd9BwQja!I9lqczn57mZiqQCwJmalOZTzB65F0cP9h34AnJoea2E) some samples
## Post #19
- Username: Dilan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 04, 2022 3:22 am
- Post datetime: 2022-11-03T19:26:12+00:00
- Post Title: Re: Ubisoft .wav RIFF header

Is there any way to do the opposite, i.e. from wav to wav (xma & ubiraki)?
