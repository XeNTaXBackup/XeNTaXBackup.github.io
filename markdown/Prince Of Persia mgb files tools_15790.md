## Post #1
- Username: Castellanos
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 30, 2016 7:06 pm
- Post datetime: 2017-01-26T14:50:53+00:00
- Post Title: Prince Of Persia mgb files tools

Hi. Who can help with import and export text from the game Prince Of Persia The Two Thrones.

Can you help me edit this kind of text file?

Example file:
[http://rgho.st/764pPDm5z](http://rgho.st/764pPDm5z)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-01-28T15:50:39+00:00
- Post Title: Prince Of Persia mgb files tools

```
//--- 010 Editor v5.0 Binary Template
//
// File:     menu.mgb
// Author:   wrs
// Revision: 1
// Purpose:  mgb parser
//--------------------------------------

LittleEndian();

char hdr[4]; // "MAGM"
uint unknown_52545;
uint unknown_4011;
ushort unknown;

ushort width;  // 640
ushort height; // 480

FSeek(250); // ??
uint num_1;
FSeek(256+7);
uint num;

Assert(num==num_1);

struct {
  uint unknown;
  uint strlen;
  wchar_t str[strlen];

  Printf("%08x : %s\n", unknown, str);

} strs[num] <optimize=false>;

uint unknown_0;
Assert(FEof());

```


any more samples?

> 0bf8fb9d : Do you want to save the game?
>
> 134c1ea7 : No
>
> 8b47c8e9 : Yes
>
> 5c4bc0d4 : Press \d0\ to continue
>
> 5fef09c1 : Current progress will be lost.\nAre you sure you want to quit?
>
> fd2ab57b : Continue without saving.\n\nAre you sure ?
>
> 92468a18 : A saved game already exist at this location.\nDo you want to overwrite it?
>
> e787905c : Saving the game…\nPlease do not turn off your PlayStation®3 system.
>
> cae8e55e : Item Cost: %d Sand Credits
>
> fd9b3c29 : Unlocked Collectible
>
> f4cf3754 : You do not have sufficient Sand Credits to view this item.
>
> 361280fe : Are you sure you wish to spend %d Sand Credits to purchase and view this item?
>
> 79bb0d7d : Unlocked Collectible
>
> fee5909f : The selected Extra Feature could not be located. Please ensure that you have installed all Extra Features by choosing a Complete installation.
## Post #3
- Username: Castellanos
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 30, 2016 7:06 pm
- Post datetime: 2017-01-28T22:37:59+00:00
- Post Title: Prince Of Persia mgb files tools

> Reply from WRS
>
> Code: Select all//--------------------------------------
//--- 010 Editor v5.0 Binary Template
//
// File:     menu.mgb
// Author:   wrs
// Revision: 1
// Purpose:  mgb parser
//--------------------------------------

LittleEndian();

char hdr[4]; // "MAGM"
uint unknown_52545;
uint unknown_4011;
ushort unknown;

ushort width;  // 640
ushort height; // 480

FSeek(250); // ??
uint num_1;
FSeek(256+7);
uint num;

Assert(num==num_1);

struct {
  uint unknown;
  uint strlen;
  wchar_t str[strlen];

  Printf("%08x : %s\n", unknown, str);

} strs[num] <optimize=false>;

uint unknown_0;
Assert(FEof());


any more samples?

0bf8fb9d : Do you want to save the game?
134c1ea7 : No
8b47c8e9 : Yes
5c4bc0d4 : Press \d0\ to continue
5fef09c1 : Current progress will be lost.\nAre you sure you want to quit?
fd2ab57b : Continue without saving.\n\nAre you sure ?
92468a18 : A saved game already exist at this location.\nDo you want to overwrite it?
e787905c : Saving the game…\nPlease do not turn off your PlayStation®3 system.
cae8e55e : Item Cost: %d Sand Credits
fd9b3c29 : Unlocked Collectible
f4cf3754 : You do not have sufficient Sand Credits to view this item.
361280fe : Are you sure you wish to spend %d Sand Credits to purchase and view this item?
79bb0d7d : Unlocked Collectible
fee5909f : The selected Extra Feature could not be located. Please ensure that you have installed all Extra Features by choosing a Complete installation.

Thanks a lot WRS.

But I do not know how to use it.

There are a few files.

Can you tell me how to do?

I need your help.

[http://rgho.st/6ldlrfmFG](http://rgho.st/6ldlrfmFG)
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-01-29T01:07:55+00:00
- Post Title: Prince Of Persia mgb files tools

thanks i will take a look at more of your samples

the code is a script for "010 Editor" as it says at the top
## Post #5
- Username: Castellanos
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 30, 2016 7:06 pm
- Post datetime: 2017-01-29T10:18:13+00:00
- Post Title: Prince Of Persia mgb files tools

> Reply from WRS
>
> thanks i will take a look at more of your samples

the code is a script for "010 Editor" as it says at the top

Thanks WRS.

I'm waiting for the other files.
## Post #6
- Username: user
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 19, 2016 11:26 pm
- Post datetime: 2017-03-08T13:24:43+00:00
- Post Title: Prince Of Persia mgb files tools

> Reply from WRS
>
> thanks i will take a look at more of your samples

the code is a script for "010 Editor" as it says at the top

Hello guys. Sorry to post here. I have a proble with a game translation since i cannot view the text. There are mostly 4 kind of files .seek, .rif, .aif and some bin. Any idea?
[1.png](https://xentaxbackup.github.io/file/12570_1.png)
## Post #7
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-03-09T06:44:04+00:00
- Post Title: Prince Of Persia mgb files tools

> Reply from user
>
> WRS wrote:thanks i will take a look at more of your samples

the code is a script for "010 Editor" as it says at the top

Hello guys. Sorry to post here. I have a proble with a game translation since i cannot view the text. There are mostly 4 kind of files .seek, .rif, .aif and some bin. Any idea?

Ask to other guys or try find a script or tool for that
This file is compressed. This page just for princ of persia!
## Post #8
- Username: user
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 19, 2016 11:26 pm
- Post datetime: 2017-03-09T08:09:34+00:00
- Post Title: Prince Of Persia mgb files tools

> Reply from GHOST DEAD
>
> user wrote:WRS wrote:thanks i will take a look at more of your samples

the code is a script for "010 Editor" as it says at the top

Hello guys. Sorry to post here. I have a proble with a game translation since i cannot view the text. There are mostly 4 kind of files .seek, .rif, .aif and some bin. Any idea?

Ask to other guys or try find a script or tool for that
This file is compressed. This page just for princ of persia!

Sorry i made post here and there but none has replied yet. I have searched for tools or scripts but i have not found anything. I made a new theard
