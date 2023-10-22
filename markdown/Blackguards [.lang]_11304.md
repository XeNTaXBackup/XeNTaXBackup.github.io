## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-03-11T05:31:45+00:00
- Post Title: Blackguards [.lang]

This game uses Unity, however the localization files are in the Languages folder.
First I thought they are editable, since they are visible with Notepad++, but I can't change even a character or in-game every line gets shifted.
"Main.lang" definetely has localization, but I uploaded other files too, just in case.
[http://www54.zippyshare.com/v/86901337/file.html](http://www54.zippyshare.com/v/86901337/file.html)
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-03-17T18:40:36+00:00
- Post Title: Blackguards [.lang]

Here tools to try: [http://www.sendspace.com/file/hjq5s5](http://www.sendspace.com/file/hjq5s5)
I include barracuda's UnityRaw script for unpack lang files.
Put quickbms in the folder with tools.

Drag a lang file to the bat.
You need to use utf8 encoding on xml when edit.
Pack the CustomAssetBundle file, then the lang file.
## Post #3
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-03-18T10:12:28+00:00
- Post Title: Blackguards [.lang]

Thank you!
So I dragged "main.lang" onto the lang_unpack.bat. I got a "CustomAssetBundle-e390a1c586f7a52448ebe5e9aebae722" file. I unpacked that with "customassetbundle_unpack.bms" and QuickBMS.
I got 2 files: "1_" and "2_English.xml".
I modified a line in "2_English.xml".
When I use customassetbundle_pack.exe and choose the "CustomAssetBundle-e390a1c586f7a52448ebe5e9aebae722" file, I get this error:
[http://i.imgur.com/QDrEdXI.png](http://i.imgur.com/QDrEdXI.png)
## Post #4
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-03-18T12:07:53+00:00
- Post Title: Blackguards [.lang]

The .bat unpacks both files. Just press "y" when quickbms says create a folder.
So CustomAssetBundle from lang must be in "langname_unpacked\" folder.
Files in CustomAssetBundle must be unpacked to "langname_unpacked\unpacked" folder.
