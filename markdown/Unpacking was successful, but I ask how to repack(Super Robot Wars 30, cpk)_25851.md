## Post #1
- Username: Naiah
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 27, 2022 10:24 pm
- Post datetime: 2022-09-27T15:59:55+00:00
- Post Title: Unpacking was successful, but I ask how to repack(Super Robot Wars 30, cpk)

I was looking for a decompilation method of illustration files such as pilot portraits among the files in SRW30.
And I succeeded in decompiling and extracting DDS through programs as CriPakTools.

But now I want to compile the decompiled DDS back into cpk, as a way for it to work without any conflicts in the game.
I tried it once with Reddit's method([https://www.reddit.com/r/Super_Robot_Wa ... ing_tools/](https://www.reddit.com/r/Super_Robot_Wars/comments/qtuh6i/srw30_modding_tools/)), but the game won't start with a repackaged cpk which is several times bigger than old one. So I'll explain how I extracted the dds file so that you can easily understand it, and then ask for advice on how to repack.

This link is a download link of a compressed file including the game file I tried to extract and the tools needed for the decompilation.
[https://drive.google.com/file/d/1TqAvTS ... sp=sharing](https://drive.google.com/file/d/1TqAvTS3Zvl2hXa_NWgiXyLwaubr9Q4FE/view?usp=sharing)
(This compressed file consists of the internal file of the game that I tried to extract with CriPakToolS, and cutter program.)

To explain briefly how to use it, First, run CriPakTools with cmd 
1. [example]  "C:\Debug\CriPakTools.exe" -x -i "C:\psgd1.cpk" -d "C:\decrypted" -q "CryptedByMititei"

And, Converts created bin file as dds by Powershell
2. [example] Get-ChildItem -Path C:\decrypted *.bin | Rename-Item -NewName {[System.IO.Path]::ChangeExtension($_.Name, ".dds")}

This converted dds files are still can't open. Therefore, edit them with the cutter program, cmd again (this is presumed to be the work of organizing the header)
3. [example] "C:\Debug\Cutter\Cutter.exe" "C:\decrypted" "DDS"

Upon completion of these courses, the extracted dds can be viewed and modified through programs such as paint.net.

For the repack of dds, maybe a kind of adder is required to restore the header editing through the cutter, but first of all, I'd like to convert dds back to a bin file and make a cpk that can run the game normally with that bin file.

It was easy to convert dds back to bin files when I applied the powershell command, but I'm having a hard time to compiling cpk(even consisting of bin files that are not converted to dds conversion and cutter process) that runs normally in the game.

I think the CriPakTools that I used for decompilation is also a program related to quickbms, but I don't know how to use it as a compilation. This is where I ask for your help.
