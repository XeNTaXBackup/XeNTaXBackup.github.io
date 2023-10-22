## Post #1
- Username: BigForte
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 24, 2016 11:49 am
- Post datetime: 2016-12-24T03:57:33+00:00
- Post Title: Assistance with extracting Battlefield 1 War Stories Audio

Hello Everyone,

I found your forums along with symthic while trying to find a method of extracting audio from the BF1 game files.

After some research, I got all the parts together to do some extractiong but I'm running into an error.

I sent Elementofprogress a PM on Symthic's forums, but I figured I'd try here as well to get more eyes.

I'm attempting to extract the single player audio files (mainly the soundbites from the NPCs) from Battlefield 1. 

I found the initial post here: [http://forum.symthic.com/battlefield-4- ... lefield-4/](http://forum.symthic.com/battlefield-4-general-discussion/6558-extracting-audio-files-from-battlefield-4/)

However that explains BF4 and the instructions didn't quite match what BF1 shows.

Then I found this: [http://forum.symthic.com/battlefield-1- ... r-scripts/](http://forum.symthic.com/battlefield-1-general-discussion/10741-bf1-flie-dumper-scripts/)

This person ran a updated Star Wars Battlefront script and was getting an error. Someone replied stating to use Python 2.7.3 32 bit...however I'm getting the same error OP was getting in that post, posted below...

Traceback (most recent call last):
File "D:\Tools\FrostBite\BattleField 1\bf1_dump\SWBFdumper.py", line 616, in <module>
if "tocRoot" in locals(): dumpRoot(tocRoot)
File "D:\Tools\FrostBite\BattleField 1\bf1_dump\SWBFdumper.py", line 354, in dumpRoot
dump(fname,targetDirectory)
File "D:\Tools\FrostBite\BattleField 1\bf1_dump\SWBFdumper.py", line 268, in dump
if len(glob.glob(basePath+"*"+resTypes[entry.resType])) == 0:
KeyError: 947691693

I was able to dump the chunk data and I was able to even extract a lot of audio from the EBX files, but they are all ambient/SFX audio, no dialogue.

Any help would be appreciated!
## Post #2
- Username: numberisthebest
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 08, 2017 3:25 am
- Post datetime: 2017-04-07T19:29:04+00:00
- Post Title: Assistance with extracting Battlefield 1 War Stories Audio

Hey for your problem I found another extractor that can extract whole Battlefield 1 and I have right now 49.85gigs of raw EXB and chunck data that I need to convert.
The link of this guy is [https://www.youtube.com/watch?v=mU5tuuwVKaY](https://www.youtube.com/watch?v=mU5tuuwVKaY)
and one thing how did you convert the EBX files into mp3/audio files ? I got a bunch of them as mentioned earlier but I do not know how to do that I've been trying for days.
