## Post #1
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2018-01-15T10:26:24+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

Hi everyone, I'm trying to mod the font support unicode characters, but my ability can not do that.
So, I volunteered to donate $40 for anyone help me create the tools mod this font. Thanks
Link of the font: [https://drive.google.com/file/d/1SXjryK ... wnkmK/view](https://drive.google.com/file/d/1SXjryKUI_1Z9T4QUz_O8A_mfeLWwnkmK/view)
I really hope you can help me
## Post #2
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2018-01-18T02:43:40+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

Need some helps, thanks
## Post #3
- Username: HuninHune
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 01, 2012 7:28 am
- Post datetime: 2018-01-19T12:01:11+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

Without knowing what game these are for or even what language they are in this is the best I can do

010 Editor Binary Template for 3 of the files(ASC16.FNT is a different format)
The template isn't perfect it's just thrown together really quick

```
{
    char HeaderText[32];
    unsigned int DataLength;
    unsigned int FontEntries;
    int Height;
    int Width;
    byte NULLS[16];
    int FontDataLocations[FontEntries];
    local int entry;
    for (entry=0; entry <= FontEntries; entry++) {
        if (FontDataLocations[entry] == 0 && entry != 0) {
            typedef struct {
	            char    IconData[0];
            } NULLICON;
            NULLICON IconEntry;
        } else {
            typedef struct {
                local int s;
                local int n = 1;
                while ( s == 0 ) {
                    s = FontDataLocations[entry+n];
                    n++;                
                }
	            char    IconData[s-FontDataLocations[entry]];
            } ICON;
            ICON IconEntry;
        }
    }
}

```
## Post #4
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2018-01-21T06:02:38+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

> Reply from HuninHune
>
> Without knowing what game these are for or even what language they are in this is the best I can do

010 Editor Binary Template for 3 of the files(ASC16.FNT is a different format)
The template isn't perfect it's just thrown together really quick
Code: Select allwhile( !FEof() )
{
    char HeaderText[32];
    unsigned int DataLength;
    unsigned int FontEntries;
    int Height;
    int Width;
    byte NULLS[16];
    int FontDataLocations[FontEntries];
    local int entry;
    for (entry=0; entry <= FontEntries; entry++) {
        if (FontDataLocations[entry] == 0 && entry != 0) {
            typedef struct {
	            char    IconData[0];
            } NULLICON;
            NULLICON IconEntry;
        } else {
            typedef struct {
                local int s;
                local int n = 1;
                while ( s == 0 ) {
                    s = FontDataLocations[entry+n];
                    n++;                
                }
	            char    IconData[s-FontDataLocations[entry]];
            } ICON;
            ICON IconEntry;
        }
    }
}
Hi HuninHune,
I tried to use the 010 Editor for the first time, but I do not know how to mod my fnt font above. Sorry for my little experience, can you help me?
Thanks
## Post #5
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2018-01-29T03:58:10+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

Really need more help  Thanks
## Post #6
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2018-01-31T15:18:54+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

I see you're more like into graphic editor for font... 40USD seem fair, I'll try to sort things out
## Post #7
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2018-02-01T03:16:48+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

> Reply from MaKiPL
>
> I see you're more like into graphic editor for font... 40USD seem fair, I'll try to sort things out
Yeah ! Thanks
## Post #8
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2018-02-07T12:56:27+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

some more reversed info for ASC12.FNT as example:

```
FontSize at 0x20, FileSize-this = x now substract 64 which is header data
```

Therefore: ((1122983-1067027) - 64 ) / 13973 (font count) = 4

This indicates 4 bytes per pointer, that means it's unsigned int. 
First pointer at 0x00, next 0x04, it means first entry is 0xC long. That's impossible to declare 12*12 pixel data upon 12 bytes. Next entries vary from 12, 18, 22, 29 bytes.

FontEntry 0 is at 55956
FontEntry 1 is at 55968
FontEntry 2 is at 55997

FontEntry 0 contains only 0x0C
FontEntry 1 starts with 0x0C
FontEntry 3 starts with 0x0C too
FontEntry 5126 also starts with 0x0C

It's some wicked thing going on here... Could you please write which software or game uses that?
## Post #9
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2018-02-09T06:22:34+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

> Reply from MaKiPL
>
> some more reversed info for ASC12.FNT as example:
Code: Select allFontSize at 0x20, FileSize-this = x now substract 64 which is header data
Therefore: ((1122983-1067027) - 64 ) / 13973 (font count) = 4

This indicates 4 bytes per pointer, that means it's unsigned int. 
First pointer at 0x00, next 0x04, it means first entry is 0xC long. That's impossible to declare 12*12 pixel data upon 12 bytes. Next entries vary from 12, 18, 22, 29 bytes.

FontEntry 0 is at 55956
FontEntry 1 is at 55968
FontEntry 2 is at 55997

FontEntry 0 contains only 0x0C
FontEntry 1 starts with 0x0C
FontEntry 3 starts with 0x0C too
FontEntry 5126 also starts with 0x0C

It's some wicked thing going on here... Could you please write which software or game uses that?
This is the download link: [https://mega.nz/#!VsFh0JgJ!MayhAnaWIgii ... ZXo1-PO-7Q](https://mega.nz/#!VsFh0JgJ!MayhAnaWIgiiEb3ngNqU8hftRxgPeAR0oZXo1-PO-7Q)
Its a chinese game  Thanks
## Post #10
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2018-02-09T16:35:14+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

archive is password protected
## Post #11
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2018-02-12T03:24:23+00:00
- Post Title: Donate $40 for the tools mod FNT font of this game

> Reply from MaKiPL
>
> archive is password protected
Sorry, the password is: gamevn.com
