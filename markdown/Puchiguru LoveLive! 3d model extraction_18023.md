## Post #1
- Username: west61224
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 10, 2018 10:44 am
- Post datetime: 2018-04-25T01:00:12+00:00
- Post Title: Puchiguru LoveLive! 3d model extraction

Hello, I’am trying to extract the models from this game ([https://play.google.com/store/apps/deta ... .puchiguru](https://play.google.com/store/apps/details?id=jp.co.pokelabo.puchiguru)) , and I think I’ve made some progress
Fist I downloaded the app on nox player
I started the game while capturing the traffic with the Packet capture app for some reason I can’t get past the start screen with the app capturing packets I disabled it only to get pass the start screen. While a video is playing I activate it again and let it download all data

I checked packet capture and got this



I clicked the 39MB one and I got this



That’s a request and a response is far as I know after the first response I got this one


And this looks like and unity asset file I saved it as a *.unity3d file to open in unity studio and I got this. Not a 3d model but is something



Packet capture let me save the entire conversation (requests and responses) as *.pcap file so I downloaded wireshark, opened the file and try to save it as raw but I don’t really know how to use wireshark and I got here



In theory I can save the received data as raw but it saves either the full conversation or all responses together.
So if someone with more knowledge in this can help me to save every response individually in an efficient way (the packet capture app method is one by one) in wire shark or use another technique to get the models it would be great.

Notes: -I got the game from QooApp searching for pokelabo
-The apps for capturing packets is called packet capture avalible in the play store
-I tried with fiddler 4 but it gave me a 403 forbidden error, maybe I’m creating the request in a wrong way

Thanks in advance and sorry for my broken English.
## Post #2
- Username: west61224
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 10, 2018 10:44 am
- Post datetime: 2018-04-25T16:56:52+00:00
- Post Title: Puchiguru LoveLive! 3d model extraction

I’m back and found that the models are downloaded when you get them in the gotcha it was tricky because the app don’t allow some things (scouting and login in) while pakect capture is capturing packages, but I was fast activating and deactivating the app and get this model it has all the textures including the multiple faces, this is a progress but that means that I have to get a character to get its model



Here is the request for this model

```
X-Unity-Version: 5.6.2f1
User-Agent: Dalvik/1.6.0 (Linux; U; Android 4.4.2; SM-G930K Build/NRD90M)
Host: puchiguru-prod-static-files.pokelabo.jp
Connection: Keep-Alive
Accept-Encoding: gzip

```


The first response 


```
x-amz-id-2: YeRrprS34qUMUxJ1VRXX97hHN9T2fJRrIgB0dOC4foFKJ73XZhuTx0wgFWcIm1Y6wtBBKjkF2VQ=
x-amz-request-id: 4276F097E071BB53
Last-Modified: Sun, 01 Apr 2018 03:44:22 GMT
ETag: "0713ead7ed566f025fb9bba468de0b29"
Accept-Ranges: bytes
Content-Type: binary/octet-stream
Content-Length: 333316
Server: AmazonS3
Date: Wed, 25 Apr 2018 04:20:01 GMT
Connection: keep-alive

```


And the second one the actual model (just the start because it too long)




But searching in the other responses in the initial download I found this  

```
X-Unity-Version: 5.6.2f1
User-Agent: Dalvik/1.6.0 (Linux; U; Android 4.4.2; SM-G930K Build/NRD90M)
Host: puchiguru-prod-static-files.pokelabo.jp
Connection: Keep-Alive
Accept-Encoding: gzip

HTTP/1.1 200 OK
x-amz-id-2: x+2M6DNTi8vZ+KRVCEFr6NDYLOfqxzGU+NFK9nOKWfVXu+nW7RIBPWW49162JfY/oreRLJJ7YLU=
x-amz-request-id: D1379F1B986A2A8A
Last-Modified: Fri, 20 Apr 2018 13:26:48 GMT
ETag: "50c635454d2e9bc8ff09c2e603fb00a0"
Accept-Ranges: bytes
Content-Type: binary/octet-stream
Content-Length: 122843
Server: AmazonS3
Date: Tue, 24 Apr 2018 20:37:09 GMT
Connection: keep-alive

puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736102381d302b17,d1f540b03d2239e040ff5ac571c475f7,29140
puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736143325220,eadce55df7fe3ecb6d0569498e425e8d,26139
puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736202381d302b17,8af621fb3c8c96dc0eb461d8465d9228,31354
puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736243325220,9b47ab0d0f37a6dcdeb49426756f11ec,31416
puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736302381d302b17,907eaa6af8e97316c25f22ea2ad122ed,28062
puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736343325220,5ea015696ed0feb95d5f457059a80714,26452
puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736402381d302b17,46c2d61ea649122fe8b5555f5c839a49,28226
puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736443325220,49f0315d4a7f753e595c577165be106b,28779
puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736502381d302b17,430c52983226f6232cc0fa374e8fcf21,28227
puzzleboostbutton/08204343063d172c3f1e2251213e171916650a095a6845736543325220,9b247a2bdac42eb93a210e7951ed7624,28778
atabouttwitter/1921585b052d01372704224731384d121921,8e5e78737a31105ce96b78bde15c3c29,653862
gachaatlas/1f345a510b39012f311e6602637b5147406c175d0b2c,be62ff34b39466faff84d901b3a22947,47667
gachaatlas/1f345a510b39012f311e66026c7a52464964175d0b2c,57ec12a633e5f6c01b892992ee82e1c0,49214
gachaatlas/1f345a510b39012f311e66026c7a57444b64175d0b2c,d040d24dbe2c469bc72f5264254e98ac,52746
gachaatlas/1f345a510b39012f311e66026c7a57464164175d0b2c,e85c4d0c34dd5d4b239edb3936b5148f,51812
gachaatlas/1f345a510b39012f311e66026c7a57474e64175d0b2c,283edd7487f6148fa9db90fdf7949889,52945
gachaatlas/1f345a510b39012f311e660364735a4f416c175d0b2c,84eedd834bc0ce1c2fad71f9583ef202,29400
gachaatlas/1f345a510b39012f311e660a647a53464866175d0b2c,8836a920bc23d986a851ea81d195a370,13470
skillcutin/0b3e5055063b003739036603647a53444860175d0b2c,0c888fd2c3be3e65a9aa37aaab815a34,241893
skillcutin/0b3e5055063b003739036603647a53444861175d0b2c,0424a01bf4d28e4709115fea7bbdf2ce,242895
skillcutin/0b3e5055063b003739036603647a53444862175d0b2c,651c07cee6143d40fab141553add88bb,243091
```


It seems like a list of the assets so I thing I might be little closer but If I request this and any other file via fiddler I got a 403 forbidden error, so I think the files need a key or the game “authenticates” (not sure if is the correct term) before you can download a file I think that because of the first request and response I got from the packet capture app in the initial download




That’s a login I think before the download starts so how I can emulate this and to get the files I want or I’m doing something wrong in the request to get the a file, here is an example for the model i got using the packet capture app trying to get it using fiddler 4



So if anyone knows what I’m doing wrong it would be helpful

Thanks in advance.
