## Post #1
- Username: Roxas75
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 03, 2010 9:20 pm
- Post datetime: 2011-02-14T17:15:41+00:00
- Post Title: Text Script Editor C, Help!

Hi!
I'm new on this forum, but it's so cool!
I'm a newbie in C programming, but I'm studying it....
Ok, i've a problem:
I'm translating in italian Kingdom hearts Birth by Sleep Final Mix, for PSP, and i want to create a tool for the text editing.
The text format isn't compressed, and you can view it with a simple Hex editor or Text editor.
But the pointers are the problem.
There is a table of pointers at the start of the file, and they are of 2 bytes(es 8B 1C).
They have a common order: the first pointer is on the first 37 and 38 bytes, and the others are the 11 and the 12 bytes, in succession.
I want to create in C a text tool that reads the pointers, go to the offset and shows text, up to the 00 byte, to divide the strings.
I don't know how to do a hex scansion in C, and how to write in C the read of the pointer.
It have o calculate the new pointer too, after the editing...
Have you any idea?
I'll publish the tool if it works!^^
Thanks, if this works
## Post #2
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-15T00:46:58+00:00
- Post Title: Text Script Editor C, Help!

I don't know C, but if you're doing a BBS patch, you should know that Birth by Sleep uses a modified version of Shift-JIS that has specifically different hex codes for those special accented characters. I have composed a list thereof and I hope it is of use to you here:

9980 À
9981 Á
9983 Ä
9985 Ç
9986 È
9987 É
9988 Ê
9990 Ó
9993 Ö
9994 Œ
9996 Ú
9998 Ü
9999 ß
999A à
999B á
999C â
999D ä
999F ç
99A0 è
99A1 é
99A2 ê
99A4 ì
99A5 í
99A6 î
99A7 ï
99A8 ñ
99A9 ò
99AA ó
99AB ô
99AD ö
99AE ù
99AF ú
99B0 û
99B1 ü
99B2 œ
99B3 ¿
99B4 ¡
99B6 „
99B8 º
99CD ™
99CE -

Shift-JIS
8166 ’
8167 “
8168 ”
83D4 χ
875A Ⅶ
## Post #3
- Username: Roxas75
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 03, 2010 9:20 pm
- Post datetime: 2011-02-15T12:43:26+00:00
- Post Title: Text Script Editor C, Help!

> Reply from Mirrorman95
>
> I don't know C, but if you're doing a BBS patch, you should know that Birth by Sleep uses a modified version of Shift-JIS that has specifically different hex codes for those special accented characters. I have composed a list thereof and I hope it is of use to you here:

9980 À
9981 Á
9983 Ä
9985 Ç
9986 È
9987 É
9988 Ê
9990 Ó
9993 Ö
9994 Œ
9996 Ú
9998 Ü
9999 ß
999A à
999B á
999C â
999D ä
999F ç
99A0 è
99A1 é
99A2 ê
99A4 ì
99A5 í
99A6 î
99A7 ï
99A8 ñ
99A9 ò
99AA ó
99AB ô
99AD ö
99AE ù
99AF ú
99B0 û
99B1 ü
99B2 œ
99B3 ¿
99B4 ¡
99B6 „
99B8 º
99CD ™
99CE -

Shift-JIS
8166 ’
8167 “
8168 ”
83D4 χ
875A Ⅶ
Thanks!^^ This help me so much!
But i want to create a text tool for CTD files, that edit itself the pointers....
This is the problem...
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-18T14:27:08+00:00
- Post Title: Text Script Editor C, Help!

fread into a short variable and fseek to it 
reading null-terminated strings is just a while a loop until you hit a null byte

calculating new pointers is adding up all the previous string lengths
