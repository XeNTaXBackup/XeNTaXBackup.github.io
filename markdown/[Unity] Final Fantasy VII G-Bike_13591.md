## Post #1
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2015-11-29T03:51:02+00:00
- Post Title: [Unity] Final Fantasy VII G-Bike

I know it's late now and they will shut down their server soon so I need your help. I'll explain everything I have with this game so far.
Radigar found the apis, methods the game used. You can find methods in Assembly-CSharp.dll with [http://dotnetresolver.eu5.org/](http://dotnetresolver.eu5.org/)

Example: bike_001_001 Hardy Daytona
[http://app.static.finalfantasy7-gbike.c ... f635f521a9](http://app.static.finalfantasy7-gbike.com/Android/dfa65b58f78561bfcae620f635f521a9)
"[http://app.static.finalfantasy7-gbike.com/Android/](http://app.static.finalfantasy7-gbike.com/Android/)" is the api
"dfa65b58f78561bfcae620f635f521a9" is the md5hash of file name
The method that create md5hash in Assembly-CSharp.dll->Rebirth1.Sys->cWWW(GetUrl, Encode, AddAppVer)
I think file name is "b001001" and extension is "unity3d", but when I try encrypt it with md5 it look different.

I play almost all of events and I think there still lots of models they still not put on events. Here is the list I found in .dll:
Assist: Tifa, Aerith, Cid, Yuffie, Barrett, Vincent, CaitSith, Red13, Zack
Boss: ShinraSoldier, WutaiSoldier, GeneralTank, Bomb, GuardScorpion, Behemoth, JumboCactuer, Ifrit, Bahamut, Reno, Sephiroth, Griffin, Garuda, DualHorn, BahamutFury, Dyne, LandWorm, Phoenix, Odin, Fenrir, Jormungand, Leviathan, Shiva, ProudClod, GuardSpider
Bike: 63 bikes
Enemy: 88 enemies
Weapon: 63 weapons
Map: 24 maps

I got Tifa, Cid, Yuffie, Barrett, ShinraSoldier, WutaiSoldier, GeneralTank, Bomb, GuardScorpion, Behemoth, Ifrit, Bahamut, Reno, Griffin, Garuda, DualHorn, BahamutFury, Dyne, Phoenix, Shiva, GuardSpider, about 1/2 bikes and 1/2 weapons in cache after played the game.

The problem right now is that we need to decrypt the "dfa65b58f78561bfcae620f635f521a9" md5hash to plain text to see what it look like then encrypt plain text back to md5hash and download the file from server. Or hacking the api server to get all files  
[datagbike.zip](https://xentaxbackup.github.io/file/10085_datagbike.zip)
## Post #2
- Username: Radigar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 02, 2015 2:37 am
- Post datetime: 2015-11-29T11:24:19+00:00
- Post Title: [Unity] Final Fantasy VII G-Bike

This is a challenge time trial I hope you can help with this  , a lot of unused models are waiting for discover it on the server.
## Post #3
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2015-11-29T23:41:51+00:00
- Post Title: [Unity] Final Fantasy VII G-Bike

Your MD5 won't look correct unless you know what the hash represents.

You can MD5 the file contents to get one hash, and MD5 the name of the file to get another.
The hash might be salted with a string, which would alter the resulting hash.

Lastly, the file hashes may not even be MD5's. The game may be hashed with a custom algorithm.

I would start by running all variations of the character names, partial character names, names with numbers and underscores, and potentially, kana names through the MD5 algorithm and see if anything matches any file you already have.

If you find something that does, look at the pattern and try to copy it with other names.

EDIT: Looking again, I notice the argument AddAppVer in the hash function you listed.
This likely means that the game's full version number (likely at the time of first inclusion) is added to the hash in some way. Its hard to tell just now what it's doing to this information. 
I'm still trying to read the file.
## Post #4
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2015-12-04T02:08:20+00:00
- Post Title: [Unity] Final Fantasy VII G-Bike

```
{
    uint num1;
    RuntimePlatform platform1;
    string str1;
    string str2;
    if (name.Contains("."))
    {
        str1 = name;
        goto Label_0023;
    }
    else
    {
        str1 = Path.ChangeExtension(name, ".unity3d");
        Label_0023:
    }
    if (!cDebugSetting.IsDownload(name))
    {
        str2 = ((Application.streamingAssetsPath + "/") + cWWW.Encode(str1));
        platform1 = Application.platform;
        switch ((platform1 - 7))
        {
            case 2:
            case 3:
                if ((platform1 != null))
                {
                    goto Label_009D;
                
            }
            case 1:
                else
                {
                    url = ("file://localhost" + str2);
                    goto Label_009D;
                
                case 4:
                    url = str2;
                    goto Label_009D;
                }
            
            url = ("file://" + str2);
            goto Label_009D;
            Label_009D:
        }
        goto Label_00C7;
    }
    else
    {
        num1 = ((uint)cVersion.GetVersion(name));
        url = ((url + cWWW.Encode(str1)) + string.Format("?{0:0000000000}", num1));
        Label_00C7:
    }
    return url;
}

```


```
{
    int num1;
    string str1;
    if ((cVersion.s_assetBundleList != null))
    {
        abName = Path.ChangeExtension(abName, ".unity3d");
        str1 = cVersion.encode(abName);
        if (cVersion.s_assetBundleList.TryGetValue(str1, &num1))
        {
            return num1;
        }
    }
    Logger.warning((("GetVersion(" + abName) + ") missing"));
    return 1;
}

```


```
{
    string str1;
    string str2;
    str1 = Path.GetExtension(fileName);
    str2 = Path.GetFileNameWithoutExtension(fileName);
    str2 = cWWW.AddAppVer(str2);
    fileName = (str2 + str1);
    return cMd5.get(fileName);
}

```


```
{
    Dictionary<string, int> dictionary1;
    int num1;
    string str1;
    str1 = fname;
    if ((str1 != null))
    {
        if ((cWWW.<>f__switch$mapB == null))
        {
            dictionary1 = new Dictionary<string, int>(2);
            dictionary1.Add("Resident", 0);
            dictionary1.Add("Common", 0);
            cWWW.<>f__switch$mapB = dictionary1;
        }
        if (cWWW.<>f__switch$mapB.TryGetValue(str1, &num1))
        {
            if ((num1 != null))
            {
                goto Label_0070;
            }
            else
            {
                fname = string.Format("{0}_{1}", fname, GameConfig.Version());
                goto Label_0075;
                Label_0070:
            }
        }
    }
    else
    {
        goto Label_0075;
        Label_0075:
    }
    return fname;
}

```


```
{
    GameConfig.App_Version = 20000;
    GameConfig.Cipher_Mode = CipherMode.ECB;
    GameConfig.Cipher_Key = "keycloudcreative";
    GameConfig.Cipher_Key_Size = 128;
    GameConfig.Cipher_Block_Size = 128;
    GameConfig.Db_Auth_Key = "0xtLTbnSyqis4105x8gD88CWqFKwr1Yzqe";
    GameConfig.Game_Server_Url = "http://app.finalfantasy7-gbike.com/api";
    GameConfig.PartyTrack_Id_Name = 18362;
    GameConfig.PartyTrack_Id_Tutorial = 18346;
    GameConfig.PartyTrack_Id_FirstPayment = 18363;
    GameConfig.PartyTrack_Id_Login = 18364;
    GameConfig.PartyTrack_Id_Share = 36358;
    GameConfig.PartyTrack_Id_Invite = 36359;
}

```


```
public static string get(string srcStr)
{
    Encoding encoding1;
    byte[] numArray1;
    byte[] numArray2;
    MD5CryptoServiceProvider provider1;
    string str1;
    encoding1 = Encoding.GetEncoding("UTF-8");
    numArray1 = encoding1.GetBytes(srcStr);
    provider1 = new MD5CryptoServiceProvider();
    numArray2 = provider1.ComputeHash(numArray1);
    str1 = BitConverter.ToString(numArray2);
    str1 = str1.Replace("-", string.Empty);
    return str1.ToLower();
}

```


I guess fileName_APPVERSIONunity3d so may be b001001_20000unity3d
App version always change after update so I don't think it would be 20000(2.0.0). It must be static since the old file name still can be download
## Post #5
- Username: Aussieroth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 30, 2017 1:20 pm
- Post datetime: 2017-11-30T06:02:24+00:00
- Post Title: [Unity] Final Fantasy VII G-Bike

So did anyone manage to rip the models of the characters, weapons and all that or have they been lost to the ages?
## Post #6
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2017-12-01T22:10:29+00:00
- Post Title: [Unity] Final Fantasy VII G-Bike

> Reply from Aussieroth
>
> So did anyone manage to rip the models of the characters, weapons and all that or have they been lost to the ages?
I've saved some cache files from the ios version. But what are they for?
## Post #7
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2017-12-02T07:34:57+00:00
- Post Title: [Unity] Final Fantasy VII G-Bike

Ooh.. if you have cache files would you be willing to share.. I was a bit late to the game and only got the last few files.
Id like to extract the models and port them to xnalara like ive done with some of the others. I'd also like to use them to make an sfm movie of ff7 vs ff8
## Post #8
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2017-12-02T08:57:46+00:00
- Post Title: [Unity] Final Fantasy VII G-Bike

[https://yadi.sk/d/KrBlA-t83QFAeT](https://yadi.sk/d/KrBlA-t83QFAeT)
