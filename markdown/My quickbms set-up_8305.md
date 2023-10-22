## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T19:05:04+00:00
- Post Title: My quickbms set-up

After awhile, the amount of scripts I have starts to pile up quickly.
Decompression scripts, unpacker scripts, texture-conversion scripts, etc.

So I have the typical quickbms folder with all of the quickbms stuff, and then inside I have a Script folder.

I then wrote a batch script

```
for /D %%X in (%*) do (
	mkdir "%%~dpnX"
	"<path to quickbms>\quickbms.exe" "<path to quickbms>\Script\%~n0.bms" %%X "%%~ndpnX"
)

```


Which
1: creates a folder for each input (just in case stuff gets dumped in the current folder)
2: uses the filename to determine which script I should be calling.

So say I have a script called "DarkBlood_jsp.bms" for a game called "DarkBlood" with archive files with format extension "jsp" (this is just a naming convention I made for myself)

The batch file would be called "DarkBlood_jsp.bat", and then I can just drag-and-drop valid jsp archives over it and it will unpack it.

To make it easier for myself, I created a batch file called "gameName_extension.bat" that I can just copy and rename and start working (clearly the name reminds me what my standard is)

Since quickbms does not create registry keys or anything (and I'm too lazy to create them myself or set up environment variables), I just hardcoded the path to quickbms which shouldn't change very much.

Anyone see any improvements I could make to make the process even faster?
Or any flaws? Or whether it is an optimal way to do it?
