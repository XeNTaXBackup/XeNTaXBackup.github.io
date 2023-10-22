## Post #1
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-12-16T22:00:04+00:00
- Post Title: Unreal Engine 2 .UAX Converter

Took a couple hours to write this because umodel wasn't preserving folder paths. Requires extract.exe ([https://www.gildor.org/downloads](https://www.gildor.org/downloads)), quickbms.exe ([http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)), and Python 3.x.

ONLY TESTED WITH STOCK UE2 FILES - MAY NOT WORK WITH MODIFIED ENGINES

Instructions
1. Extract bin\ and UAX.py to a new folder
2. Copy extract.exe and quickbms.exe to the bin\ folder
3. Open UAX.py in a text editor and replace "uaxpath" with the path to the game's "Sounds" folder. Make sure to use double backslashes with two more at the end, as seen in the example.
4. Open cmd and enter "python UAX.py"
5. Wait for it to complete - this may take a while. When it's finished, the resulting .wav files can be found in the new workspace\ folder right next to UAX.py.
[UAX.7z](https://xentaxbackup.github.io/file/19199_UAX.7z)
