## Post #1
- Username: newby
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 14, 2010 7:51 pm
- Post datetime: 2021-12-15T08:36:45+00:00
- Post Title: Hatsune Miku: Colorful Stage (data obfuscation)

Hello guys,

I wanted to see if anyone would be willing to look at it at a Unity game for mobile phones named Hatsune Miku: Colorful Stage.
This is a Unity game, which would make it easy to extract. However, whilke the contents of the *.APK are fairly standard and are able to be extracted easily, the problem is with the downloaded data the game uses to add extra content.

The game can be downloaded for free at:

```
https://play.google.com/store/apps/details?id=com.sega.ColorfulStage.en
```


the data is in: 
```
/sdcard/Android/data/com.segaColorfulStage.en
```


and the data that are obfuscated are in: 
```
/sdcard/Android/data/com.segaColorfulStage.en/files/data/
```


I do not believe there is an encryption infolved, but rather some kind of obfuscation that is causing tools that can extract Unity archives to fail.
You can still see plain text in the files, but parts that should have a specific structure are with mangled characters.

The files are in easily accessible place, no root is required, therefore I won't upload any files here.

If you'll need any files in spite of that, I can of course provide them.

Thanks for help in advance!
