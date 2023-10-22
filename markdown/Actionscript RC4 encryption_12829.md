## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-05-09T20:45:02+00:00
- Post Title: Actionscript RC4 encryption

I'm looking at some actionscript code for decrypting resources:

```
{
    var _loc_7:IVMode = null;
    var _loc_2:* = URLLoader(event.target).data;
    this.url_loader.removeEventListener(Event.COMPLETE, this.URLLoaderCompleteFunc);
    this.url_loader.removeEventListener(ProgressEvent.PROGRESS, this.onProgress);
    var _loc_3:* = new NullPad();
    var _loc_4:String = "dmmidol";
    var _loc_5:* = Crypto.getCipher("rc4", Hex.toArray(_loc_4), _loc_3);
    if (Crypto.getCipher("rc4", Hex.toArray(_loc_4), _loc_3) is IVMode)
    {
        _loc_7 = _loc_5 as IVMode;
        _loc_7.IV = Hex.toArray(_loc_4);
    }
    _loc_5.decrypt(_loc_2);
    var _loc_6:* = new LoaderContext();
    new LoaderContext().allowCodeImport = true;
    _loc_6.applicationDomain = new ApplicationDomain();
    this.loader = new Loader();
    this.loader.contentLoaderInfo.addEventListener(Event.COMPLETE, this.onCompleteImag);
    this.loader.loadBytes(_loc_2, _loc_6);
    return;
}// end function

```


And it looks like just plain-old RC4 using the key "dmmidol"
However, whenever I run it through RC4, I don't get a valid image file.

Here's some ruby code

```

data = File.open("sample.dat", "rb").read
key = "dmmidol"
d = OpenSSL::Cipher::Cipher.new("rc4")
d.decrypt  
d.key_len = 7
d.key = key      
dec = d.update(data) + d.final
# this should be the decrypted data

```


Can anyone look at this and see if I'm missing something?
RC4 itself is straightforward, so maybe the application is doing something else to the data before sending it for decryption, or perhaps doing something after decryption to load the image.

Sample attached with original and my decrypted version.
If you get the same thing I'll probably have to look around some more in the code.
[sample.zip](https://xentaxbackup.github.io/file/9184_sample.zip)
