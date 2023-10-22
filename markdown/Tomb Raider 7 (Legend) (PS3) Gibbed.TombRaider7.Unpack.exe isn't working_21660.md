## Post #1
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-01-23T19:34:02+00:00
- Post Title: Tomb Raider 7 (Legend) (PS3): Gibbed.TombRaider7.Unpack.exe isn't working

Hi guys, I experience problems trying to unpack a BIGFILE.000 archive from TR7 for PS3 (a part of Tomb Raider Trilogy release).

I got [this version](http://svn.gib.me/builds/crystaldynamics/tombraider7a8d/tombraider7a8d-r122_b80.zip) of Rick’s tool (the newest build I presume), set project value to "Tomb Raider 7 (PS3)" but "Gibbed.TombRaider7.Unpack.exe" crashed with this error (


t.jpg (23.04 KiB) Viewed 74 times

).
Then I tried [a somewhat similar program](http://svn.gib.me/builds/crystaldynamics/deusex3/deusex3-r122_b80.zip) (the latest ver. too), moved both "Tomb Raider 7 (PS3)" folder & "Tomb Raider 7 (PS3).xml" file to "projects" folder inside "bin_dx3" folder, once again I set project value to "Tomb Raider 7 (PS3)" but "Gibbed.DeusEx3.Unpack.exe" had a crash very early on too; it gave me much more detailed info about possible reasons though ([attachment #2](https://mega.nz/#!sB8wBSJK!6eGGk1aMYWLd3Z34aZlsORQj8kEydM6ZHZING23trS8)).

Is anyone else experiencing the same problems? When I set out to try & rip some BGMs from TR7 I never thought that any trouble could wait for me on the 1st stage of the whole process...
Goodbye & thanks in advance for any feedback!

PS. I'm attempting to rip BLES01195 release if it helps; can this problem be release-specific (for example I had to choose US release to make "Gibbed.TombRaider7.Unpack.exe" or "Gibbed.DeusEx3.Unpack.exe" work)? It doesn't seem too likely to me after all...
## Post #2
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-03-11T14:05:57+00:00
- Post Title: Tomb Raider 7 (Legend) (PS3): Gibbed.TombRaider7.Unpack.exe isn't working

I've just checked US release & got the same error... in case anyone's interested.
Bye!
Edit: the version I tried to rip was BLUS30718 this time.
## Post #3
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-03-12T09:33:34+00:00
- Post Title: Tomb Raider 7 (Legend) (PS3): Gibbed.TombRaider7.Unpack.exe isn't working

Read the instructions

PS3 is big endian so you must pass flag -b on commandline.
## Post #4
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-03-14T15:33:33+00:00
- Post Title: Tomb Raider 7 (Legend) (PS3): Gibbed.TombRaider7.Unpack.exe isn't working

Like this?


TR7.png (22.58 KiB) Viewed 55 times


It doesn't look like this *.exe understands such a flag...

Later!
## Post #5
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2020-03-24T10:30:09+00:00
- Post Title: Tomb Raider 7 (Legend) (PS3): Gibbed.TombRaider7.Unpack.exe isn't working

If anyone's interested then here's the current status of all this: I searched for another build and found something, it had that --big-endian option so that it managed to extract data. Playing back sounds isn't possible though, it might be some new variation of *.mul AKA *.EMFF format and we'll have to wait & see if it can be implemented in VGMstream plugin.

So long!
