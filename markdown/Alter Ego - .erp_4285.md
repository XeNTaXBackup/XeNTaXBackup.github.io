## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-31T20:10:53+00:00
- Post Title: Alter Ego - *.erp

I thought it would be nice to post the quickBMS scripts I write into the forum. Maybe someone can then make entries on the Xentax Wiki.

Here's the script to extract the files from the game "Alter Ego". A little unusual to have these short-variables in between...

```
# file type: *.erp
# (c) 2010 AlphaTwentyThree

set NAMEDAT 0x3D
get FILES short

for i = 1 <= FILES
   get ZEROS short
   get DUMMY long
   get SIZE long
   get OFFSET long
   get TYPE short
   get NAME string
   savepos CURR
   strlen NAMEL NAME
   set RES NAMEDAT
   math RES -= NAMEL
   math CURR += RES
   goto CURR
   
   log NAME OFFSET SIZE
next i
```
The file extensions are specific, for example *.ESA are sounds and music, *.EIT are dds files and so on. If you want you can write a little extractor into the code so you can directly work with the files. I don't have the game so I can't check all formats.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-31T20:42:57+00:00
- Post Title: Alter Ego - *.erp

Nice! But why don't you put it in the wiki  ?
## Post #3
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2010-08-23T18:21:01+00:00
- Post Title: Alter Ego - *.erp

Strange but, the structure you provided seems wrong to me ?!

Here's my pack/unpacker for Alter Ego's ERP files. I'll be happy for any feedback.
[Alter_Ego_ERP_unpacker_1.0.zip](https://xentaxbackup.github.io/file/3364_Alter_Ego_ERP_unpacker_1.0.zip)
## Post #4
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-08-29T18:06:36+00:00
- Post Title: Alter Ego - *.erp

Works great XpoZed,   . The problem is all files are encrypted (EMA, ESA, EIT and so on).   

Its look like they wanted protect Alter Ego's files like a state secret.   

Regards.
## Post #5
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2010-08-29T18:49:43+00:00
- Post Title: Alter Ego - *.erp

> Reply from Sheen
>
> Works great XpoZed,   . The problem is all files are encrypted (EMA, ESA, EIT and so on).   

Its look like they wanted protect Alter Ego's files like a state secret.   

Regards.
Not encrypted actually... ESA are OGG, EIM are DDS and so on... they just have a small header at the beginning.
For example EIM has the following structure :

```
   header[DWORD] {
      "EIM\x20"
   }
   size[DWORD] {
      DDS file size
   }
   width[DWORD] {
      DDS width dimension
   }
   height[DWORD] {
      DDS height dimension
   }
   DDS[size] {
      Standard DDS file data goes here...
   }
   t[n] {
      N number of \x00 bytes to make the whole file dividable by \x0F
   }
}

```
## Post #6
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-08-30T04:19:32+00:00
- Post Title: Alter Ego - *.erp

Aha, ok thank for the advise. But if anybody wants to open a dds file, how he can do it? I suposse is not so easy like changing the extension of the file (I tried   ), and the lang files don't appear. Where i looked for I only found code...and I looked for in all compressed files.  

Regards.
## Post #7
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2010-08-30T08:49:28+00:00
- Post Title: Alter Ego - *.erp

You can edit DDS easily with photoshop and a free DDS plugin ffrom nvidia (google it).
To edit EIM files as DSS, open the file with some text editor and remove the first 16 bytes until you reach the DDS header. Then change the extension to .DDS and you're ready.
The language file is located in US_D_UI_Local.erp as Alter_Ego_Texty.ete.
The ETE file has very simple structure, so you can edit it quite easy with any HEX editor.

```
	header[4] {
		"ETE\0x20"
	}
	unknown[9] {
		\x01\x00\x01\x00\x00\x00\x00\x00\x10
	}
	row[0] {
		id_len[WORD] {
			
		}
		id[id_len] {
			
		}
		unk[DWORD] {
			
		}
		data_len[3] {
			
		}
		data {
			str1[n] {
				// 0x00 terminated
			}
			str2[n] {
				// 0x00 terminated
			}
			str3[n] {
				// 0x00 terminated
			}
			str4[n] {
				// 0x00 terminated
			}
			str5[n] {
				// 0x00 terminated
			}
			str6[n] {
				// 0x00 terminated
			}
			str7[n] {
				// 0x00 terminated
			}
			str8[n] {
				// 0x00 terminated
			}
			str9[n] {
				// 0x00 terminated
			}
			eod[BYTE] {
				"\x10"
			}
		}
	}
	...
	row[n] {
		...
	}
}
```
## Post #8
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-08-30T09:39:34+00:00
- Post Title: Alter Ego - *.erp

oh, thanks a lot XpoZed!

I have two dds programs (dds converter and image converter plus, and photoshop and fireworks of course) already cause I work a lot with graphics files, but i'll take a look for that nvidia dds plugin that you said.  

Best regards.
## Post #9
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-02T21:05:42+00:00
- Post Title: Alter Ego - *.erp

I created two simple programs help converting files from .EIM to .DDS and vice-versa.
Now I'm working on .ETE <-> .TXT converter, to help translating the game texts.

Updated! I combined the two programs into one. If the given file extension is .EIM, then converts to .DDS; If .DDS, then converts to .EIM
## Post #10
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-05T04:26:34+00:00
- Post Title: Alter Ego - *.erp

Here's the new proggy: the .ETE <-> .TXT converter.
## Post #11
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2010-09-05T19:48:20+00:00
- Post Title: Alter Ego - *.erp

btw, hit Ctrl+F1 while playing Alter Ego
## Post #12
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-07T06:30:22+00:00
- Post Title: Alter Ego - *.erp

The latest version of my ETE <-> TXT and EIM <-> DDS converter.
I added new function to help the updating of .ERP files.
(To replace only one file in the existing ERP archive)

Example of the usage:
1: extract the files from the contents of the "US_D_UI_Local.erp" archive:
AE_TOOL.EXE X US_D_UI_Local.erp e:\mydir

The tool automatically generates a hash value for each file, to help the replacing:

Alter_Ego_Texty.ete => Alter_Ego_Texty.[46690988f13307b07508d45d].ete

2: convert to text file:
AE_TOOL.EXE Alter_Ego_Texty.[46690988f13307b07508d45d].ete

3: edit your Alter_Ego_Texty.[46690988f13307b07508d45d].txt file

4: reconvert it to .ete file:
AE_TOOL.EXE Alter_Ego_Texty.[46690988f13307b07508d45d].txt

5: insert it into the original archive:
AE_TOOL.EXE R US_D_UI_Local.erp Alter_Ego_Texty.[46690988f13307b07508d45d].ete


You can also convert EIM files to DDS and vice-versa
## Post #13
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-09-07T07:32:26+00:00
- Post Title: Alter Ego - *.erp

I'm gonna try your new tool bacter. Using XpoZed tool with your executables together all works perfectly. 

Thanks to both.
## Post #14
- Username: JirkaB
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 23, 2010 5:36 pm
- Post datetime: 2010-11-23T22:56:58+00:00
- Post Title: Alter Ego - *.erp

> Reply from bacter
>
> 2: convert to text file:
AE_TOOL.EXE Alter_Ego_Texty.[46690988f13307b07508d45d].ete
Hello Bacter, extract was OK, but convert does not work, please help me, what am i doing wrong.

edit:   it works!!! , great work!!!, thanks a lot, and sorry for spam..
## Post #15
- Username: pitbon1986
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 05, 2012 5:55 pm
- Post datetime: 2012-01-05T10:57:53+00:00
- Post Title: Alter Ego - *.erp

thx for all
## Post #16
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2014-02-24T21:09:54+00:00
- Post Title: Re: Alter Ego - *.erp

I would be grateful if somebody sends me bacter conventer because I want to change .ETE file into txt.
## Post #17
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-02-26T06:27:30+00:00
- Post Title: Re: Alter Ego - *.erp

where is the tool for download pls ? No link at all
## Post #18
- Username: Vecna
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 20, 2015 9:28 am
- Post datetime: 2016-06-17T10:36:01+00:00
- Post Title: Re: Alter Ego - *.erp

Sorry for this bump, but I need the AE_TOOL.EXE in order to translate this game.
I wonder if someone can help me out...
## Post #19
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-06-17T12:52:50+00:00
- Post Title: Re: Alter Ego - *.erp

Here you are.
[AE_tool_by_Bacter.zip](https://xentaxbackup.github.io/file/11070_AE_tool_by_Bacter.zip)
## Post #20
- Username: Vecna
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 20, 2015 9:28 am
- Post datetime: 2016-06-18T21:30:35+00:00
- Post Title: Re: Alter Ego - *.erp

Thank you very much merlinsvk!
