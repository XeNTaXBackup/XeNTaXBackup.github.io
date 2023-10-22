## Post #1
- Username: JaoSming
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 20, 2011 3:33 am
- Post datetime: 2013-05-18T21:31:07+00:00
- Post Title: [Solved] NBA 2K13 Audio Files

Years later we are still attempting to decode the music file in NBA 2K games on PC.  I think this has to be my third or fourth post here on the topic.

A new member on our site has made a lot of progress, finding that the songs are split up into a few second sections rather than one song followed by another.  He also found that each section or part of the song is split up in the file by the following header.

```
69A1BED202000000CD0500000A00000044AC
```


I'll quote his post on the finding

> isnt just header of section
>
> after 69A1BED2
>
> 02 part must point to stereo
>
> 44AC after CD05 part must point to 44100 rate
>
> and its ADPCM
>
> 
>
> So we are missing only two things
>
> 1. BitRate
>
> 2. Version of ADPCM ( Microsoft or Intel one )
>
> 
>
> so as its ADPCM its 4bit big-endian with chunks for every song
>
> every chunk/section has a number that is at offset 24 with it of an chunk

```
Chunks of 1st song
00000000
00003A62
000074C4
0000AF26
0000E988
000123EA
00015E4C
000198AE
0001D310
00020D72
000247D4
00028236
0002BC98
0002F6FA
0003315C
00036BBE
0003A620
0003E082
00041AE4
00045546
00048FA8
0004CA0A
0005046C
00053ECE
00057930
0005B392
0005EDF4
00062856
000662B8
00069D1A
0006D77C
000711DE
00074C40
000786A2
0007C104
0007FB66
000835C8
0008702A
0008AA8C
0008E4EE
00091F50
000959B2
00099414
0009CE76
000A08D8
000A433A
000A7D9C
000AB7FE
000AF260
000B2CC2
000B6724
000BA186
000BDBE8
000C164A
000C50AC
000C8B0E
000CC570
```


Here is the link to our forum thread if there are details I missed (there is no posts of the audio file anyone who can help outside of that header above will need to have 2K13 or 2K12 installed.  We know 2K11 has a different header. [http://forums.nba-live.com/viewtopic.php?f=149&t=91435](http://forums.nba-live.com/viewtopic.php?f=149&t=91435)

If it helps, he also posted a memory dump

```
Address Disassembly Text string
6F181000 OR EAX,27758EB1 (Initial CPU selection)
6F185AE3 PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F185AE8 PUSH 6F18A3BC UNICODE "ncalrpc"
6F189F4C PUSH 6F189FCC UNICODE "Microsoft\Windows Audio"
6F18ACF7 PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F18ACFC PUSH 6F18A3BC UNICODE "ncalrpc"
6F18B071 PUSH 6F18B2C0 UNICODE "UserDuckingPreference"
6F18B076 PUSH 6F18B278 UNICODE "Software\Microsoft\Multimedia\Audio"
6F18C17E MOV EDX,6F195728 UNICODE "NULL"
6F18C6AA PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F18C6AF PUSH 6F18A3BC UNICODE "ncalrpc"
6F18D082 MOV EBP,2883FBD6 UNICODE "e'.
"
6F18ECDC PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F18ECE1 PUSH 6F18A3BC UNICODE "ncalrpc"
6F18F846 MOV EDX,6F195728 UNICODE "NULL"
6F18FF20 PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F18FF25 PUSH 6F18A3BC UNICODE "ncalrpc"
6F19288F PUSH 6F1929F8 UNICODE "Global\SYSTEM_AUDIO_STREAM_MAPPING_%I64X"
6F1928B0 PUSH 6F1929A8 UNICODE "Global\SYSTEM_AUDIO_STREAM_EVENT_%I64X"
6F192A56 MOV EDX,6F195734 UNICODE "<NULL>"
6F19463B MOV EDX,6F195734 UNICODE "<NULL>"
6F195E6D PUSH 6F195F18 UNICODE "API-MS-Win-Core-LocalRegistry-L1-1-0.dll"
6F195E7C PUSH 6F195F08 ASCII "RegDeleteKeyExW"
6F195E8D PUSH 6F195EEC UNICODE "advapi32.dll"
6F195E9C PUSH 6F195EDC ASCII "RegDeleteKeyW"
6F196A8C MOV ESI,6F196B28 UNICODE ".tlb"
6F197121 PUSH 6F1973E4 UNICODE "CLSID\"
6F19715B PUSH 6F1973B8 UNICODE "\Required Categories"
6F197212 PUSH 6F1973E4 UNICODE "CLSID\"
6F197241 PUSH 6F197388 UNICODE "\Implemented Categories"
6F197A15 PUSH 6F197FAC UNICODE "Delete"
6F197A2B PUSH 6F197FD0 UNICODE "ForceRemove"
6F197AFF PUSH 6F197FBC UNICODE "NoRemove"
6F197B2B PUSH 6F197FE8 UNICODE "Val"
6F19830B PUSH 6F195648 UNICODE "{0662CA35-C93E-4700-A687-AF2648A0E2A5}"
6F198310 PUSH 6F1956B0 UNICODE "APPID"
6F198734 PUSH 6F1987CC UNICODE "Module"
6F198756 PUSH 6F1987B4 UNICODE "Module_Raw"
6F198771 PUSH 6F1987A0 UNICODE "REGISTRY"
6F1987F6 MOV DWORD PTR SS:[EBP-10],6F1956B0 UNICODE "APPID"
6F198805 MOV DWORD PTR SS:[EBP-C],6F195648 UNICODE "{0662CA35-C93E-4700-A687-AF2648A0E2A5}"
6F19B0CB MOV EDX,6F195734 UNICODE "<NULL>"
6F19B0D2 MOV EDX,6F195728 UNICODE "NULL"
6F19B13B MOV EBX,6F195728 UNICODE "NULL"
6F19B14A MOV EDX,6F195734 UNICODE "<NULL>"
6F19B18A MOV EAX,6F195734 UNICODE "<NULL>"
6F19DA24 PUSH 6F19DB78 UNICODE "AudioDeviceGraph"
6F19DA29 PUSH 6F18A3BC UNICODE "ncalrpc"
6F19E2D8 MOV EDX,6F195734 UNICODE "<NULL>"
6F19E2DF MOV EDX,6F195728 UNICODE "NULL"
6F19E376 MOV EDX,6F195734 UNICODE "<NULL>"
6F19E37D MOV EDX,6F195728 UNICODE "NULL"
6F1A1CAB PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A1CB0 PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A1D9D PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A1DA2 PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A1E75 PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A1E7A PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A1F4D PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A1F52 PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A202D PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A2032 PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A2105 PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A210A PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A21DD PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A21E2 PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A22B5 PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A22BA PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A2395 PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A239A PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A246D PUSH 6F18A3CC UNICODE "AudioClientRpc"
6F1A2472 PUSH 6F18A3BC UNICODE "ncalrpc"
6F1A2A16 MOV ECX,6F1A2A3C ASCII "NULL"
6F1A3EB6 MOV EBX,6F1A3F68 UNICODE "D:(A;OICI;0x%08I32X;;;%ws)"
6F1A4683 PUSH 6F1A46A0 ASCII "Invalid parameter passed to C runtime function.
"
6F1A6957 IMUL EBP,DWORD PTR DS:[EDI+6E],417845 ASCII "oA"
6F1AA6CC MOV EBX,80000 UNICODE "athan"

/////////////////////////////////////////////////////////////////////////////////////
Text strings referenced in X3DAudio:.text
Address Disassembly Text string
6CB51000 ADC AH,AL (Initial CPU selection)
6CB51299 PUSH 6CB51104 ASCII "Microsoft X3DAudio"
6CB5129E PUSH 6CB510B0 ASCII "CPU does not meet minimum requirement; Streaming SIMD Extensions support required."
6CB535FF PUSH 6CB53161 ASCII ";
"

//////////////////////////////////////////////////////////////////////////////////////

Text strings referenced in XAudio2_:.text
Address Disassembly Text string
61221000 POPFD (Initial CPU selection)
61222CD1 MOV EDI,7FFB3CC5 ASCII "????????????????????????????????????????????????? ?????????????????????????????????????????????????? ?????????????????????????????????????????????????? ?????????????????????????????????????????????????? ??????????????????????????????????????"...
61228B75 SUB EAX,0F0000 UNICODE "indows"
612291E5 SUB EAX,0F0000 UNICODE "indows"
612291F5 SUB EAX,0F0000 UNICODE "indows"
61229A2D SUB EAX,0F0000 UNICODE "indows"
6122AE4D CMP EAX,0F0000 UNICODE "indows"
6122AE65 CMP EAX,0F0000 UNICODE "indows"
6122AEB5 PUSH 0F0000 UNICODE "indows"
6122BA3D CMP EAX,0F0000 UNICODE "indows"
6122BC15 CMP EAX,0F0000 UNICODE "indows"
6122BFD5 PUSH 0F0000 UNICODE "indows"
6122C2B5 CMP EAX,0F0000 UNICODE "indows"
6122C5D5 CMP EAX,0F0000 UNICODE "indows"
6122CDBD CMP EAX,0F0000 UNICODE "indows"
6122CDED CMP EAX,0F0000 UNICODE "indows"
6122CE4D PUSH 0F0000 UNICODE "indows"
6122DA65 CMP EAX,0F0000 UNICODE "indows"
6122E2AD PUSH 0F0000 UNICODE "indows"
6122E2E5 PUSH 0F0000 UNICODE "indows"
6122ECC5 CMP EAX,0F0000 UNICODE "indows"
6122EDB5 CMP EAX,0F0000 UNICODE "indows"
6122EEF5 PUSH 0F0000 UNICODE "indows"
6122EF4D PUSH 0F0000 UNICODE "indows"
6122EFDD PUSH 0F0000 UNICODE "indows"
6122F435 CMP EAX,0F0000 UNICODE "indows"
6122F45D CMP EAX,0F0000 UNICODE "indows"
6122F4BD PUSH 0F0000 UNICODE "indows"
6122F51D PUSH 0F0000 UNICODE "indows"
61237E5F MOV ESP,70004 ASCII "(
"
61237F3F MOV ESP,0F0004 UNICODE "dows"
61238AB6 IMUL ECX,ESP,30002 ASCII "tx "
612392E5 ADD EAX,30002 ASCII "tx "
6123990B ADD EAX,30002 ASCII "tx "
61239943 ADD EAX,80002 UNICODE "than"
61239B8F ADD EAX,30002 ASCII "tx "
61239E75 ADD EAX,30002 ASCII "tx "
6123A425 ADD EAX,30002 ASCII "tx "
6123A72F ADD EAX,30002 ASCII "tx "
6123B0D3 MOV EAX,90004 UNICODE "ge)"
6123B9D5 MOV EBX,90006 UNICODE "e)"
6123C717 MOV EBP,30002 ASCII "tx "
6123C7E7 MOV ESP,70004 ASCII "(
"
61243571 PUSH 612212FC ASCII "XMA1"
61243597 MOV DWORD PTR SS:[EBP-8],612212F4 ASCII "Mono"
612435AF MOV DWORD PTR SS:[EBP-C],612212EC ASCII "Stereo"
612435C7 MOV DWORD PTR SS:[EBP-10],612212E8 ASCII "2.1"
612435DF MOV DWORD PTR SS:[EBP-14],612212E0 ASCII "Quad"
612435F4 MOV DWORD PTR SS:[EBP-18],612212DC ASCII "4.1"
61243609 MOV DWORD PTR SS:[EBP-1C],612212D8 ASCII "5.1"
6124361E MOV DWORD PTR SS:[EBP-20],612212D4 ASCII "6.1"
61243633 MOV DWORD PTR SS:[EBP-24],612212D0 ASCII "7.1"
6124363C MOV DWORD PTR SS:[EBP-24],612212C0 ASCII "ManyChannels"
61243676 MOV DWORD PTR SS:[EBP-28],612212B8 ASCII "Float"
6124368B MOV DWORD PTR SS:[EBP-2C],612212B0 ASCII "Adpcm"
612436A3 MOV DWORD PTR SS:[EBP-30],612212A8 ASCII "XMA2"
612436BA MOV DWORD PTR SS:[EBP-34],612212A0 ASCII "WMAStd"
612436D2 MOV DWORD PTR SS:[EBP-38],61221298 ASCII "WMAPro"
612436EA MOV DWORD PTR SS:[EBP-3C],6122128C ASCII "WMASpdif"
61243701 MOV DWORD PTR SS:[EBP-40],61221280 ASCII "AC3Spdif"
61243716 MOV DWORD PTR SS:[EBP-44],61221278 ASCII "Unknown"
6124372B MOV DWORD PTR SS:[EBP-48],61221270 ASCII "Pcm8Bit"
61243740 MOV DWORD PTR SS:[EBP-4C],61221264 ASCII "Pcm16Bit"
61243755 MOV DWORD PTR SS:[EBP-50],61221258 ASCII "Pcm24Bit"
6124376A MOV DWORD PTR SS:[EBP-54],6122124C ASCII "Pcm32Bit"
61243773 MOV DWORD PTR SS:[EBP-54],61221238 ASCII "BadBitsPerSample"
612437D4 PUSH 6122122C ASCII "%luk%s%s"
61246AB5 PUSH 61221424 ASCII "Microsoft XAudio2"
61246ABA PUSH 612213D0 ASCII "CPU does not meet minimum requirement; Streaming SIMD Extensions support required."
61248890 PUSH 61221324 ASCII "SimpList: non-growable list ran out of room for new elements"
61248974 PUSH 61221324 ASCII "SimpList: non-growable list ran out of room for new elements"
61250324 PUSH 61221324 ASCII "SimpList: non-growable list ran out of room for new elements"
61250561 PUSH 6122187C ASCII "CLSID\{"
612505FE PUSH 61221868 ASCII "InProcServer32"
61250613 PUSH 61221860 ASCII "Both"
61250618 PUSH 61221850 ASCII "ThreadingModel"
6125061D PUSH 61221868 ASCII "InProcServer32"
612506B8 PUSH 6122187C ASCII "CLSID\{"
61253CFD PUSH 612219A8 ASCII "Software\Microsoft\Multimedia\LEAP"
61253D24 PUSH 61221994 ASCII "PreferredRenderer"
61253D37 PUSH 61221988 ASCII "DirectSound"
61253D5C PUSH 61221984 ASCII "UMA"
6125586B PUSH 61221A84 UNICODE "Unknown"
61256860 PUSH 61221324 ASCII "SimpList: non-growable list ran out of room for new elements"
61256A0E PUSH 61221AF0 ASCII "dsound.dll"
61256A4E PUSH 61221AE4 ASCII "GetDeviceID"
61256A68 PUSH 61221ACC ASCII "DirectSoundEnumerateW"
61256A85 PUSH 61221AB8 ASCII "DirectSoundCreate"
61256C73 PUSH 61221B00 UNICODE "{%8.8lX-%4.4X-%4.4X-%2.2X%2.2X-%2.2X%2.2X%2.2X%2.2X%2.2X%2.2X}"
6125751C PUSH 61221AF0 ASCII "dsound.dll"
6125755B PUSH 61221AB8 ASCII "DirectSoundCreate"
61258F0F PUSH 61221C8C ASCII "avrt.dll"
61258F4F PUSH 61221C6C ASCII "AvSetMmThreadCharacteristicsA"
61258F7B PUSH 61221C54 ASCII "AvSetMmThreadPriority"
61258FAA PUSH 61221C34 ASCII "AvRevertMmThreadCharacteristics"
61258FD8 PUSH 61221C2C ASCII "Audio"
6125AA64 PUSH 61221324 ASCII "SimpList: non-growable list ran out of room for new elements"
6125AF71 MOV DWORD PTR SS:[EBP-44],61221D64 ASCII "LocalNonPcmOutputPackets"
6125AF88 MOV DWORD PTR SS:[EBP-44],61221D50 ASCII "LocalOutputPackets"
6125AF9F MOV DWORD PTR SS:[EBP-44],61221D3C ASCII "RemoteOutputPackets"
6125AFAE PUSH 612219A8 ASCII "Software\Microsoft\Multimedia\LEAP"
61261494 PUSH 61221324 ASCII "SimpList: non-growable list ran out of room for new elements"
6126857B PUSH 612212FC ASCII "XMA1"
6126859D MOV EDX,612212F4 ASCII "Mono"
612685AA MOV EDX,612212EC ASCII "Stereo"
612685B7 MOV EDX,612212E8 ASCII "2.1"
612685C4 MOV EDX,612212E0 ASCII "Quad"
612685D1 MOV EDX,612212DC ASCII "4.1"
612685DE MOV EDX,612212D8 ASCII "5.1"
612685EB MOV EDX,612212D4 ASCII "6.1"
612685F6 MOV EDX,612212D0 ASCII "7.1"
612685FD MOV EDX,612212C0 ASCII "ManyChannels"
61268608 MOV EAX,612212B8 ASCII "Float"
61268618 MOV EAX,612212B0 ASCII "Adpcm"
61268629 MOV EAX,612212A8 ASCII "XMA2"
6126863A MOV EAX,612212A0 ASCII "WMAStd"
61268648 MOV EAX,61221298 ASCII "WMAPro"
61268656 MOV EAX,6122128C ASCII "WMASpdif"
61268664 MOV EAX,61221280 ASCII "AC3Spdif"
61268671 MOV EAX,61221278 ASCII "Unknown"
61268682 MOV EAX,61221270 ASCII "Pcm8Bit"
6126868F MOV EAX,61221264 ASCII "Pcm16Bit"
6126869C MOV EAX,61221258 ASCII "Pcm24Bit"
612686A7 MOV EAX,6122124C ASCII "Pcm32Bit"
612686AE MOV EAX,61221238 ASCII "BadBitsPerSample"
612686C2 PUSH 6122122C ASCII "%luk%s%s"
612693FD MOV ESI,30D40 UNICODE "ccf1df",type="win32",version="5.82.7601.17514"C:\ Windows\WinSxS\manifests\x86_microsoft.windows.com m"
6127D4D0 MOV ESI,61227128 ASCII ""V"
61297E51 MOV DWORD PTR DS:[6129B670],61221888 ASCII "XAudio2"
61297E89 MOV DWORD PTR DS:[6129B684],612218C4 ASCII "AudioVolumeMeter"
61297EC1 MOV DWORD PTR DS:[6129B698],612218A8 ASCII "AudioReverb"
61297FE4 MOV ESI,61222090 UNICODE "Copyright (c) Microsoft Corporation"
61297FE9 MOV EDI,6129BC18 UNICODE "Copyright (c) Microsoft Corporation"
612980D0 MOV ESI,61222090 UNICODE "Copyright (c) Microsoft Corporation"
612980D5 MOV EDI,6129C048 UNICODE "Copyright (c) Microsoft Corporation"
612981BC MOV ESI,61222090 UNICODE "Copyright (c) Microsoft Corporation"
612981C1 MOV EDI,6129C478 UNICODE "Copyright (c) Microsoft Corporation"
61298268 MOV ESI,6122224C UNICODE "FilterMatrixMix"
6129826D MOV EDI,6129C6A8 UNICODE "FilterMatrixMix"
6129828D MOV ESI,61222090 UNICODE "Copyright (c) Microsoft Corporation"
61298292 MOV EDI,6129C8A8 UNICODE "Copyright (c) Microsoft Corporation"
61298338 MOV ESI,612222CC UNICODE "ADPCM decoder"
6129833D MOV EDI,6129CAD8 UNICODE "ADPCM decoder"
6129835D MOV ESI,61222090 UNICODE "Copyright (c) Microsoft Corporation"
61298362 MOV EDI,6129CCD8 UNICODE "Copyright (c) Microsoft Corporation"
61298460 MOV ESI,61222090 UNICODE "Copyright (c) Microsoft Corporation"
61298465 MOV EDI,6129D108 UNICODE "Copyright (c) Microsoft Corporation"
6129854C MOV ESI,61222090 UNICODE "Copyright (c) Microsoft Corporation"
61298551 MOV EDI,6129D538 UNICODE "Copyright (c) Microsoft Corporation"
61298E1F IMUL EBP,DWORD PTR DS:[EDI+6E],417845 ASCII "oA"
```


Followed by this

> These 3 things are important
>
> 
>
> 612686AE MOV EAX,61221238 ASCII "BadBitsPerSample" <<< Sample Check
>
> 61298338 MOV ESI,612222CC UNICODE "ADPCM decoder" <<< Data Compression
>
> 6129833D MOV EDI,6129CAD8 UNICODE "ADPCM decoder" <<< Data Compression
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-05-24T07:03:10+00:00
- Post Title: [Solved] NBA 2K13 Audio Files

The header on these seems to be possibly around 90-94 bytes as there is ever repeating similarities, possibly basic header followed by an decoding table(?) thus the 00s prior to main data that is very dense.

It would be doubtful this is adpcm if such small filesizes vs lenght, in any case, file is 44khz stereo according to header which means PCM output bitrate of 1411kbps and that in adpcm is 352kbps, so filesize should be more than 320kbps mp3 encoded of a song.

If microsoft xaudio2 system is used to handle all audio literally, it outlines formats available to MS ADPCM,XMA (only xbox360),wma,xwma (?)

WMA is possible for being used in the lower sizes than adpcm is capable of, either way, looks very custom job atleast header wise and can't say more as not so familiar with wma and its variants.

Should record the song and find its encoded version and encode with various fixed kbps ratio (say mp3) to find closest match to the filesize to suggest the level of compression/codec used.
## Post #3
- Username: JaoSming
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 20, 2011 3:33 am
- Post datetime: 2013-06-16T21:46:52+00:00
- Post Title: [Solved] NBA 2K13 Audio Files

I was going to be bumping today asking for more help, but the guy on our forums was able to figure it out.  For the sake of sharing information, NBA 2K13's jukeboxmusic.bin file uses

> WMA (version2)
>
> 44100
>
> 31kbps
>
> 16bits
>
> stereo

Props to nesa24 on our forums for figuring that out, and thank you to everyone here that we've bothered over the years asking for help with this game series.
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-06-24T06:30:49+00:00
- Post Title: [Solved] NBA 2K13 Audio Files

congrats on that, I had a hunch it was one of the WMA related codecs given filesize and microsoft libraries.
