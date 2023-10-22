## Post #1
- Username: Sureno12
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 30, 2015 4:07 am
- Post datetime: 2017-04-11T07:12:34+00:00
- Post Title: What to look for?

Hi, please move this thread if I'm in the wrong section.
I need help in debugging the .dll in ollydbg.
What I am trying to do is to change ID for PCMesh so that I can add more 3d model/mesh/ID to be use in the future.
The default ID for the PCMesh, 

Start ID is 10301 = 283D
End ID is 10999 = 2AF7









If I will just try to expand 10999 to 11999/12999 etc it cannot be done because on 11,000-300,000+ is use by NPC Dialogue and others.
So to be safe I want to change it to start ID in 400,000 and end ID in 405,000.
I edited two location of PCMesh offset 10025348 and 10045C90.








After that when I test it, this one appears.








I look at the crash report but I cannot understand what to change.




It seems I have to edit something inside HT3DHeaven.dll. 
I tried looking the offset in HT3DHeaven.dll from the crash report but I dont have any clue or idea what to do next.
Please help, thank you.

```
https://mega.nz/#!3pMUUTRZ!Ykf5V3XUF9t6B_fpaYCfmIDR2UC8Ei6U4PTNJCqhMEY
```
## Post #2
- Username: Sureno12
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 30, 2015 4:07 am
- Post datetime: 2017-04-12T01:20:34+00:00
- Post Title: What to look for?

Bump, please help.
