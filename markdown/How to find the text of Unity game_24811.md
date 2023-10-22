## Post #1
- Username: komputerdelisi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 25, 2018 3:21 am
- Post datetime: 2021-12-06T21:27:53+00:00
- Post Title: How to find the text of Unity game?

Hello. I did the steps on the site below for the road 96 game.

[https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)

As it appears in the first picture, when I search for a word in the game, the total commander program finds the text.

1. [](https://www.hizliresim.com/8rfxjcj)

but it just shows up as "resources.assets". there is no folder name.

I extracted all the files with the AssetStudioGUI tool. but no "txt" or similar text file was output. I looked at all the files one by one.

2.[](https://www.hizliresim.com/fxy9ccf)

please help me. How do I get the language files for the road 96 game.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-06T22:22:12+00:00
- Post Title: How to find the text of Unity game?

> please help me. How do I get the language files for the road 96 game.

I think that maybe you haven't read this tutorial carefully enough. There is an instruction there to search again after extracting data from resources.assets archive (it's important).

> but no "txt" or similar text file was output.
It won't always be text file. Sometimes it will be binary file. In this situation you should edit text only in hex editor or try to find/create a tool for parsing binary file containing text data.



Btw, on your screenshot I can see "TextAsset" directory. I would start searching there. 

Btw2, don't discard your other findings. Text can also be in "level45", "level88" files, so extract data from them as well.
## Post #3
- Username: komputerdelisi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 25, 2018 3:21 am
- Post datetime: 2021-12-07T06:31:31+00:00
- Post Title: How to find the text of Unity game?

thank you for the answer. yes i realized i skipped some steps and i did everything from the beginning. this time I searched for a subtitle text in the game. The program found 2 files in it. "level36" and again "resources.assets". 

[](https://www.hizliresim.com/jfg7x1d)


I exported 2 files. I searched the subtitle text again with Total Commander 64 program. but still didn't find it.

[](https://www.hizliresim.com/dm73h00)

Also, there are 4 meaningless files in the TextAsset folder. It's not an in-game text file.

[](https://www.hizliresim.com/1so7o1h)
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-07T08:28:10+00:00
- Post Title: How to find the text of Unity game?

Ok, that's weird. Can you upload for me those two files - "level36" and "resources.assets"?
I will check it myself and I will let you know.
## Post #5
- Username: komputerdelisi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 25, 2018 3:21 am
- Post datetime: 2021-12-07T09:33:11+00:00
- Post Title: How to find the text of Unity game?

here:

[https://disk.yandex.com.tr/d/4xhZotABQ1rD5Q](https://disk.yandex.com.tr/d/4xhZotABQ1rD5Q)
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-07T09:57:09+00:00
- Post Title: How to find the text of Unity game?

Ok, so I couldn't use AssetStudio this time, but I have used UnityEx instead.

You need to open your assets files in UnityEx, extract all data and then search in "Unity_Assets_Files" directory for text.
I have found two files [https://i.imgur.com/ojHnh0z.png](https://i.imgur.com/ojHnh0z.png)

ASSETS\Unity_Assets_Files\level36\level36_00001.-51
and
ASSETS\Unity_Assets_Files\resources\resources_00001.-36

Those two are binary files, so you can open end edit them in hex editor (like Hex Workshop)
and this will be the result [https://i.imgur.com/pDhQJDB.png](https://i.imgur.com/pDhQJDB.png)
## Post #7
- Username: komputerdelisi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 25, 2018 3:21 am
- Post datetime: 2021-12-07T10:19:39+00:00
- Post Title: How to find the text of Unity game?

Thanks for your help. In another forum a guy sent me the language file in ".csv" format. but when I say how to import, he asks me to buy a paid program  I uploaded the file he sent me for you. how can i pack this file back again.

HERE:
[https://disk.yandex.com.tr/d/o86fV3EGXyjqTA](https://disk.yandex.com.tr/d/o86fV3EGXyjqTA)
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-07T15:52:55+00:00
- Post Title: How to find the text of Unity game?

> how can i pack this file back again.

I don't know. There is a program called UnityText which may help you with translation [https://forum.zoneofgames.ru/topic/47582-unitytext/](https://forum.zoneofgames.ru/topic/47582-unitytext/)
but in some cases a custom program needs to be written to parse data.
## Post #9
- Username: komputerdelisi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 25, 2018 3:21 am
- Post datetime: 2021-12-07T16:47:44+00:00
- Post Title: How to find the text of Unity game?

somehow I finally managed to import it. but the game looks like this. I think I will give up...


[](https://www.hizliresim.com/gphee5t)
## Post #10
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-07T19:21:43+00:00
- Post Title: How to find the text of Unity game?

Did you edit the file using HexEditor? If so, remember you cannot add any data in there. Only replace. Meaning that if you translate some text, the translation must have the same length as untranslated text. Otherwise you will "break" the file and it won't be readable by the game.

Try to use AssetStudo again and extract all files with PathID 51 and 36. Atleast one of them should be MonoBehaviour file.
Also AssetStudio can only export, it does not have import function.

So either you can use UnityEx (and I think you will need premium version for that) or UABE (UnityAssetBundleExtractor).
## Post #11
- Username: komputerdelisi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 25, 2018 3:21 am
- Post datetime: 2021-12-07T20:12:49+00:00
- Post Title: How to find the text of Unity game?

No, I didn't use hex editor. In a different forum a guy shared the game's text files as .csv file format. but did not say how to pack. I also found some bat commands. this way i managed to import the language text file. but as above, codes appear, not language texts. also I can't open files with UnityEx. It says you need to buy premium version. and the AssetBundleExtractor program doesn't open the files.
## Post #12
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-07T22:02:40+00:00
- Post Title: How to find the text of Unity game?

> I can't open files with UnityEx. It says you need to buy premium version.
Well, we can't really force you to buy anything, but it's only 15$, so you should at least consider buying it.
It works pretty well with all newer games.

> No, I didn't use hex editor.
Maybe you should. It's always the first thing you should try - to change one letter in some text (without changing it's length) and see if changed text will appear in game.

> In a different forum a guy shared the game's text files as .csv file format. but did not say how to pack.
Can you tell us the name of this forum and name of the program he used?

> I also found some bat commands.
We need more details. What was in those bat commands etc.

> and the AssetBundleExtractor program doesn't open the files.
There are also similar programs like those [http://wiki.xentax.com/index.php/Unity_ ... d_Programs](http://wiki.xentax.com/index.php/Unity_Assets#Supported_Programs)
## Post #13
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-07T23:49:17+00:00
- Post Title: How to find the text of Unity game?

So I downloaded the game and now I think I know where your problem is.
The tool you extract monobehaviour with needs assembly DLLs. Meaning there should be a 'Managed' folder in the game directory.

But this is a newer game so there is no 'Managed' folder with assembly DLLs. But there is il2cpp folder and you need to dump those DLLs from that. So, you can download this tool:
[https://drive.google.com/file/d/1JN2ats ... sp=sharing](https://drive.google.com/file/d/1JN2atsQlLx6n4FPxlRfQjoY5TaBBP9s6/view?usp=sharing)

It will dump DLLs from il2cpp files. Once you download it extract it somewhere and inside 'il2cpp dumper' directory is file called 'cmd il2cpp dumper.bat'. Open this file in notepad and edit your paths.

First specify path to 'GameAssembly.dll'. This file is in your game's main directory.
Next is 'global-metadata.dat' file. This file is in Road 96_Data\il2cpp_data\Metadata
And the last path is where you want DLLs to be extracted to. Create a folder somewhere outside of your system drive and name it 'Managed' and extract the files there.

Example:
[](https://ibb.co/w7dFgZV)

Go in the Managed folder and delete everything but the subfolder. Now move everything from the subfolder to your 'Managed' folder and delete 'DummyDll' folder.
Now move this 'Managed' folder in your Road 96/Road96_Data directory.

Now you should be able to properly extract monobehaviours. Open AssetStudio. Open resources.assets. From the upper menu choose 'Filter Type - MonoBehaviour' click on any file and now in the pop-up window choose the 'Managed' folder and click on 'Open'.

Now you can extract every MonoBehaviour (Export - All Filtered Assets) and repeat the TotalCommander method to find your text file.

[](https://ibb.co/rHGBf1V)


As for Import:

I used Unity Asset Bundle Extractor Avalonia. This is not the same tool I mentioned before. This one will work with newer versions of unity games.
[https://github.com/nesrak1/UABEA/releases](https://github.com/nesrak1/UABEA/releases)

Open resources.asset and find a file with pathID 28660. Click on Export Dump (USE THIS FILE FOR TRANSLATION, NOT THE ONE FROM ASSET STUDIO) and after you edit it, click on Import DUMP. Now make sure there is a star on the far right of the file under the Modified column.

Now File-Save and save it as a new file. You can't overwwrite the old one. After you save the new one, close the tool, delete old one a rename the new one.

[](https://ibb.co/xXM403Y)
## Post #14
- Username: komputerdelisi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 25, 2018 3:21 am
- Post datetime: 2021-12-08T18:29:57+00:00
- Post Title: How to find the text of Unity game?

first of all thanks for your help. I finally got the game files. but there is a problem in the "As for Import" section. I have 1 question. If we are going to import with Unity Asset Bundle Extractor Avalonia, why do we extract the files with the "AssetStudio" program? the real problem is this. Unity Asset Bundle Extractor Avalonia program only exports with the "dat" extension. When I select txt extension, the program closes automatically. but I can import the ".dat" file that I output. but the "dat" file is in notepad++ etc. not programmatically edited. It contains mixed text. How did you import? Can you export the attached file for me as txt? because i have the steam version.

[https://disk.yandex.com.tr/d/x9KgHOOZjlvUTg](https://disk.yandex.com.tr/d/x9KgHOOZjlvUTg)
## Post #15
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-08T20:29:39+00:00
- Post Title: How to find the text of Unity game?

If you are going to import with ABEA then you should export with that as well.

[](https://ibb.co/xgcNTQf)

Red - Export
Green - Import
Pink - After import, save file after you see this star symbol.
## Post #16
- Username: komputerdelisi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Dec 25, 2018 3:21 am
- Post datetime: 2021-12-08T20:59:28+00:00
- Post Title: Re: How to find the text of Unity game?

When I click export, the program closes itself.
## Post #17
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-09T05:21:38+00:00
- Post Title: Re: How to find the text of Unity game?

Perhaps the steam version was udated so it does not work anymore. The only tool that come to my mind is UnityEx, but you need premium version to export monobehaviors.
