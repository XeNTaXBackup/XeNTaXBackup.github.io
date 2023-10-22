## Post #1
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-10-24T09:22:40+00:00
- Post Title: Yakuza 4 Just Cause *.DDS file decompression

The contents of this post was deleted because of possible forum rules violation.
[Snap1.jpg](https://xentaxbackup.github.io/file/3551_Snap1.jpg)
## Post #2
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-10-26T05:09:37+00:00
- Post Title: Yakuza 4 Just Cause *.DDS file decompression

PS3のソフトは暗号化されているので、まずは復号化した状態でリッピングをする必要があります。(ググればヒントがあると思います)
１体のモデルは独自のアイカーブ形式でテクスチャと一緒に連結されLZSS系かと思われる圧縮がされていました。
見たところ一般的なLZSSではないと思います。
多分、圧縮フラグのビットを反転させれば行けそうな気がしますがやってみないとわかりません。
テクスチャはDDSファイルのようです。モデルはPS系標準フォーマット？のGMDフォーマットのようです。
あとはダンプエディタで16進数を眺め変換プログラムを書くと良いでしょう。
