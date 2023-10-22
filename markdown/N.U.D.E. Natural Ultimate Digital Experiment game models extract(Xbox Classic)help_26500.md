## Post #1
- Username: AgentCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 02, 2023 9:27 pm
- Post datetime: 2023-02-22T09:54:39+00:00
- Post Title: N.U.D.E. Natural Ultimate Digital Experiment game models extract(Xbox Classic)help

I used Yandex Translate to translate the following text (Chinese to English), there may be some grammatical 

problemsPrevious posts:[viewtopic.php?t=24750](https://forum.xentax.com/viewtopic.php?t=24750)
Thanks @RokkuDayo  @shakotay2 , more than 20 years after the game was released, there are still people who want to know her.

It took me a long time to figure out the model structure of this game. There are 5 character model files in the game without encryption/obfuscation.BU/FL is the character's high-precision upper body/low-precision whole body, and BU/FL has some of the same models.

BU_base/BU_base_TANEDA is the same except that the hair model is different.FL_base/FL_base_taneda/FL_baseorg These three are almost the same model.

For all model files, 0x3-0x7 represents the length/title of the vertex area, 0x8 is the starting point of the vertex, the beginning part is the model of the hair, the length is 52 bytes (padding 40), BU_base/BU_base_taneda/FL_ The number of vertices used by the hair are: 4108/2661/1006, the subsequent data is the vertex data of other parts of the body, the length is 32 bytes, but some of them overlap, and direct reading will produce “noise”.

According to the instructions of the game production team, they have made high-precision/low-precision models for use in animation (sitting posture) and normal scenes, but at present they only see high-precision models of the upper body. Where is the high-precision model of the lower body?Could it be FL_base?Its size is 374KB, it may also be superimposed by the model?



picture 未标题-1.jpg (168.69 KiB) Viewed 55 times



There is an animation of the character's description on the title screen of the game. It can be intercepted in Cxbx-Reloaded using Ninja Ripper 1.7.1 (wait about 10 minutes to see it after opening the game). Referring to the screen, the model used should be “BU_base_TANEDA.MMX"(I put the intercepted model in the link after the article: PASS-half-from-ninjaripper.Max, the original model is very small, so I enlarged it by 100x)

xxxx.motion.MMX is an action file, so “ndbm"/"ndfm” is the action file of the character ,it took me a long time to find out that they are not models.

Use IDA to analyze the game's startup file :default.xbe, the “sub_3DF10” and "sub_36D80""sub_36A20" in it may be the parameters of the game engine when calling the model (but I can't understand...).
Code: (dummy code)

> int __thiscall sub_3DF10(int this, int a2, int a3)
>
> {
>
>   _DWORD *v4; // ebx
>
>   int *v5; // ebp
>
>   _DWORD *v6; // edi
>
>   int v7; // eax
>
>   int v8; // eax
>
>   int v9; // eax
>
>   int v11; // [esp+50h] [ebp-20h]
>
>   int v12[3]; // [esp+64h] [ebp-Ch] BYREF
>
> 
>
>   *(_DWORD *)(this + 704) = a3;
>
>   sub_11010((_DWORD *)(this + 728), a2);
>
>   v4 = (_DWORD *)(this + 716);
>
>   sub_96F60(this + 716);
>
>   if ( (*(int (__stdcall **)(_DWORD, char *, _DWORD))(*(_DWORD *)*v4 + 12))(*v4, off_3C9F2C[0], 0) == 1 )
>
>     sub_50D30(1);
>
>   sub_3D850(&unk_3C9BF8, 0, *v4);
>
>   v5 = (int *)(this + 720);
>
>   (**(void (__stdcall ***)(_DWORD, void *, int))*v4)(*v4, &unk_31B73C, this + 720);
>
>   (*(void (__stdcall **)(int, _DWORD, _DWORD))(*(_DWORD *)*v5 + 12))(*v5, 0, 0);
>
>   if ( dword_4038C0 == 4 )
>
>     sub_3CE20(&dword_3C152C);
>
>   else
>
>     sub_3CE20(&dword_403934);
>
>   (*(void (__stdcall **)(int))(*(_DWORD *)*v5 + 16))(*v5);
>
>   (*(void (__stdcall **)(_DWORD, _DWORD))(*(_DWORD *)*v4 + 52))(*v4, 0);
>
>   (*(void (__stdcall **)(_DWORD))(*(_DWORD *)*v4 + 48))(*v4);
>
>   v6 = (_DWORD *)(this + 708);
>
>   sub_21A10(0, &unk_31B5AC, this + 708);
>
>   (*(void (__stdcall **)(_DWORD, _DWORD))(*(_DWORD *)*v6 + 68))(*v6, *v4);
>
>   (*(void (__stdcall **)(int, _DWORD))(*(_DWORD *)a2 + 48))(a2, *(_DWORD *)(this + 708));
>
>   (*(void (__stdcall **)(_DWORD, int))(*(_DWORD *)*v6 + 172))(*v6, dword_403EE0);
>
>   (*(void (__stdcall **)(_DWORD, int))(*(_DWORD *)*v6 + 172))(*v6, dword_403EE4);
>
>   (*(void (__stdcall **)(_DWORD, int))(*(_DWORD *)*v6 + 172))(*v6, dword_403EE8);
>
>   (*(void (__stdcall **)(_DWORD, int))(*(_DWORD *)*v6 + 172))(*v6, dword_403EEC);
>
>   v7 = *(_DWORD *)(this + 708);
>
>   v12[0] = 1056964608;
>
>   v12[1] = 1056964608;
>
>   v12[2] = 1056964608;
>
>   (*(void (__stdcall **)(int, _DWORD, int *))(*(_DWORD *)v7 + 28))(v7, 0, v12);
>
>   sub_E9990(*v5, 0);
>
>   sub_E8D60(off_3EC598, 0);
>
>   sub_EA7D0("Textures\\w-cube.dds");
>
>   sub_EAB40((void *)(this + 380), *v5, off_3EC668);
>
>   sub_EA870(637534207);
>
>   v8 = sub_EA580(this + 380);
>
>   sub_EA590(v8);
>
>   sub_EAB40((void *)(this + 404), *v5, &off_3EC660);
>
>   sub_EA870(637534207);
>
>   *(_BYTE *)(this + 421) = 1;
>
>   v9 = sub_EA580(this + 380);
>
>   sub_EA590(v9);
>
>   sub_EAB40((void *)(this + 428), *v5, off_3EC6F0);
>
>   sub_EA870(2013265919);
>
>   sub_EAD40(*v5, off_3EC738);
>
>   sub_EA4A0(*v5, off_3EC778);
>
>   sub_EA2E0(*v5, 0);
>
>   v11 = *(_DWORD *)(this + 708);
>
>   *(_DWORD *)(this + 848) = 0;
>
>   *(_BYTE *)(this + 840) = 0;
>
>   *(_DWORD *)(this + 852) = 0;
>
>   *(_DWORD *)(this + 856) = 0;
>
>   *(_DWORD *)(this + 860) = 0;
>
>   sub_2CDD0((_DWORD *)(this + 4004), v11);
>
>   sub_2CDD0((_DWORD *)(this + 4024), *(_DWORD *)(this + 708));
>
>   (*(void (__stdcall **)(_DWORD, _DWORD))(**(_DWORD **)(this + 4008) + 12))(*(_DWORD *)(this + 4008), 0);
>
>   return (*(int (__stdcall **)(_DWORD, _DWORD))(**(_DWORD **)(this + 4028) + 12))(*(_DWORD *)(this + 4028), 0);
>
> }
I hope someone can make a tool to read these model data. BMS script or 3Ds Max script can be used. The files I mentioned are all here:
[https://pan.baidu.com/s/1YBz6cEQFCMQENfQ2Algzsw](https://pan.baidu.com/s/1YBz6cEQFCMQENfQ2Algzsw)
Extraction code: 5pz1
