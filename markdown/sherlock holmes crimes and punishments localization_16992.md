## Post #1
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-09-09T12:47:03+00:00
- Post Title: sherlock holmes crimes and punishments localization

I need you help me edit text file. Data_SH7_CaseInfo, I'm in very need, pleaseee

[CaseInfo_bp.rar](https://xentaxbackup.github.io/file/13292_CaseInfo_bp.rar)
## Post #2
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-09-09T15:51:32+00:00
- Post Title: sherlock holmes crimes and punishments localization

Try mod file
[Mod .Data_SH7_CaseInfo.rar](https://xentaxbackup.github.io/file/13293_Mod .Data_SH7_CaseInfo.rar)
## Post #3
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-09-10T02:21:40+00:00
- Post Title: sherlock holmes crimes and punishments localization

> Reply from makcar
>
> Try mod file
No, i think it will appear in this part of the file. And i need to edit support for unicode or utf8


[CaseInfo_bp.rar](https://xentaxbackup.github.io/file/13296_CaseInfo_bp.rar)
## Post #4
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2017-09-10T07:09:08+00:00
- Post Title: sherlock holmes crimes and punishments localization

Text files are a mess, I found text in a lot of different files:
*.Data_SH7_Action
*.Data_SH7_Mappoint
*.Data_SH7_Clue
*.Data_SH7_Deduction
*.Data_SH7_Document
*.Data_SH7_Item
*.Data_SH7_Note
*.Data_SH7_Task
*.Data_SH7_DetectiveRank
*.Data_SH7_MoralRank
*.Data_SH7_CaseMessage
*.Data_SH7_CaseTrophy
*.Data_SH7_Conclusion
*.Data_SH7_MoralChoice
*.Data_SH7_CaseInfo
*.Data_SH7_Character
*.SoundNodeWave
In your case, Data_SH7_CaseInfo always starts in offset 0x8C (String Length including null terminator = 4 bytes) >> String >> + 0x1D Second string length >> Second string
But sometimes the string is unicode, simetimes is ANSI and simetimes the file have the two enconding, as I say, a mess...
## Post #5
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-09-10T09:10:47+00:00
- Post Title: sherlock holmes crimes and punishments localization


