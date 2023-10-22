## Post #1
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2016-02-13T09:15:52+00:00
- Post Title: Half-Life 2 .sav file

Hi,
I have been struggling with this for quite a while. I figured out the .dem format for HL2 but I can't seem to get anywhere with this.
If anyone would help it would be greatly appriciated.
So far I know:

```

byte {X}     - File Data 

// Directory 
// for each file 
while (variableID != 12) { 
uint16 {2}   - Variable ID 
if (variableID == 1){ 
byte {3}     - Unknown 
} 

if (variableID == 2){ 
uint32 {4}   - Unknown 
} 

if (variableID == 12){ 
uint32 {4}   - Unknown (3375) 
} 
} 

uint32 {4}   - Unknown (16256) 
byte {6}     - null 
uint16 {2}   - Unknown (4) 
uint16 {2}   - Unknown (72) 
uint16 {2}   - Unknown (3) 
uint16 {2}   - null 
uint16 {2}   - Unknown (12) 
byte {X}     - Unknown 
byte {1}     - null Unknown Field Terminator 
uint16 {2}   - Unknown (3866) 
char {128}   - filename (null)
```

Sav files: [https://drive.google.com/folderview?id= ... sp=sharing](https://drive.google.com/folderview?id=0B3mjSUI16K7cX0RQc3dSVk80STg&usp=sharing)
Thanks in advance.
## Post #2
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2016-03-10T16:29:15+00:00
- Post Title: Half-Life 2 .sav file

A little progress report:
## Post #3
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2016-09-30T11:18:14+00:00
- Post Title: Half-Life 2 .sav file

If anyone is willing to help me with reversing the file completely I am willing to pay them because I desperately need this to be reversed for my university project. I started reversing it by looking at the sdk but I couldn't get anything other than the header of the file which I posted earlier. Sadly the wiki page([http://wiki.xentax.com/index.php/Half_Life_2_SAV](http://wiki.xentax.com/index.php/Half_Life_2_SAV)) doesn't contain everything so its not a huge help. Thanks to anyone who took the time to read my post.
Regards,
  Ben
## Post #4
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2017-01-14T18:58:20+00:00
- Post Title: Half-Life 2 .sav file

Now parsing the basic file archive is done I can export the .hl? files:
## Post #5
- Username: Udogol2017
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 22, 2017 4:50 pm
- Post datetime: 2017-10-09T07:46:50+00:00
- Post Title: Half-Life 2 .sav file

Thanks, nice help.
