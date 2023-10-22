## Post #1
- Username: fuvegotado
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 24, 2019 1:30 am
- Post datetime: 2022-12-20T19:53:34+00:00
- Post Title: [solved] Extract sound/music from High on Life

How to extract sound files from High on Life? It uses wwise and umodel does list sound files but export doesn't work. Quickbms (ut2004) also exports nothing.
## Post #2
- Username: fuvegotado
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 24, 2019 1:30 am
- Post datetime: 2022-12-31T00:07:26+00:00
- Post Title: [solved] Extract sound/music from High on Life

Fmodel from Github is able to open the .pak and just open and play and extract the audio

I was trying to find solutions step-by-step before I realized FModel is the solution:

> UE 4.27, Umodel/UE Viewer can export .uasset + .ubulk + .uexp files.
>
> 
>
> For example for the 68MB 499660376.ubulk, trid.exe guesses:
>
> Code: Select allCollecting data from file: 499660376.ubulk
>
>  40.0% (.WAV) RIFF/WAVe standard Audio (4008/2)
>
>  39.9% (.) Generic RIFF container (4000/1)
>
>  19.9% (.) Philips Respironics M-Series data format (2000/1)
>
> 
>
> and its HeX does start with:
>
> Code: Select allRIFF
>
> �'WAVEfmt B���ÿÿ� Œ��?.a
>
> 
>
> but of course it doesn't open like a .wav in audacity or vlc.
>
> 
>
> When converted to JSON via UAssetGUI, the .uasset file starts with:
>
> Code: Select all{
>
>   "$type": "UAssetAPI.UAsset, UAssetAPI",
>
>   "Info": "Serialized with UAssetAPI 1.0.0.0 (a5978d9)",
>
>   "NameMap": [
>
>     "/Game/WwiseAudio/Media/499660376",
>
>     "/Script/AkAudio",
>
>     "/Script/CoreUObject",
>
>     "499660376",
>
>     "AkMediaAsset",
>
>     "AkMediaAssetData",
>
>     "BoolProperty",
>
>     "Class",
>
>     "Default__AkMediaAsset",
>
>     "Default__AkMediaAssetData",
>
>     "Id",
>
>     "IsStreamed",
>
>     "None",
>
>     "Package",
>
>     "UInt32Property"
>
>   ],
>
>   "UseSeparateBulkDataFiles": true,
>
> 
>
> wwiseutil-gui.exe can't open the .ubulk file even if I rename the endings to .pck or .bnk or .nbnk or .npck
>
> 
>
> UAssetGUI is able to export two "Export Data" datasets but the results are extremely short (8 and 32 bytes) binary files.
>
> 
>
> At this point I searched for AkMediaAssetData on Github and found Fmodel.
