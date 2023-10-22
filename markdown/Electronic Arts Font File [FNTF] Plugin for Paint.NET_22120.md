## Post #1
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-05-08T04:31:43+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

Purpose:
This plugin allows for "*.ffn" files to be edited directly in Paint.NET. It was a request made by Rancher#1263 on Discord.

Format:
FNTF Files use an edited version of the infamous RAWBMP/2 Format which originates in the PS2. Funnliy enough, the font files are present and are eing used on PC games.

The most of the format is currently unknown territory. But this plugin works well enough to open, edit and save the image within the files. Currently, the known bits are:

```
Int32 = File Size - 0x10
0x14 = Unknown
Int32 = Image Location

// Skip to Image Location
Int32 = 0x7A
Int16 = Width
Int16 = Height
Int64 = Padding
[Width * Height / 2] = Image Data

Image Info:
Depth: 4BPP
RGB = 0xFFFFFF
Alpha = 4BPP Value

Image Structure Formula:
for (int i = 0; i < PixelData.Count; i++)
{
    byte b = PixelData[i];

    byte b2 = (byte)(b & 0xF);
    b = (byte)(b >> 4 & 0xF);

    Image.SetPixel(x, y, Color.FromArgb(16 * b, 255, 255, 255));
    Image.SetPixel(x + 1, y, Color.FromArgb(16 * b2, 255, 255, 255));

    x += 2;

    if (x >= 256)
    {
        x = 0;
        y += 1;
    }
}

```

Odds and Ends:
[*] This plugin is non-destructive, it will NOT hurt the possibly existent font data
[*] It does not care about color, only Alpha values
[*] Supports Transparency

Installation:
Extract the .DLL file inside the downloaded .ZIP file to C:/Program Files/paint.net/FileTypes.

Screenshots:




Download:
Attached Below.

Please do not hesitate to report any bugs that occur.
Keep on Moddin'!

- TopazTK
[EAFont.zip](https://xentaxbackup.github.io/file/18104_EAFont.zip)
## Post #2
- Username: Pikachok
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 10, 2018 5:02 pm
- Post datetime: 2020-05-10T09:43:10+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

Can you adapt the plugin for paint.net version 3.5.11?
## Post #3
- Username: TopazTK
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 22, 2019 1:26 am
- Post datetime: 2020-08-01T19:59:19+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

> Reply from macalok ↑Sun May 10, 2020 5:43 pm at Sun May 10, 2020 5:43 pm
>
> 
Can you adapt the plugin for paint.net version 3.5.11?

Sorry, I was away for a bit due to personal reasons. Does this plugin not work with PDN 3.5.11?
I will check this issue out.
## Post #4
- Username: Pikachok
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 10, 2018 5:02 pm
- Post datetime: 2020-08-19T21:47:03+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

> Reply from TopazTK ↑Sun Aug 02, 2020 3:59 am at Sun Aug 02, 2020 3:59 am
>
> 
macalok wrote: ↑Sun May 10, 2020 5:43 pm
Can you adapt the plugin for paint.net version 3.5.11?


Sorry, I was away for a bit due to personal reasons. Does this plugin not work with PDN 3.5.11?
I will check this issue out.

No, for some reason, when investing fashion in the version 3.5.11, the mod does not work.
## Post #5
- Username: BurningUp
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 28, 2021 1:38 am
- Post datetime: 2021-02-04T12:28:30+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

Nothing works. Can anyone help add Cyrillic to fonts? 
[ConduitMdITC8b.ffn](https://drive.google.com/file/d/1OFXBeHz5AY3UQJWTyMzU8sFIszKsceKq/view?usp=sharing)
[ConduitMdITC10b.ffn](https://drive.google.com/file/d/145arQ_A-V4NZMYlOf7bE6N123j7yg35z/view?usp=sharing)
[ConduitMdITC12b.ffn](https://drive.google.com/file/d/1GuudBO8a2mZxbJ4VOxp708Onsbq8lh2s/view?usp=sharing)
[ConduitMdITC14b.ffn](https://drive.google.com/file/d/170gpB-pDIiD55dDdbhDACEr-X2OEKZnF/view?usp=sharing)
[ConduitMdITC16b.ffn](https://drive.google.com/file/d/1uMUBIKRqSrb8NQJlyYOtoj7h9mVZMiB0/view?usp=sharing)


If you help, I will be the happiest
## Post #6
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2022-06-03T04:01:47+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

All these files from NHL 2000 cannot be read by the plugin. The following two replies will feature unreadable files from NHL 2001 and 2002, as one attachment is the maximum for each reply. >:(
[Screenshot_June_02_2022_08_58_53_PM.png](https://xentaxbackup.github.io/file/22301_Screenshot_June_02_2022_08_58_53_PM.png)
## Post #7
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2022-06-03T04:02:14+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

The NHL 2001 example.
[Screenshot_June_02_2022_08_56_44_PM.png](https://xentaxbackup.github.io/file/22302_Screenshot_June_02_2022_08_56_44_PM.png)
## Post #8
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2022-06-03T04:02:30+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

The NHL 2002 example.
[Screenshot_June_02_2022_08_58_33_PM.png](https://xentaxbackup.github.io/file/22303_Screenshot_June_02_2022_08_58_33_PM.png)
## Post #9
- Username: bugsimtasdesimt
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 02, 2022 11:02 pm
- Post datetime: 2022-12-22T21:11:35+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

All fonts for Need for Speed: High Stakes don't open and only some open for Need for Speed: Porsche Unleashed...
## Post #10
- Username: helendam
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 15, 2023 3:17 pm
- Post datetime: 2023-04-15T07:30:06+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

> Reply from BurningUp ↑Thu Feb 04, 2021 8:28 pm at Thu Feb 04, 2021 8:28 pm
>
> 
If you help, I will be the happiest

yes, i so think
## Post #11
- Username: hok1994
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 10, 2023 6:23 pm
- Post datetime: 2023-06-10T22:22:28+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

is there any way I can change the height of the background if I need to fit more characters? because the program does not allow this
## Post #12
- Username: SlavaVlasov
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:00 am
- Post datetime: 2023-06-25T23:31:56+00:00
- Post Title: Electronic Arts Font File [FNTF] Plugin for Paint.NET

Cool!
