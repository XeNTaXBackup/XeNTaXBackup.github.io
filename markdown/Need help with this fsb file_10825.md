## Post #1
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-10-01T00:34:45+00:00
- Post Title: Need help with this fsb file?

I want to extract the audio from this fsb file from a video game but I don't know how. I tried using fsbext but it doesn't work properly on ogg files as the files extracted are unplayable. Are there any other methods to extract the audio files and have them playable?

The file:
[http://www.mediafire.com/download/dwg6h ... stream.fsb](http://www.mediafire.com/download/dwg6h3jktd7zio7/VO_stream.fsb)

I would REALLY appreciate help, thank you!
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-10-01T01:51:48+00:00
- Post Title: Need help with this fsb file?

you can listen to the samples in fmod designer/event player if you find the fev file it comes with. thats the only way to listen to the ogg ones I know of.
## Post #3
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-10-01T03:02:54+00:00
- Post Title: Need help with this fsb file?

Your FSB file is an FSB5 with an important hex value of 00 00 16. In order for any FSB5 to decode properly it must be 50 00 00 16 which this sample file is. Therefore you'll need [this](http://www.mediafire.com/?ti0qoqqzk43qvdd) tool to properly convert.

I noticed though that this sample has multiple fsb5 hex values which means you'll have to split each fsb5 header and run it through this tool. 

Give a big shout out to jseidelin he is the guy who figured this all out. 

Addendum: sometimes fsb5 files have different values that you'll need to edit, for example instead of being 50 00 00 16 a fsb5 header may actually have a value of 21 00 00 16 in that case you'll have to edit it and make it 50 00 00 16 at the beginning of each file you'll always find the first instance of 00 00 16 at 040 the value you may need to edit is at 044. 

Hope this helps.
## Post #4
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-10-01T03:37:09+00:00
- Post Title: Need help with this fsb file?

> Reply from durandal217
>
> Your FSB file is an FSB5 with an important hex value of 00 00 16. In order for any FSB5 to decode properly it must be 50 00 00 16 which this sample file is. Therefore you'll need this tool to properly convert.

I noticed though that this sample has multiple fsb5 hex values which means you'll have to split each fsb5 header and run it through this tool. 

Give a big shout out to jseidelin he is the guy who figured this all out. 

Addendum: sometimes fsb5 files have different values that you'll need to edit, for example instead of being 50 00 00 16 a fsb5 header may actually have a value of 21 00 00 16 in that case you'll have to edit it and make it 50 00 00 16 at the beginning of each file you'll always find the first instance of 00 00 16 at 040 the value you may need to edit is at 044. 

Hope this helps.

Really appreciate this  I'll give it a shot.
## Post #5
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-10-01T22:14:47+00:00
- Post Title: Need help with this fsb file?

> Reply from durandal217
>
> Your FSB file is an FSB5 with an important hex value of 00 00 16. In order for any FSB5 to decode properly it must be 50 00 00 16 which this sample file is. Therefore you'll need this tool to properly convert.

I noticed though that this sample has multiple fsb5 hex values which means you'll have to split each fsb5 header and run it through this tool. 

Give a big shout out to jseidelin he is the guy who figured this all out. 

Addendum: sometimes fsb5 files have different values that you'll need to edit, for example instead of being 50 00 00 16 a fsb5 header may actually have a value of 21 00 00 16 in that case you'll have to edit it and make it 50 00 00 16 at the beginning of each file you'll always find the first instance of 00 00 16 at 040 the value you may need to edit is at 044. 

Hope this helps.

When I try running the ps2fsb.exe it says the program can't start because MSVCP110.dll from my computer. I don't know much about fsb files. If it's not to much to ask can I you extract the files for me and I can pay you for your time?
## Post #6
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-10-01T23:08:49+00:00
- Post Title: Need help with this fsb file?

Three things; One you don't double click the ps2fsb.exe because it's not a typical program, it is something that runs by simply dragging and dropping the file in question (in this case VO_Stream.fsb onto ps2fsb.exe, which you'd than see a black pop up box (don't worry this is just command prompt a command line program to every windows operating system since Bill Gates was born) and it will then convert the file. 

Two; as much as I'd love money, considering I'm unemployed and struggling to find a job, I won't and can't take any money you'd offer to pay me to extract. Why? Well, First because I consider it a sin to take money from someone to do something that is the equivalent of plugging in a toaster, placing a piece of bread in the toaster and pushing the handle down. It is not hard, I'm no expert in fact I'm a fucking noob at almost all of this. I had to do it all myself, because sometimes help is difficult to come by here. So If I can do it, so can you. Also I couldn't take money from you anyway because it is against the rules of this community to exchange money for services.

Three; If by some chance you did take your fsb file and dragged and dropped in onto ps2fsb.exe and still got this MSVCP110.dll is not on this machine, do a google search for the dll and look for instructions on how to add it to your windows operating system. [Here Is a safe link that will help you.](http://www.dll-files.com/dllindex/dll-files.shtml?msvcp110)

I hope you understand, I'm not trying to be an ass or be mean but dude, this isn't hard to figure out. You just need patience. And the ability to learn.

PS. What I am willing to do is post a step by step process on how to extract what you are looking for if you are totally new to this. However I can't diagnosis any problems your computer is having, so if something is wrong with your computer that is on you, and for you to figure out.
## Post #7
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-10-01T23:19:51+00:00
- Post Title: Need help with this fsb file?

> Reply from durandal217
>
> Three things; One you don't double click the ps2fsb.exe because it's not a typical program, it is something that runs by simply dragging and dropping the file in question (in this case VO_Stream.fsb onto ps2fsb.exe, which you'd than see a black pop up box (don't worry this is just command prompt a command line program to every windows operating system since Bill Gates was born) and it will then convert the file. 

Two; as much as I'd love money, considering I'm unemployed and struggling to find a job, I won't and can't take any money you'd offer to pay me to extract. Why? Well, First because I consider it a sin to take money from someone to do something that is the equivalent of plugging in a toaster placing a piece of bread in the toaster and pushing the handle down. It is not hard, I'm no expert, in fact I'm a fucking noob at almost all of this. And I couldn't anyway because it is against the rules of this website to offer services for money. 

Three; If by some chance you did take your fsb file and dragged and dropped in onto ps2fsb.exe and still got this MSVCP110.dll is not on this machine, do a google search for the dll and look for instructions on how to add it to your windows operating system. Here Is a safe link that will help you.

I hope you understand, I'm not trying to be an ass or be mean but dude, this isn't hard to figure out. You just need patience. And the ability to learn.

PS. What I am willing to do is post a step by step process on how to extract what you are looking for if you are totally new to this. However I can't diagnosis any problems your computer is having, so if something is wrong with your computer that is on you, and for you to figure out.

No I understand. I wasn't sure how complicated the process is which is why I offered payment and I appreciate you informing me that this was against website rules. I'll try to get it working and inform you of any issues. Appreciate the help btw.
## Post #8
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-10-01T23:24:35+00:00
- Post Title: Need help with this fsb file?

> Reply from Tartarus
>
> No I understand. I wasn't sure how complicated the process is which is why I offered payment and I appreciate you informing me that this was against website rules. I'll try to get it working and inform you of any issues. Appreciate the help btw.

Not a problem, I'll do what I can to help you with what I know.
## Post #9
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-10-02T01:35:46+00:00
- Post Title: Need help with this fsb file?

> Reply from durandal217
>
> Tartarus wrote:No I understand. I wasn't sure how complicated the process is which is why I offered payment and I appreciate you informing me that this was against website rules. I'll try to get it working and inform you of any issues. Appreciate the help btw.

Not a problem, I'll do what I can to help you with what I know.

Alright so I no longer get the error but when I drag the fsb file onto the .exe the black box pops up but I can't type anything and only one .wav file is made that seems to play depending on the fsb but I know there are supposed to be much more What do I have to do now?
## Post #10
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-10-02T02:50:22+00:00
- Post Title: Need help with this fsb file?

> Reply from Tartarus
>
> Alright so I no longer get the error but when I drag the fsb file onto the .exe the black box pops up but I can't type anything and only one .wav file is made that seems to play depending on the fsb but I know there are supposed to be much more What do I have to do now?

It turns out this is a bit more difficult than I realized. I was in the process of writing out and taking screenshots on how to do this, until I opened up my hex editor and realized the data doesn't split like in a normal archive. So my attempts at splitting the files so you can convert each individual audio file have only been met with unsuccessful garbled mess. 

I should have looked at the file more closely. I'm afraid I've run my limit. Unless someone with more expertise can chime in, the only way I can see you accessing the VO stream is like Pepper said, you'd have to download fmod event player if you find the .fev file it comes with VO_stream.fsb and even than you'd only be able to listen to the audio not save it as a .mp3 or .ogg.

I fucked up, I should have looked over the file more. Please accept my apologies.
## Post #11
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-10-02T03:07:16+00:00
- Post Title: Need help with this fsb file?

> Reply from durandal217
>
> Tartarus wrote:Alright so I no longer get the error but when I drag the fsb file onto the .exe the black box pops up but I can't type anything and only one .wav file is made that seems to play depending on the fsb but I know there are supposed to be much more What do I have to do now?

It turns out this is a bit more difficult than I realized. I was in the process of writing out and taking screenshots on how to do this, until I opened up my hex editor and realized the data doesn't split like in a normal archive. So my attempts at splitting the files so you can convert each individual audio file have only been met with unsuccessful garbled mess. 

I should have looked at the file more closely. I'm afraid I've run my limit. Unless someone with more expertise can chime in, the only way I can see you accessing the VO stream is like Pepper said, you'd have to download fmod event player if you find the .fev file it comes with VO_stream.fsb and even than you'd only be able to listen to the audio not save it as a .mp3 or .ogg.

I fucked up, I should have looked over the file more. Please accept my apologies.

Nah its fine thanks for trying to help anyway :\
## Post #12
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2013-10-18T10:12:36+00:00
- Post Title: Need help with this fsb file?

del
