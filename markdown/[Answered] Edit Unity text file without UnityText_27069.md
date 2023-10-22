## Post #1
- Username: Bembee
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 01, 2023 4:51 pm
- Post datetime: 2023-08-06T20:01:19+00:00
- Post Title: [Answered] Edit Unity text file without UnityText?

Hello,

I am translating a Unity Android game, I extract the text (.dat) file from resources.assets with UABEA but unfortunately [UnityText](https://forum.zoneofgames.ru/topic/47582-unitytext/) can't open all .dat file, (not recognize the text on those file) just a few.
Is there any other similar program like UnityText or any other way to edit those file? (if I edit the files with notepad++ the game not start, Unity Text 2 works well if it can open .dat files)

There is the picture of 2 files, one of them where it's working, and the other it's not.



2023-08-07_23h32_17.png (69.65 KiB) Viewed 128 times



Here is a sample file (both the working and the non working one).
[https://gofile.io/d/aap9GC](https://gofile.io/d/aap9GC)
## Post #2
- Username: enarkay
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 26, 2023 12:46 pm
- Post datetime: 2023-08-08T09:45:43+00:00
- Post Title: [Answered] Edit Unity text file without UnityText?

I've personally never worked on mobily game localization yet.
So while I can't be 100% sure, I'm guessing the big picture must be the same.
Judging from your attachment and pictures, do you have access to resources.assets?
Instead of extracting ~~~resources.assets-27.dat (raw format data), open resources.assets with UABEA, look for the asset you wish to edit, and export dump in either txt/json. You can edit the exported txt/json, and the insert it back with the import dump feature.
## Post #3
- Username: Bembee
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 01, 2023 4:51 pm
- Post datetime: 2023-08-08T14:27:35+00:00
- Post Title: [Answered] Edit Unity text file without UnityText?

> Reply from enarkay ↑Tue Aug 08, 2023 5:45 pm at Tue Aug 08, 2023 5:45 pm
>
> 
I've personally never worked on mobily game localization yet.
So while I can't be 100% sure, I'm guessing the big picture must be the same.
Judging from your attachment and pictures, do you have access to resources.assets?
Instead of extracting ~~~resources.assets-27.dat (raw format data), open resources.assets with UABEA, look for the asset you wish to edit, and export dump in either txt/json. You can edit the exported txt/json, and the insert it back with the import dump feature.

Thank you, the export dump (txt), modify the file and import dump works perfectly.
