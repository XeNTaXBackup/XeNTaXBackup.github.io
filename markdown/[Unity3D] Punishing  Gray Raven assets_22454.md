## Post #1
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-07-27T06:16:24+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

Recently, this game's assets have been encrypted.
As far as I know, this game is made by unity3d (2018.4.23f1) and it is an Android mobile game.



It's 3D models and illustrations are really exquisite. I really want to rip its models from this game's assets but I came out fruitless after using AssetStudio, AssetsBundleExtractor, disunity etc..
I do hope someone nice can help me figure this out!!  
Thanks!!

And here are some samples from this game (2MB)
[https://mega.nz/folder/L0NCXJyJ#yqor70qVzlXs6trW-BoV3Q](https://mega.nz/folder/L0NCXJyJ#yqor70qVzlXs6trW-BoV3Q)
## Post #2
- Username: yibanshanlei
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 08, 2020 4:13 am
- Post datetime: 2020-08-07T22:43:50+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

Up, i need it
## Post #3
- Username: zhanghongming123
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Mar 16, 2019 1:01 pm
- Post datetime: 2020-08-20T06:53:25+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

Use this quickbms script batch process all assets.then AssetStudio will recognize them.

```
set Name string "new\\"
string Name + ArcName
get Size asize
math Size - 0x04
log Name 0x04 Size
```
## Post #4
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-08-22T01:27:29+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

> Reply from zhanghongming123 ↑Thu Aug 20, 2020 2:53 pm at Thu Aug 20, 2020 2:53 pm
>
> 
Use this quickbms script batch process all assets.then AssetStudio will recognize them.
Code: Select allget ArcName filename
set Name string "new\\"
string Name + ArcName
get Size asize
math Size - 0x04
log Name 0x04 Size

Thanks for your effort!
But it doesn't work on my part.
I think this script you made is mainly for this game's previous version. I know we can simply delete the "Kuro" before the "UnityFS" before.However, the latest version of this game has changed it encryption way and I totally got no clue of if 
and it seems quite complicated to decrypt since it's data is irregular and messing around.
Anyway, heartfeltly thanks for your replies!
## Post #5
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-09-03T17:25:21+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

The latest version I installed from taptap today was not encrypted.
It's neither a kuro header nor another encryption. It was a regular unity3d file.

By the way, the second-type encryption method seems to be same in "castlevania moonlight rhapsody".
Add 70 bytes of dummy data and rewrite random bytes. I have no idea on how it will be decrypted.
## Post #6
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-09-05T02:27:36+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

> Reply from einherjar007 ↑Fri Sep 04, 2020 1:25 am at Fri Sep 04, 2020 1:25 am
>
> 
The latest version I installed from taptap today was not encrypted.
It's neither a kuro header nor another encryption. It was a regular unity3d file.

By the way, the second-type encryption method seems to be same in "castlevania moonlight rhapsody".
Add 70 bytes of dummy data and rewrite random bytes. I have no idea on how it will be decrypted.

Yeah, I've asked some people specialized in decrypting Unity3d assets but they gave the same answer as yours--dummy and random bytes added.
But glad to know the game from taptap isn't encrypted and do hope that this game could be popular in the world! It's really a good game and the characters' skins as well as 2D portraits are fabulous
## Post #7
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-12-02T03:28:31+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

Up!
I wish someone could see this thread and it seems that there are some people have managed to extract the assets from this game already
## Post #8
- Username: yibanshanlei
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 08, 2020 4:13 am
- Post datetime: 2021-01-09T18:39:41+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

Well, up x2
## Post #9
- Username: librarykeep
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 12, 2019 12:05 am
- Post datetime: 2021-09-26T02:17:22+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

Up x3!
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-26T12:12:46+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

I've just tested it on version 1.9.1 of the game and all assets are unencrypted.
If you'll just remove "Kuro" word which is right before "UnityFS" signature, all files will be readable in Asset Studio or UnityEx.
[https://i.imgur.com/veXNC3j.png](https://i.imgur.com/veXNC3j.png)

But is the v1.9.1 the newest one? If not, then please specify which version of the game is encrypted.
Becasue on the google play site you can see that v1.9.1 is the newest, so I'm a little confused with your request.
[https://play.google.com/store/apps/deta ... n_US&gl=US](https://play.google.com/store/apps/details?id=com.kurogame.gplay.punishing.grayraven.en&hl=en_US&gl=US)
## Post #11
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2021-09-26T13:43:50+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Sun Sep 26, 2021 8:12 pm at Sun Sep 26, 2021 8:12 pm
>
> 
I've just tested it on version 1.9.1 of the game and all assets are unencrypted.
If you'll just remove "Kuro" word which is right before "UnityFS" signature, all files will be readable in Asset Studio or UnityEx.
https://i.imgur.com/veXNC3j.png

But is the v1.9.1 the newest one? If not, then please specify which version of the game is encrypted.
Becasue on the google play site you can see that v1.9.1 is the newest, so I'm a little confused with your request.
https://play.google.com/store/apps/deta ... n_US&gl=US

The global version hasn't been encrypted yet. That's because kuro just simply "copy paste" the files that they used in the CN server. 

[The following may contain spoilers]
And they didn't set complex encryption until the "Granblue version"(Swimsuit version). So before that ver, all files were able to be loaded in AssetStudio.
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-26T17:07:51+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

Ok, sure, can you tell me how can I get this "Granblue version" (or newer) to see encrypted assets?
## Post #13
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2021-09-26T17:37:13+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Mon Sep 27, 2021 1:07 am at Mon Sep 27, 2021 1:07 am
>
> 
Ok, sure, can you tell me how can I get this "Granblue version" (or newer) to see encrypted assets?

Here are some samples from this game (2MB)
[https://mega.nz/folder/L0NCXJyJ#yqor70qVzlXs6trW-BoV3Q](https://mega.nz/folder/L0NCXJyJ#yqor70qVzlXs6trW-BoV3Q)

Or you can download the whole game file here:
[https://punishing-gray-raven.ru.uptodow ... d/download](https://punishing-gray-raven.ru.uptodown.com/android/download)
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-26T18:06:02+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

Ok, thanks, this version for China you linked is v1.22.1, so I should see some differences now.
I'll try to check it.
## Post #15
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2021-09-27T00:51:29+00:00
- Post Title: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Mon Sep 27, 2021 2:06 am at Mon Sep 27, 2021 2:06 am
>
> 
Ok, thanks, this version for China you linked is v1.22.1, so I should see some differences now.
I'll try to check it.

Thanks for that! Looking forward to your reply!:mrgreen:
## Post #16
- Username: quang23021998
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 22, 2020 4:53 am
- Post datetime: 2021-10-12T02:18:57+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

Upx4!
## Post #17
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-12T06:51:00+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from quang23021998 ↑Tue Oct 12, 2021 10:18 am at Tue Oct 12, 2021 10:18 am
>
> Upx4!

Well, the thing is that v1.23 is available only for China. And if you don't have real chineese name and identification number, you are not even able to play this game. I think that you guys should just wait to global version update to v1.23. Then it will be possible to check this game without issues.
## Post #18
- Username: quang23021998
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 22, 2020 4:53 am
- Post datetime: 2021-10-12T21:39:01+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Tue Oct 12, 2021 2:51 pm at Tue Oct 12, 2021 2:51 pm
>
> 
quang23021998 wrote: ↑Tue Oct 12, 2021 10:18 amUpx4!

Well, the thing is that v1.23 is available only for China. And if you don't have real chineese name and identification number, you are not even able to play this game. I think that you guys should just wait to global version update to v1.23. Then it will be possible to check this game without issues.

Thank you for the reply! For this problem, I can provide the full source file of v1.22 + all downloaded content if this is possible for the research.
## Post #19
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-13T06:56:58+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> I can provide the full source file of v1.22 + all downloaded content
Thanks, but it's not needed. We already have some samples in this topic and the APK can be downloaded from bilibili or other similar sites.
## Post #20
- Username: ravioxentax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 01, 2016 5:47 pm
- Post datetime: 2021-11-21T06:35:38+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Thank you for the reply! For this problem, I can provide the full source file of v1.22 + all downloaded content if this is possible for the research.
On my side I want you to share these files if possible !  Impossible to extract them on the latest version...
## Post #21
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-21T11:48:38+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> I want you to share these files if possible !
Sharing assets is forbidden on this forum.
## Post #22
- Username: tachiban
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 18, 2021 2:09 pm
- Post datetime: 2021-12-16T04:15:58+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Sun Nov 21, 2021 7:48 pm at Sun Nov 21, 2021 7:48 pm
>
> 
I want you to share these files if possible !
Sharing assets is forbidden on this forum.
Excuse me, have you solved it?
## Post #23
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-12-16T05:40:56+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

Recently, more and more games use the same encryption as this game.
The function seems to use AssetBundleEncryptStream.
I don't know the offset and key information, but it's definitely an XOR with certain rules.
It is presumed that the data added to the header is probably dummy and not used to generate the key.
## Post #24
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-16T09:05:48+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

@tachiban, no, chineese client is not available for me as I'm not from China.
Just wait for the global client update or ask someone who has passed chineese ID verification.
## Post #25
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2021-12-16T12:24:14+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from einherjar007 ↑Thu Dec 16, 2021 1:40 pm at Thu Dec 16, 2021 1:40 pm
>
> 
Recently, more and more games use the same encryption as this game.
The function seems to use AssetBundleEncryptStream.
I don't know the offset and key information, but it's definitely an XOR with certain rules.
It is presumed that the data added to the header is probably dummy and not used to generate the key.

They change the way of encryption as time goes by. Former versions of this game's assets can be dumped by using Gameguardian and other tools. However, it DOESN'T WORK for the current version now.  
They transfer the code C# to C++ in order to obfuscate the data.
(I don't know much about it. I get the information from a chinese blog and he said by using Gameguardian can dump the source assets, somehow bypass the encryption, and export a file called libil2cpp.so.

[](https://ibb.co/TMXQM3B)

Then use Il2CppDumper to have access to the metadata in the original C#'s il code(Intermediate Language).
Use dnspy to open Assembly-CSharp.dll to search for the key to the encryption.

[](https://ibb.co/ChwWj5n)

Use IDA(Interactive Disassembler Professional) to open the exported libil2cpp.so mentioned above and locate 

[](https://ibb.co/XDRbJmr), which seems to be an algorithm for decryption.

Compile the following code in unity:

```
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;
using UnityEditor;
using System.IO;
using System;

public class MainBehaviourScript : MonoBehaviour
{
    Text listText;
    Text matrixPath;
    Text configPath;
    private Texture2D duplicateTexture(Texture2D source)
    {
        RenderTexture renderTex = RenderTexture.GetTemporary(
                    source.width,
                    source.height,
                    0,
                    RenderTextureFormat.Default,
                    RenderTextureReadWrite.Linear);

        Graphics.Blit(source, renderTex);
        RenderTexture previous = RenderTexture.active;
        RenderTexture.active = renderTex;
        Texture2D readableText = new Texture2D(source.width, source.height);
        readableText.ReadPixels(new Rect(0, 0, renderTex.width, renderTex.height), 0, 0);
        readableText.Apply();
        RenderTexture.active = previous;
        RenderTexture.ReleaseTemporary(renderTex);
        return readableText;
    }
    // Start is called before the first frame update
    void Start()
    {
        //listText = GameObject.Find("Canvas/Panel/Text").GetComponent<Text>();
        matrixPath = GameObject.Find("Canvas/matrixPath").GetComponent<Text>();
        configPath = GameObject.Find("Canvas/configPath").GetComponent<Text>();
    }

    public void OnClick1()
    {
        configPath.text = MyLocalDialog.GetDir().Trim('\0');
    }

    public void OnClick2()
    {
        matrixPath.text = MyLocalDialog.GetDir().Trim('\0');
    }

    public void OnClick3()
    {
        AssetBundle.SetAssetBundleDecryptKey("kurokurokurokuro");
        FileStream newfst = new FileStream(configPath.text + "\\newoutfile.txt", FileMode.Create, FileAccess.Write);
        FileStream allfst = new FileStream(configPath.text + "\\alloutfile.txt", FileMode.OpenOrCreate, FileAccess.ReadWrite);
        StreamWriter newfWriter = new StreamWriter(newfst);
        StreamWriter allfWriter = new StreamWriter(allfst);
        StreamReader allfReader = new StreamReader(allfst);
        Dictionary<string, int> myDictionary = new Dictionary<string, int>();
        DirectoryInfo TheFolder = new DirectoryInfo(matrixPath.text);
        string outdir = MyLocalDialog.GetDir().Trim('\0') + "\\";
        if (outdir == "")
            return;
        //istText.text = "";
        string str;
        bool outtext = GameObject.Find("Canvas/TextToggle").GetComponent<Toggle>().isOn;
        bool outpic = GameObject.Find("Canvas/PicToggle").GetComponent<Toggle>().isOn;
        while ((str = allfReader.ReadLine()) != null)
        {
            myDictionary.Add(str, 1);
        }
        foreach (FileInfo NextFile in TheFolder.GetFiles())
        {
            MyLocalDialog.MessageBox((IntPtr)0, NextFile.ToString(), "提示", 0);
            var ab = AssetBundle.LoadFromFile(NextFile.ToString());
            Debug.LogError(ab);
            string[] patht = ab.GetAllAssetNames();
            MyLocalDialog.MessageBox((IntPtr)0, patht[0], "提示", 0);
            return;
            foreach (string s in patht)
            {
                if (!myDictionary.ContainsKey(s))
                {
                    var o = ab.LoadAsset(s);
                    if (o == null)
                        continue;
                    if (outpic && o.GetType() == typeof(Texture2D))
                    {
                        Texture2D tx = (Texture2D)o;
                        Texture2D readableText = duplicateTexture(tx);
                        string file_path = outdir + s;
                        int len = file_path.Length - 1;
                        while (len > 0 && file_path[len] != '/')
                            len--;
                        Directory.CreateDirectory(file_path.Substring(0, len));

                        byte[] filedata = readableText.EncodeToPNG();
                        using (var fs = new FileStream(file_path, FileMode.Create, FileAccess.Write))
                        {
                            fs.Write(filedata, 0, filedata.Length);
                        }
                        newfWriter.WriteLine(s);
                        allfWriter.WriteLine(s);
                    }
                    else if (outtext && o.GetType() == typeof(TextAsset))
                    {
                        TextAsset ta = (TextAsset)o;
                        string file_path = outdir + s;
                        int len = file_path.Length - 1;
                        while (len > 0 && file_path[len] != '/')
                            len--;
                        Directory.CreateDirectory(file_path.Substring(0, len));
                        using (var fs = new FileStream(file_path, FileMode.Create, FileAccess.Write))
                        {
                            fs.Write(ta.bytes, 0, ta.bytes.Length);
                        }
                        newfWriter.WriteLine(s);
                        allfWriter.WriteLine(s);
                    }
                }
            }
        }
        newfWriter.Close();
        newfst.Close();
        allfWriter.Close();
        allfReader.Close();
        allfst.Close();
        MyLocalDialog.MessageBox((IntPtr)0, "导出完成！", "提示", 0);
    }

    public void OnClick4()
    {
        AssetBundle.SetAssetBundleDecryptKey("kurokurokurokuro");
        var ab = AssetBundle.LoadFromFile("E:\\matrix2\\fff6ce1e25b48a043aa026247cbb231fbd2f225c");
        //string[] patht = ab.GetAllAssetNames();
        //Debug.LogError(patht[0]);
        var o = ab.LoadAsset("assets/product/scene/sceneres/common/scene020/textures/2003.png");
        MyLocalDialog.MessageBox((IntPtr)0, o.name, "提示", 0);
    }
    // Update is called once per frame
    void Update()
    {

    }
}
```


And voila, here comes the result:

[](https://ibb.co/9wRyckh)
(The original blog owner’s here[https://my.oschina.net/u/4363636/blog/5269405](https://my.oschina.net/u/4363636/blog/5269405))
## Post #26
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2021-12-16T12:54:52+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Thu Dec 16, 2021 5:05 pm at Thu Dec 16, 2021 5:05 pm
>
> 
@tachiban, no, chineese client is not available for me as I'm not from China.
Just wait for the global client update or ask someone who has passed chineese ID verification.

Maybe you can try to take a look at the jp version of this game? I think they use the same way of encryption now.
## Post #27
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-12-16T13:29:54+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

This is the first time I learned that there is a function called SetAssetBundleEncryptKey, and its set of functions.
I think it's probably an option when building AssetBundle. I'm not sure if that is supported by all Unity Editors, as it only gives information in Chinese.

*EDIT
There seems to be something called "Unity中国增强版". This may be a unique feature of this editor.

Recently, services such as virbox that make analysis difficult by obfuscation instead of encryption are increasing,
so it is less likely that will get code that can be analyzed even by dumping.
## Post #28
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-12-18T05:33:50+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

*EDIT
SetAssetBundleEncryptKey, Apparently this is not a feature for decryption. Chinese Unity loads the encrypted file as is.
## Post #29
- Username: lfanguest
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 20, 2021 4:00 pm
- Post datetime: 2021-12-20T08:30:24+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Sun Sep 26, 2021 8:12 pm at Sun Sep 26, 2021 8:12 pm
>
> 
I've just tested it on version 1.9.1 of the game and all assets are unencrypted.
If you'll just remove "Kuro" word which is right before "UnityFS" signature, all files will be readable in Asset Studio or UnityEx.
https://i.imgur.com/veXNC3j.png

But is the v1.9.1 the newest one? If not, then please specify which version of the game is encrypted.
Becasue on the google play site you can see that v1.9.1 is the newest, so I'm a little confused with your request.
https://play.google.com/store/apps/deta ... n_US&gl=US
May I ask how to delete the "Kuro" before the signature of "UnityFS"?
## Post #30
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-20T10:37:28+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from lfanguest ↑Mon Dec 20, 2021 4:30 pm at Mon Dec 20, 2021 4:30 pm
>
> 
May I ask how to delete the "Kuro" before the signature of "UnityFS"?

1. Download hex workshop [http://www.bpsoft.com/downloads/](http://www.bpsoft.com/downloads/)
2. Open unity3d file in hex workshop
3. Select "Kuro" word
4. Right click and choose "Delete"
5. Save the file
## Post #31
- Username: lfanguest
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 20, 2021 4:00 pm
- Post datetime: 2021-12-20T16:00:18+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Mon Dec 20, 2021 6:37 pm at Mon Dec 20, 2021 6:37 pm
>
> 
lfanguest wrote: ↑Mon Dec 20, 2021 4:30 pm
May I ask how to delete the "Kuro" before the signature of "UnityFS"?


1. Download hex workshop http://www.bpsoft.com/downloads/
2. Open unity3d file in hex workshop
3. Select "Kuro" word
4. Right click and choose "Delete"
5. Save the file
Ok, thank you.
## Post #32
- Username: zecknor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 28, 2021 5:13 pm
- Post datetime: 2021-12-28T09:14:18+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

Anyone able to find the Mesh for the characters? They seem to be missing from my files when looking with AssetstudioGUI.
## Post #33
- Username: NeferneferOttom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 07, 2022 11:42 am
- Post datetime: 2022-01-07T04:09:43+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

Is there still a way to extract the Chinese version now, the global version is too low, I can hardly find any information on the Chinese website because it is all blocked by kuro
## Post #34
- Username: SCArkadia
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 7:50 am
- Post datetime: 2022-05-10T13:32:27+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

So as of today, is the game not extractable anymore? Not decryptable?
## Post #35
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-05-11T02:33:33+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from SCArkadia ↑Tue May 10, 2022 9:32 pm at Tue May 10, 2022 9:32 pm
>
> 
So as of today, is the game not extractable anymore? Not decryptable?

Nope. It's still encrypted and kuro keeps changing its way to encryption
## Post #36
- Username: SCArkadia
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 7:50 am
- Post datetime: 2022-05-13T14:19:38+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from Kanbara ↑Wed May 11, 2022 10:33 am at Wed May 11, 2022 10:33 am
>
> 
SCArkadia wrote: ↑Tue May 10, 2022 9:32 pm
So as of today, is the game not extractable anymore? Not decryptable?


Nope. It's still encrypted and kuro keeps changing its way to encryption

Awww, too bad. I kinda love the model and animation.
## Post #37
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2022-05-14T07:55:03+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

just give up, china developer like KURO and miyoho keep their eyes on forum like this and will change their encrypt key EVERY update
## Post #38
- Username: hunshimowangzhy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 04, 2019 4:53 am
- Post datetime: 2022-05-18T05:19:15+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

Recently I was trying to learn some reverse engineering stuff as more and more games are encrypting their data, and it turns out the encryption method is fairly straitforward for this one.  There are special encryption funtions in the chinese version of unity. You can get the editor by downloading the chinese version of unity hub on the chinese official website. Both the hub and editor has the suffix "c1" appended to the version number. In unity write your own c# script and call AssetBundle.SetAssetBundleDecryptKey("") with the 16 byte key before you load the assetbundles. I am not providing the key here just in case some passerby decided to do stupid things with these assets that angers the developers and provokes them to change the encryption method again (this acutually happened weeks after the initial release of the game). Prove that you are clever enough by dumping the game library and figuring out the key your self. After getting the key you can use AssetBundle.RecompressAssetBundleAsync to decrypt the bundle and load it into assetstudio, or do whatever you like. Currently this method works for all versions of this game, including the latest chinese version.
## Post #39
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-05-18T06:24:21+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from hunshimowangzhy ↑Wed May 18, 2022 1:19 pm at Wed May 18, 2022 1:19 pm
>
> 
Recently I was trying to learn some reverse engineering stuff as more and more games are encrypting their data, and it turns out the encryption method is fairly straitforward for this one.  There are special encryption funtions in the chinese version of unity. You can get the editor by downloading the chinese version of unity hub on the chinese official website. Both the hub and editor has the suffix "c1" appended to the version number. In unity write your own c# script and call AssetBundle.SetAssetBundleDecryptKey("") with the 16 byte key before you load the assetbundles. I am not providing the key here just in case some passerby decided to do stupid things with these assets that angers the developers and provokes them to change the encryption method again (this acutually happened weeks after the initial release of the game). Prove that you are clever enough by dumping the game library and figuring out the key your self. After getting the key you can use AssetBundle.RecompressAssetBundleAsync to decrypt the bundle and load it into assetstudio, or do whatever you like. Currently this method works for all versions of this game, including the latest chinese version.
Thank you for the information on "AssetBundle.RecompressAssetBundleAsync".
I didn't know about it. It certainly works. The method seems to be uncompressed stable.
Until I knew it, I was calling the prefab and getting the clip from the array. Now all we have to do is run the script.
## Post #40
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-05-22T17:53:41+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from hunshimowangzhy ↑Wed May 18, 2022 1:19 pm at Wed May 18, 2022 1:19 pm
>
> 
https://i.imgur.com/Udt4gxb.png
https://i.imgur.com/7AbY6IO.png

How can you manage to get the bone/skeleton of them? I only find their mesh files. 
I rummage all the files only to find no Animator files for the correspondent characters  
What I see are just some mesh files' names that end with VC.
It's quite weird that the old characters's Animator file are stored together with their textures and meshes, but the newer ones seem to be separated into several files (I guess)?
I use the latest build of Assetstudio v0.16.40,btw.

[](https://ibb.co/8zXh7DW)
[](https://ibb.co/vYbxwpC)
## Post #41
- Username: hunshimowangzhy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 04, 2019 4:53 am
- Post datetime: 2022-05-25T03:23:19+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

First make sure you have downloaded all the game asset. Most of the assets are in sdcard/android/data, but there are also quiet some files in the apk file in /data/app for the chinese version, and a ~2gb obb file in sdcard/android/obb for global versions. The obb file is actually a bunch of zip file stacking together and you need to write a script to split the obb into zip files based on the zip header signature. After combining those files you should be able to get the complete game asset.
## Post #42
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-05-25T13:37:38+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from hunshimowangzhy ↑Wed May 25, 2022 11:23 am at Wed May 25, 2022 11:23 am
>
> 
First make sure you have downloaded all the game asset. Most of the assets are in sdcard/android/data, but there are also quiet some files in the apk file in /data/app for the chinese version, and a ~2gb obb file in sdcard/android/obb for global versions. The obb file is actually a bunch of zip file stacking together and you need to write a script to split the obb into zip files based on the zip header signature. After combining those files you should be able to get the complete game asset.

Oh, I see.I forget the assets in the apk.
Thanks!!
## Post #43
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-07-10T16:42:49+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Mon Dec 20, 2021 6:37 pm at Mon Dec 20, 2021 6:37 pm
>
> 

May I ask is it possible to decrypt the audio files from this game, for some they seldom release the background music from this game.I find it also encrypted as well since foobar2000 and VGMToolBox are fail to recognize neither the .acb nor .awb format.
It seems that I need to get the .hcakey or something like that so as to make it readable by foobar? 
But I have not an inkling of decoding TBH  

Here are some samples of the .acb and .awb files. It would be great if you can take a look at them!  
[https://mega.nz/folder/gPJDRJqK#GWREFN3Kzjlo1WHgf0ffxA](https://mega.nz/folder/gPJDRJqK#GWREFN3Kzjlo1WHgf0ffxA)
## Post #44
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-10T17:44:42+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> It would be great if you can take a look at them!

I would love to help, but unfortunately I don't know the correct hca key for your samples.
## Post #45
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-07-12T01:57:58+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from ikskoks ↑Mon Jul 11, 2022 1:44 am at Mon Jul 11, 2022 1:44 am
>
> 
It would be great if you can take a look at them!

I would love to help, but unfortunately I don't know the correct hca key for your samples.

I see..Thanks for your answer!
## Post #46
- Username: NeferneferOttom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 07, 2022 11:42 am
- Post datetime: 2022-09-29T13:48:53+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

Github search "Razmoth",he made a tool,I successfully extracted TW version
## Post #47
- Username: KlausSh
- Rank: beginner
- Number of posts: 25
- Joined date: Fri May 06, 2022 12:08 am
- Post datetime: 2022-10-03T22:28:13+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

I'm trying to extract the audio files but they exist in assest.splitXX files and dunno how to merge them ... anyone got a solution ?
## Post #48
- Username: KlausSh
- Rank: beginner
- Number of posts: 25
- Joined date: Fri May 06, 2022 12:08 am
- Post datetime: 2022-10-03T22:42:42+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from Kanbara ↑Mon Jul 11, 2022 12:42 am at Mon Jul 11, 2022 12:42 am
>
> 
ikskoks wrote: ↑Mon Dec 20, 2021 6:37 pm


May I ask is it possible to decrypt the audio files from this game, for some they seldom release the background music from this game.I find it also encrypted as well since foobar2000 and VGMToolBox are fail to recognize neither the .acb nor .awb format.
It seems that I need to get the .hcakey or something like that so as to make it readable by foobar? 
But I have not an inkling of decoding TBH  

Here are some samples of the .acb and .awb files. It would be great if you can take a look at them!  
https://mega.nz/folder/gPJDRJqK#GWREFN3Kzjlo1WHgf0ffxA

Couldn't even extract those. Mind telling me what script or method you used ?
## Post #49
- Username: Xodd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 06, 2023 3:39 pm
- Post datetime: 2023-03-06T07:51:45+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from Kanbara ↑Mon Jul 11, 2022 12:42 am at Mon Jul 11, 2022 12:42 am
>
> 
ikskoks wrote: ↑Mon Dec 20, 2021 6:37 pm


May I ask is it possible to decrypt the audio files from this game, for some they seldom release the background music from this game.I find it also encrypted as well since foobar2000 and VGMToolBox are fail to recognize neither the .acb nor .awb format.
It seems that I need to get the .hcakey or something like that so as to make it readable by foobar? 
But I have not an inkling of decoding TBH  

Here are some samples of the .acb and .awb files. It would be great if you can take a look at them!  
https://mega.nz/folder/gPJDRJqK#GWREFN3Kzjlo1WHgf0ffxA
on some recent version i forgot which it was 62855594017927612 u can use foo_input_vgmstream in foobar just create binary file called .hcakey with the hex of that key 00DF4ED46995B1BC then save after that u can drop both key and file in same folder and foobar can play them directly
## Post #50
- Username: junyi163
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 27, 2023 1:35 am
- Post datetime: 2023-07-26T17:40:57+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

how to unpack
## Post #51
- Username: ruka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 03, 2023 8:10 am
- Post datetime: 2023-09-16T02:52:35+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

Can you help me after decrypting the game file, deleting Kuro, putting the file in assetstudio and identifying it? assetstudio decrypts the shader files incorrectly and Unity gives an error message with the shader code. What is the solution? Can someone extract the shader file for me and I can run it with Unity without any errors? I left the shader file after deleting Kuro, so someone can come and help me, please
________________________________
[https://drive.proton.me/urls/G9WGA0QDPW#KRwOHCIp7JlQ](https://drive.proton.me/urls/G9WGA0QDPW#KRwOHCIp7JlQ)
## Post #52
- Username: rubik
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 13, 2023 11:04 pm
- Post datetime: 2023-09-16T11:48:19+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

> Reply from ruka ↑Sat Sep 16, 2023 10:52 am at Sat Sep 16, 2023 10:52 am
>
> 

How to decrypt the game file? I downloaded the latest official PC emulator version, but my assetstudio cannot read the original game files correctly.
## Post #53
- Username: hunterxoar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 08, 2022 6:27 pm
- Post datetime: 2023-10-09T12:11:26+00:00
- Post Title: Re: [Unity3D] Punishing : Gray Raven assets

I don’t care for the 3D assets or whatever, I just want the character sprites for fanfiction purposes. How would I go about getting those?
