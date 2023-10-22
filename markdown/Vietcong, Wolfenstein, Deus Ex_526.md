## Post #1
- Username: Johner
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 11, 2004 5:58 pm
- Post datetime: 2004-01-11T10:04:40+00:00
- Post Title: Vietcong, Wolfenstein, Deus Ex

Hey! This seems like a great program but I have yet to get it to work. I also have some questions and comments.

First what's the deal with the "malicious script" this program runs. That's what my norton antivirus shield calls it.

I would REALLY like to see support for Vietcong, and Deus Ex (especially Vietcong) does it support any of these and I don't know it?

Anyways it says it supports return to castle wolfenstein which is PK3 files...but when I try to extract I get "run time error '380': Invalid properity value" what's the deal? Also any idea which PK3 and where it's located to find the music files? (perphaps there could be a support document detailing where exactly each file that has the music is on). I don't want to be demanding or anything but I assume if it's known that the game is supported then it's also know where the file is by default. THANKS
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-01-11T12:09:50+00:00
- Post Title: Vietcong, Wolfenstein, Deus Ex

> Reply from Johner
>
> First what's the deal with the "malicious script" this program runs. That's what my norton antivirus shield calls it.

Hmm, I don't know for sure, but I think Norton doesn't like the fact that the program retrieves the necessary multiex scripts from the internet (our multiex server), you can disable this check in Options, and see if Norton shuts up. 

> Reply from Johner
>
> 
I would REALLY like to see support for Vietcong, and Deus Ex (especially Vietcong) does it support any of these and I don't know it?

Anyways it says it supports return to castle wolfenstein which is PK3 files...but when I try to extract I get "run time error '380': Invalid properity value" what's the deal? Also any idea which PK3 and where it's located to find the music files? (perphaps there could be a support document detailing where exactly each file that has the music is on). I don't want to be demanding or anything but I assume if it's known that the game is supported then it's also know where the file is by default. THANKS

No, you can check the files it supports from Help->Supported Games   
Deus Ex uses Unreal engine files (UTX and stuff), there are Unreal engine editors out there, I should download them instead if I were you. 

With regards to PK3 files, MultiEx Commander calls unzip32.dll to process it and this should have been installed during setup. Perhaps there's some version conflict with an unzip32.dll that was already resident on your computer and calling conventions now conflict. You can also check in Help->Supported Games which engine processes a listed Game Archive, either MEX2, MEX3 or ZIP. Any listed with ZIP can be opened with standard PKZIP supporting archivers, such as WinAce, WinRAR and WinZIP. Just use those on PK3 files instead.
