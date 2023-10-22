## Post #1
- Username: oG Goddess
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 20, 2013 10:52 pm
- Post datetime: 2014-04-21T18:08:02+00:00
- Post Title: GTA V (Project XSC)

A team of us are currently working on Research and development of GTA V xsc files. Our project leader has put together a team to get the ball rolling. I am not a programmer. I have my skill in rpf edits and basic knowledge. Since Rock* has made it clear they are persistent in patching alot of the game files we are going to work on the xsc assembly. 

We do understand this is a very hard project, but with the right people and help it can be accomplished. There is already people who have found how the opcode handles but this is what is being worked on now.
The big picture is to make a compiler/decompiler. 

I'm here branching out for people who are interested in joining the team and would like to take part with us. That is my role on the team for now. We can go very far and others have already done so, we are trying to do the same.

I will be providing notes, reports, etc to people who want to know or just stay updated on our project of the research we have found. This is posted on another website but this is us coming to different places.

Here is some information we found on here and other various websites along with some reports.

I would like to thank the people who have helped us in this project and references that were helpful.


Natives found
[http://gta5hasher.glokon.org/natives/](http://gta5hasher.glokon.org/natives/)

XSC reports

[https://www.mediafire.com/?bg3zvnpk4xtm7ws](https://www.mediafire.com/?bg3zvnpk4xtm7ws)

[https://www.virustotal.com/en/file/8918 ... 398102904/](https://www.virustotal.com/en/file/8918da685d454441d99ab0cc66c36630c6d0a747f6fbe3a71ff5fc33e1822810/analysis/1398102904/)


Link to using xex files in IDA Pro tutorial 

[http://www.xboxchaos.com/topic/1415-how ... o-ida-pro/](http://www.xboxchaos.com/topic/1415-how-to-load-an-xex-into-ida-pro/)

Default.xex

[http://www.mediafire.com/download/e1b50 ... efault.xex](http://www.mediafire.com/download/e1b50lc1hxwj4n9/default.xex)

[https://www.virustotal.com/en/url/3e187 ... 398103257/](https://www.virustotal.com/en/url/3e1875c2c2fb889b5fa418fe9aba0cc28feb330f78fea7d6646a9c34144709db/analysis/1398103257/)

XSC files

[http://www.mediafire.com/download/6ajat ... _files.rar](http://www.mediafire.com/download/6ajatsa0m0fc3pi/.xsc_files.rar)

[https://www.virustotal.com/en/url/7359b ... 398103349/](https://www.virustotal.com/en/url/7359b81cc7f87ec231346cf276605240befcec71c93ace98fd2337858329c4d4/analysis/1398103349/)
## Post #2
- Username: oG Goddess
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 20, 2013 10:52 pm
- Post datetime: 2014-04-21T18:11:07+00:00
- Post Title: GTA V (Project XSC)

Some ppc instruction found today.

text:8221C418 sub_8221C418:                           # CODE XREF: sub_8221F230+98p
.text:8221C418                 mflr      r12
.text:8221C41C                 bl        loc_8362ED2C
.text:8221C420                 stwu      r1, -0x70(r1)
.text:8221C424                 lwz       r31, 8(r3)
.text:8221C428                 mr        r11, r3
.text:8221C42C                 mr        r29, r5
.text:8221C430
.text:8221C430 loc_8221C430:                           # DATA XREF: .rdata:8200BCB4o
.text:8221C430                                         # .rdata:8200CAD4o ...
.text:8221C430                 cmplwi    cr6, r31, 0
.text:8221C434                 beq       cr6, loc_8221C48C
.text:8221C438                 lwz       r10, 4(r3)
.text:8221C43C                 addi      r30, r31, 4
.text:8221C440                 lwz       r9, 0(r31)
.text:8221C444                 addi      r8, r10, 1
.text:8221C448                 mr        r3, r30
.text:8221C44C                 stw       r8, 4(r11)
.text:8221C450                 stw       r9, 8(r11)
.text:8221C454                 lwz       r7, 0(r4)
.text:8221C458                 stw       r7, 0(r31)
.text:8221C45C                 bl        sub_830B8750
.text:8221C460                 addi      r3, r30, 4
.text:8221C464                 bl        sub_830B8750
