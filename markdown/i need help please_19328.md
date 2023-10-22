## Post #1
- Username: gugus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 16, 2019 12:02 am
- Post datetime: 2019-01-15T16:05:11+00:00
- Post Title: i need help please

Hello,

Im trying to extract multiple .wav from hex editor file...

Could you explain me how to extract it please?

thanks
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2019-01-18T12:41:39+00:00
- Post Title: i need help please

PCM WAV files usually start with the magic string "RIFF" or "RIFX". There are exceptions but this is usually the case.

There are many ways to extract multiple WAV files from a single archve source.

The easiest being using [QuickBMS](https://aluigi.altervista.org/papers/quickbms.zip) and [Aluigi's RIFF Parser BMS script](https://aluigi.altervista.org/bms/riff_parser.bms)

1. Download and extract QuickBMS.

2. Download the RIFF Parser BMS script and put it in the same folder that you extracted QuickBMS to. (Note: these BMS files can be opened with any kind of text editor)

3. Run QuickBMS

4. Select the RIFF Parser BMS script first

5. Then select the file you want to use the script on so it can extract the WAV files

6. Then choose where you want those WAV files to be saved to.

Done
