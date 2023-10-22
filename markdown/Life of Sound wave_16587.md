## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-07-24T09:42:44+00:00
- Post Title: Life of Sound wave

I had this on my mind for a long time, but never got right words to put into search bar, too redundant.
When I play any sound file from my player, I get that data from sound file must be decoded to raw data and send to sound card to be converted to audio signal, but what formats sound card actually receives? 
I know that GPUs can process RGBA8, DXT or PowerVR formats as they are, beouse you know GPUs are fine in case of paralell computing, but what about sound cards? Does the player just send data in float, and drivers just take care of rest? Or can drivers receive PCM data as well?
This is big unknown for me. What is going on between player output and sound card?
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-07-24T10:27:11+00:00
- Post Title: Life of Sound wave


## Post #3
- Username: Dvaser
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 30, 2019 7:25 pm
- Post datetime: 2019-01-30T11:28:35+00:00
- Post Title: Life of Sound wave

But what formats sound card actually receives?
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-03-12T17:26:13+00:00
- Post Title: Life of Sound wave

Now since there was a reply recently, I did spend some time digging thru oceans of code for drivers/APIs/datasheets(kinda).
So here is the story of a "Life of Sound wave"

A sound track is stored in MuLAW format, it is stored on Windows OS, when suddenly someone or something wants to play it.
A program will pull out its data, and passes them into Kernel API in same or other way.
Now let's say that API is called WinMM, this API supports many formats, but must comply with driver.
The driver can read only a few formats, it can read MuLAW, so API doesn't need to convert data and just passes them to the driver.
Now driver must comply to the chip itself.

Each sound chip has their own input specifications, for example:
PCM270x: supports only 16bit PCM signals,
ALC8xx: supports 16/24/32bit PCM signals.

So the only thing that driver must do, is convert data from MuLAW into PCM whinch sound card can understand.

We can imagine Chip, Driver, Kernel API as black boxes, where each one must output data, that the other one can understand.

Now what if, the sound track was stored in MP3 format?
WinMM can read MP3 data, but driver may not (again depends on the driver).
So in this case, WinMM must convert data into PCM format, so driver can just pass them into sound card.

And as you may guess, when sound track is stored in PCM format, the data are just passed straight to the sound card.

Now this example is fairly simple, it doesn't contain any special mumbo-jumbo like mixers, DSP effects, etc.

The programmer himself will always work with Kernel API, or any abstraction layer of it.
Abstraction layers may limit input formats even further, but can also add custom format support.
