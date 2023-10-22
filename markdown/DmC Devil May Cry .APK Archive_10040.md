## Post #1
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-01-14T18:13:04+00:00
- Post Title: DmC: Devil May Cry .APK Archive

DmC has .apk Unreal Engine archives that I believe contain the audio assets. (RIFX so most likely OGG) Is there any way of extracting these archives so that the original file names extract with them like how .XXX's can be extracted? If anyone is interested in the APK archive, PM me.
## Post #2
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-01T01:05:45+00:00
- Post Title: DmC: Devil May Cry .APK Archive

Pretty simple format, so its strange no one made a script before. There is wwise .bnk files inside, that can be extracted with AlphaTwentyThree script and converted with ww2ogg.

```
# script for QuickBMS http://quickbms.aluigi.org

get FILES long
get DUMMY long
for i = 0 < FILES
    get ID long
    get OFFSET long
    get SIZE long
    set NAME ID
    string NAME p= "%08x" NAME
    string NAME += ".bnk"
    log NAME OFFSET SIZE
next i
```
