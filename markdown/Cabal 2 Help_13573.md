## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-11-24T19:10:48+00:00
- Post Title: Cabal 2 Help

Hello guys, well today I try make some bypass methods to load models in Cabal 2, for some reason when try load a chr model file I got this issue in script.



> -- Error occurred in i300a3db(); filename: C:\Program Files\Autodesk\3ds Max 2014\scripts\Cabal2\C2.ms; position: 4242; line: 0
>
> --  Frame:
>
> --   g78c2467: [0,0,0]
>
> --   fscale: 1
>
> --   i56ef901: 0
>
> --   f: <BinStream:C:\Users\xxx\Desktop\char_40\body.chr>
>
> --   b0201145: 0
>
> --   d284fc56: #(undefined, undefined, undefined, undefined, undefined, #Multi/Sub-Object:body(Standard:char_40_h, Standard:char_40_m1, Standard:char_40_s, Standard:char_40_c, Standard:char_40_m2, Standard:char_40_weapon_m1, Standard:char_40_weapon_m2), undefined, undefined, undefined, #Multi/Sub-Object:body(Standard:char_40_h, Standard:char_40_m1, Standard:char_40_s, Standard:char_40_c, Standard:char_40_m2, Standard:char_40_weapon_m1, Standard:char_40_weapon_m2))
>
> --   a223dcd3: 0
>
> --   d33ef847: (matrix3 [0,0,0] [0,0,0] [0,0,0] [0,0,0])
>
> --   e702203a: ""
>
> --   i854dd20: [0,0,0]
>
> --   f770d529: 0
>
> --   h3ed8742: (quat 0 1 0 0)
>
> --   called in e572cd54 loop; filename: C:\Program Files\Autodesk\3ds Max 2014\scripts\Cabal2\C2.ms; position: 8785; line: 0
>
> --  Frame:
>
> --   e572cd54: #(-1394868224, 11, 0, 2048, 424, 78304)
>
> --   called in f501c263(); filename: C:\Program Files\Autodesk\3ds Max 2014\scripts\Cabal2\C2.ms; position: 9053; line: 0
>
> --  Frame:
>
> --   e3f5881a: 20
>
> --   fscale: 1
>
> --   f80566e2: #()
>
> --   g83eadc7: #(#(2584, 19, 52428, 0, 0, 2328), #(2328, 100, 0, 2684, -859045874, -859045868), #(-859045868, 2, 0, 2048, 68, 424), #(424, 2752, 0, -859045868, 4, 5), #(5, 2048, 0, 424, 3176, 3600), #(3600, 20, 52428, 6, 2048, 2048), #(2048, 424, 0, 4024, -859045868, -859045868), #(-859045868, 7, 0, 2048, 424, 424), #(424, 4448, 0, -859045868, 8, 9), #(9, 2048, 0, 424, 4872, 5296), #(5296, 20, 52428, 10, 2048, 2048), #(2048, 424, 0, 5720, -859045868, -1394868224), #(-1394868224, 11, 0, 2048, 424, 78304), #(78304, 6144, 0, -1394868223, 150, 151), #(151, 2048, 0, 20416, 84448, 104864), #(104864, 3, 44252, 152, 2048, 2048), #(2048, 872, 1, 171272, -1394868222, -1394868219), #(-1394868219, 153, 0, 2048, 20, 310640), #(310640, 40220, 2, -1394868220, 154, 155), #(155, 2048, 0, 50092, 481932, 532024), ...)
>
> --   f: <BinStream:C:\Users\xxxx\Desktop\char_40\body.chr>
>
> --   dec80413: 128
>
> --   d284fc56: #(undefined, undefined, undefined, undefined, undefined, #Multi/Sub-Object:body(Standard:char_40_h, Standard:char_40_m1, Standard:char_40_s, Standard:char_40_c, Standard:char_40_m2, Standard:char_40_weapon_m1, Standard:char_40_weapon_m2), undefined, undefined, undefined, #Multi/Sub-Object:body(Standard:char_40_h, Standard:char_40_m1, Standard:char_40_s, Standard:char_40_c, Standard:char_40_m2, Standard:char_40_weapon_m1, Standard:char_40_weapon_m2))
>
> --   a5e322dc: "C:\Users\xxx\Desktop\char_40\body.chr"
>
> --   g22701a1: "CryTek"
>
> --   b65ed331: #()
>
> --   f33b8042: 1861
>
> --   called in opnRes.pressed(); filename: C:\Program Files\Autodesk\3ds Max 2014\scripts\Cabal2\C2.ms; position: 9626; line: 0
>
> --  Frame:
>
> --   ce3a645b: ".chr"
>
> --   a5e322dc: "C:\Users\xxx\Desktop\char_40\body.chr"
>
> --   b65ed331: #()
>
> >> MAXScript Rollout Handler Exception:
>
> -- Runtime error: array index must be positive number, got: 0 <<

here is a sample of file I try load.

[http://www.2shared.com/file/AZrHC7-2/char_40.html](http://www.2shared.com/file/AZrHC7-2/char_40.html)
