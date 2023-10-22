## Post #1
- Username: jacksonlowry
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 26, 2022 4:14 am
- Post datetime: 2022-03-25T21:12:11+00:00
- Post Title: MVP 07: NCAA Baseball (PS2) - .ssh files

Hello, I have been interested in modding the EA game MVP NCAA Baseball 07 for the PS2. The game's uniform and other texture files are in the .ssh format. 
I have already tried the tools found here: [https://wiki.xentax.com/index.php/EA_SSH_FSH_Image](https://wiki.xentax.com/index.php/EA_SSH_FSH_Image) and none of them worked.
I also tried the noesis plugin found in this thread [viewtopic.php?p=177561#p177561](https://forum.xentax.com/viewtopic.php?p=177561#p177561) but trying to open one of the files gives the error "Tried to set offset beyond buffer size. 852096>52000". 
If anyone knows of a tool or could point me in the right direction to solve the noesis error it would be greatly appreciated.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-25T21:39:00+00:00
- Post Title: MVP 07: NCAA Baseball (PS2) - .ssh files

Can you upload a few samples?
## Post #3
- Username: jacksonlowry
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 26, 2022 4:14 am
- Post datetime: 2022-03-25T22:53:05+00:00
- Post Title: MVP 07: NCAA Baseball (PS2) - .ssh files

Here are some examples of what's in the uniform folder attached. All the uniform files are in this format, there's an xxx.ssh, xxxa.ssh, and xxxb.ssh. It does this from 001 to 255. I was able to use the "Console Texture Explorer" tool to open the 1st file and using the offset listed for the file in BigGUI (0x00027F44), it gave a garbled image of rainbow pixels but that is as far as I've gotten. No matter the settings, the a and b files will not give any image in the program.
[mvp07ssh.zip](https://xentaxbackup.github.io/file/22017_mvp07ssh.zip)
