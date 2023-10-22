## Post #1
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2010-07-17T16:29:02+00:00
- Post Title: Colin McRae DiRT 2 .lng file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-07-27T10:17:01+00:00
- Post Title: Colin McRae DiRT 2 .lng file

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2010-07-27T13:07:51+00:00
- Post Title: Colin McRae DiRT 2 .lng file

what?
## Post #4
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-07-27T14:33:11+00:00
- Post Title: Colin McRae DiRT 2 .lng file

> Reply from Jurko
>
> what?
+1 means once more interested in the same question u posted here.

So +1 from me too, i won't reject if the help will occure
## Post #5
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2010-07-29T12:33:58+00:00
- Post Title: Colin McRae DiRT 2 .lng file

I have a tool to edit this file. A translation tool. I'll search it in home, and if I find, I'll post it here.
## Post #6
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-08-01T11:06:48+00:00
- Post Title: Colin McRae DiRT 2 .lng file

Herdell please ...
## Post #7
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2010-08-02T08:35:23+00:00
- Post Title: Colin McRae DiRT 2 .lng file

Herdell please post him
## Post #8
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2010-08-04T18:03:51+00:00
- Post Title: Colin McRae DiRT 2 .lng file

Admin edit: tool was shared without permission. Removed by request. Don't do it again.

This is the DiRT 2 .lng editor.

See the "how to use inside the .rar to guide you.

Enjoy
## Post #9
- Username: jenner
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 21, 2010 5:10 am
- Post datetime: 2010-08-21T13:39:58+00:00
- Post Title: Colin McRae DiRT 2 .lng file

Well, although the user is sharing my tool without permission, it is a great opportunity to show our work on game translation. Here is the english version of my tool, feel free to use it (works with Dirt2 too).
[Race Driver GRID.zip](https://xentaxbackup.github.io/file/3361_Race Driver GRID.zip)
## Post #10
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2010-11-15T03:17:17+00:00
- Post Title: Colin McRae DiRT 2 .lng file

AVG is reporting this as a Generic Trojan... i tried to ignore but Windows won't let me open the file.
Considering you have screenshots of the program with a GUI, 29kb is far too small for a program like this.

[](http://i228.photobucket.com/albums/ee249/xer2k7/rdgte_troj.jpg)

File name: 
Race_Driver_GRID_Text_Editor.rar
    Submission date: 
2010-11-15 03:06:16 (UTC)
              Result: 
2/                                  43 (4.7%)

[Results from VirusTotal.com](http://www.virustotal.com/file-scan/report.html?id=124b58837bbd9eb7dec30865fccc23e7684a20f0394039a63e98a86698ca518f-1289790376)

I think AVG is giving me a huge false positive (which is what i am sure of)... but i don't know of any other secure, quiet & reliable Anti Virus software.. i used to have NOD32 but that used to bug the hell outta me... so i'm not sure what to do... I'm trying to find out if the language files contain the names of the event ID's and track ID's from the database.bin file.

I've searched everywhere and there is no explanation online about what these things mean;

```
      <base_result_list type="string" size="64">
      </base_result_list>
      <blank type="int">0</blank>
      <event_id type="int">1</event_id>
      <id type="int">148</id>
```


I am just trying to find out if by reading the language files these will make any more sense without having to trial and error everything...
If no1 can help me with what they mean, can someone please post a decrypted language file? even in .txt format i dont really mind, i don't want to edit strings i just need to find out what the IDs actually mean & which is which...

Thanks in advance, Jenx 

EDIT: I know the file i have posted a screenshot of above is a different archive format, i.e it was in a RAR not a zip, and the exe name is different, but i also downloaded Jenner's zip version just now, i get the same Generic17.ARJI warning.  

EDIT2: Ok so i reluctantly uninstalled AVG so i could use this tool, unfortunately in the language_use/eng files there are no IDs... and i thought maybe the ID is also the line number but that isn't correct either... not sure where i can find these IDs because there are a couple of mods out there (like the AnyCarAnyTrack mod) which the developers seem to have a grasp on what these IDs actually are... 

Ok scratch that i think i'm starting to see where these IDs are... very hard to spot imo.. i'm using notepad++ and have got all the parameters collapsed which makes it slightly easier to read...

(by the way, i am trying to edit the Racedriver: GRID database.bin but from what i've read, all EGO engine racing games have a similar structure even the new F1 2010 which is EGO 2.0)

For all of you who are having the same trouble, this might help;

1. Open the decrypted database.xml in Notepad++
2. Go View > Fold All
3. Click the + Sign left of the word "<database>"
Now you should have something that looks like this;


Also as a hint, this file also tells you how many items are in each set of parameters;

Where i have circled in green, that is the number of sub sets of parameters inside the parent parameter

This is where i think i have found the IDs for vehicles so far;



etc...

So as you can see in the top 2 images, displaying the Vehicle IDs and their internal names within the parameters, the first image shows the Plymouth AAR Cuda (codename: ply), and the second image shows the Saleen S7R (codename: sal).

Which i worked out because i found this list of internal car names & their real world names (Thanks to Teddy for this list)

```
390 - Nissan R390 GT-1
787 - Mazda 787B
911 - Porsche 911 GT3 RSR
b05 - Lola B05-40
b06 - Lola B06-10
bmw - BMW 320SI
bos - Ford Mustang Boss 302
c5r - Chevrolet Corvette C5-R
c6r - Chevrolet Corvette C6-R
c65 - Courage C65
cam - Chevrolet Camaro Concept
ccg - Koenigsegg CCGT
ccx - Koenigsegg CCXR
cha - Dodge Challenger Concept
cor - Toyota Corolla GT-S
cre - Creation CA06/H-JUDD
dbr - Aston Martin DBR9
df3 - Dallara Formula 3
esp - Panoz Esperante
fmj - JRC FJ1000
gto - Pontiac GTO
gtr - Ford Mustang GT-R Concept
imp - Subaru Impreza
je4 - Ford Doran JE4
lac - Chevrolet Lacetti
lam - Lamborghini Murcielago RGT
lc7 - Courage LC70
mop - Dodge Charger SRT-8 Drift
nsx - Honda NSX-R
ply - Plymouth AAR Cuda
r10 - Audi R10 TDI
rx7 - Mazda RX-7 FD3S
s15 - Nissan Silvia
sal - Saleen S7R
sky - Nissan Skyline GT-R Z-Tune
soa - Toyota Soarer
spk - Spyker C8 Spyder
stk - Jupiter Eagleray MK5
sup - Toyota Supra
tch - TVR Tuscan Challenge
vip - Dodge Viper SRT-10
zon - Pagani Zonda R
```


If i discover any more useful tips while trying to mod this, i will make sure to post them here 

-J
## Post #11
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2011-12-03T18:11:10+00:00
- Post Title: Colin McRae DiRT 2 .lng file

For Jenner's tool, Symantec alerts "Downloader"!
