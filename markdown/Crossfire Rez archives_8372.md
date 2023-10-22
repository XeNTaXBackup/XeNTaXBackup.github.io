## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T06:36:29+00:00
- Post Title: Crossfire Rez archives

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-22T19:06:20+00:00
- Post Title: Crossfire Rez archives

except for the first header the rest is changed.
for example where should be located the information table there is a small header probably encrypted (blowfish?)
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-24T20:42:28+00:00
- Post Title: Crossfire Rez archives

Try [CrossFire REZ Injector / Extractor](http://www.progamercity.net/game-files/2702-tool-crossfire-rez-injector-extractor.html)
## Post #4
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2012-02-25T04:09:16+00:00
- Post Title: Crossfire Rez archives

All info i have:
PHP extractor for LTB

```
function hexToStr($hex){ $string=''; for ($i=0; $i < strlen($hex)-1; $i+=2) { $string .= chr(hexdec($hex[$i].$hex[$i+1])); }return $string;}


$rez = file_get_contents("RF016.REZ"); // get the rez as a string

$ltbs = explode(hexTostr('0100090000000000'),$rez); //make an array containing the ltbs, its header is cut off, but we gonna fix that

foreach($ltbs as $k => $v) {
if($k==0) continue; //skip the first, its the rez header
$f = fopen("model_".$k.".ltb","a+"); //save as model_NUMBER
fwrite($f,hexTostr('0100090000000000 ').$v); //write the header + the ltb itself
fclose($f);
}
sleep(3000);
?>
```

(Tex)   dtx: 00000000FBFFFFFF
(Model) ltb: 0100090000000000
(Sound) wav: 52494646
(Map)   dat: the first "55000000" (I think, but when i try import to NOLF2 i got error report)

Name of file at the end of it in hex

Old List


Someone on MPGH already make Extractor for all CF rez (files have name "not same as model_01,..." i think), but he didn't released it
Import files to NOLF2
[http://www.mpgh.net/forum/194-crossfire ... r-2-d.html](http://www.mpgh.net/forum/194-crossfire-mods-rez-modding/386725-crossfire-maps-no-one-lives-forever-2-d.html)
