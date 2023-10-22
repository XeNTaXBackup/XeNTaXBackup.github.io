## Post #1
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2008-03-19T20:36:19+00:00
- Post Title: Call Of Duty Roads To Victory PSP .RES Text file!!

Hi folks, i´m new here and i have this game and i wanna translate it, i found the text file, but i can´t edit it, can anyone help me?
[eng.rar](https://xentaxbackup.github.io/file/1475_eng.rar)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-03-20T22:23:36+00:00
- Post Title: Call Of Duty Roads To Victory PSP .RES Text file!!

This MexScript can at least extract the text stuff using MultiEx Commander. It is a crude script and not really covers the actual format of the archive (GRAF). 

```
Set F String "text" ;
Set Ba String ".txt" ;
Get B Byte 0 ;
Get U1 Int 0 ;
Get U2 Int 0 ;
Get U3 Long 0 ;
Get DOff Long 0 ;
Get DataSize Long 0 ;
SavePos TailOffOff 0 ;
Get TailOff Long 0 ;
GoTo TailOff 0 ;
Get FNum Long 0 ;
Get Type Long 0 ;
For T = 1 To FNum ;
Get Type Long 0 ;
Get ROff Long 0 ;
Get RSize Long 0 ;
Get U4 Long 0 ;
Get U5 Long 0 ;
SavePos TOff 0 ;
Math ROff += DOff ;
GoTo ROff 0 ;
Get DSize Long 0 ;
Get Type Long 0 ;
SavePos FOO 0 ;
Set Name String F ;
String Name += T ;
String Name += Ba ;
Log Name FOO DSize 0 0 ;
GoTo TOff 0 ;
Next T ;

```


Here's an example of what it extracted: 

```
{
tod_01_arnhem_a_a_11=
{
text = "Operation Market Garden",
},
tod_01_arnhem_a_a_12=
{
text = "Arnhem, Netherlands",
},
tod_01_arnhem_a_a_28=
{
text = "17 September 1944",
},
bs3_01_arnhem_a_f_10=
{
displaytime= 1.477,
text = "We have them in a crossfire!",
},
bs2_01_arnhem_a_d_26=
{
displaytime= 0.689,
text = "Watch out!",
},
bs4_01_arnhem_a_e_18=
{
displaytime= 2.633,
text = "One of our gliders has crashed into a building up ahead!",
},
bco_01_arnhem_a_a_18=
{
displaytime= 1.631,
text = "Don't move! Stay right there!",
},
bs4_01_arnhem_a_e_22=
{
displaytime= 3.57,
text = "There are injured men over there! We need to get to them before it's too late!",
},
bco_01_arnhem_a_a_13=
{
displaytime= 4.05,
text = "Hold on, sorry about that. We're scattered from hell to breakfast and the Jerries are everywhere.",
},
bs2_01_arnhem_a_d_12=
{
displaytime= 1.387,
text = "There's no going back that way!",
},
bs4_01_arnhem_a_b_3=
{
displaytime= 1.447,
text = "Look out! Hanomag!",
},
bs4_01_arnhem_a_e_21=
{
displaytime= 1.411,
text = "Cover us so we can advance!",
},
tod_01_arnhem_a_e_35=
{
text = "Protect your troops so they can advance.",
},
bs2_01_arnhem_a_e_19=
{
displaytime= 0.956,
text = "Quick! Through here!",
},
bs4_01_arnhem_a_b_4=
{
displaytime= 0.895,
text = "Set the charge!",
},
bs3_01_arnhem_a_b_5=
{
displaytime= 1.038,
text = "Get clear!",
},
bs4_01_arnhem_a_b_6=
{
displaytime= 2.101,
text = "Our gliders are safer for that bit of work!",
},
bs3_01_arnhem_a_b_7=
{
displaytime= 1.39,
text = "Let's push on to the bridge!",
},
bs4_01_arnhem_a_f_7=
{
displaytime= 2.814,
text = "My God! It must be one Hell of a fight up ahead.",
},
bs1_01_arnhem_a_c_9=
{
displaytime= 1.59,
text = "Germans! Behind the lorry!",
},
tod_01_arnhem_a_b_8=
{
text = "Make your way to the bridge.",
},
bs2_01_arnhem_a_g_10=
{
displaytime= 4.952,
text = "The whole thing's bollixed! Bloody Jerries are protecting the bridge with everything they've got!",
},
bs4_01_arnhem_a_c_14=
{
displaytime= 1.591,
text = "Come on! This way to the bridge!",
},
bs2_01_arnhem_a_f_10=
{
displaytime= 1.794,
text = "Ohhhh.",
voice = "moan of pain"
},
bco_01_arnhem_a_g_11=
{
displaytime= 4.097,
text = "We're not giving in just yet! Send up another squad to clear those MG nests!",
},
tod_01_arnhem_a_c_13=
{
text = "Clear through the supply depot.",
},
bs3_01_arnhem_a_f_11=
{
displaytime= 2.531,
text = "Ahhhhh.",
voice = "moan of pain"
},
bs2_01_arnhem_a_g_12=
{
displaytime= 2.798,
text = "You heard your commanding officer! Move out!",
},
bs4_01_arnhem_a_f_12=
{
displaytime= 2.624,
text = "Ohhhh.",
voice = "moan of pain"
},
bs1_01_arnhem_a_f_13=
{
displaytime= 1.921,
text = "Ahhhh",
voice = "moan of pain"
},
bs2_01_arnhem_a_d_19=
{
displaytime= 1.286,
text = "Did you hear that Perrins?",
},
bco_01_arnhem_a_a_14=
{
displaytime= 2.377,
text = "Come on then, we've got to gather the men and get to the bridge!",
},
tod_01_arnhem_a_g_15=
{
text = "Take the Arnhem Bridge.",
},
bs4_01_arnhem_a_f_8=
{
displaytime= 0.883,
text = "There's the CO!",
},
bs1_01_arnhem_a_d_20=
{
displaytime= 2.168,
text = "Sounds like a Panzer. But where's it coming from?",
},
tod_01_arnhem_a_a_26=
{
text = "Rendezvous with your squad.",
},
bs2_01_arnhem_a_d_20=
{
displaytime= 1.353,
text = "Run! Run!",
},
bs3_01_arnhem_a_g_15=
{
displaytime= 1.286,
text = "Take out that MG!",
},
bs1_01_arnhem_a_d_28=
{
displaytime= 1.965,
text = "Aaaaah!",
voice = "Death by tank"
},
bs4_01_arnhem_a_g_16=
{
displaytime= 0.987,
text = "Watch that tower!",
},
bs2_01_arnhem_a_d_21=
{
displaytime= 1.023,
text = "Now's our chance!",
},
bs3_01_arnhem_a_a_17=
{
displaytime= 1.678,
text = "We're pinned down here! Give us a hand!",
},
bs1_01_arnhem_a_g_17=
{
displaytime= 1.832,
text = "There's a tank coming across the bridge!",
},
bs4_01_arnhem_a_a_27=
{
displaytime= 2.746,
text = "Those Ack Acks are making short work of our gliders!",
},
bs2_01_arnhem_a_d_27=
{
displaytime= 1.858,
text = "Come on! Let's get out of here.",
},
bs1_01_arnhem_a_g_18=
{
displaytime= 0.742,
text = "Look out!",
},
bco_01_arnhem_a_a_15=
{
displaytime= 2.026,
text = "Advance on that flak cannon and take it out!",
},
tod_01_arnhem_a_a_16=
{
text = "Destroy the Flak Cannon.",
},
bco_01_arnhem_a_a_19=
{
displaytime= 1.689,
text = "Get up there and put a charge on that gun!",
},
bs2_01_arnhem_a_d_22=
{
displaytime= 3.251,
text = "That was close! Too close for poor old Perrins.",
},
bs3_01_arnhem_a_g_19=
{
displaytime= 2.011,
text = "We've got to put a sticky bomb on that tank!",
},
bs4_01_arnhem_a_a_20=
{
displaytime= 2.261,
text = "Hurry up! Plant the charge on the Flak cannon!",
},
bs4_01_arnhem_a_a_24=
{
displaytime= 1.654,
text = "Charges are set! Get clear!",
},
bs3_01_arnhem_a_a_21=
{
displaytime= 2.368,
text = "There's another flak gun across the street! Let's go!",
},
bs4_01_arnhem_a_g_21=
{
displaytime= 2.006,
text = "That's got it! Now get clear!",
},
tod_01_arnhem_a_g_25=
{
text = "Rendezvous with your allies",
},
tod_01_arnhem_a_a_22=
{
text = "Destroy the second flak cannon.",
},
bs4_01_arnhem_a_g_24=
{
displaytime= 0.98,
text = "We've done it!",
},
tod_01_arnhem_a_e_40=
{
text = "You have failed to protect your allies.",
},
bs1_01_arnhem_a_g_24=
{
displaytime= 3.664,
text = "It's not over yet. We hold the bridge, now we have to defend it.",
},
bs2_01_arnhem_a_d_23=
{
displaytime= 0.762,
text = "In here!",
},
bs4_01_arnhem_a_e_39=
{
displaytime= 2.421,
text = "Man down! Man down! What are you doing?",
},
bs4_01_arnhem_a_e_40=
{
displaytime= 1.129,
text = "You've got to cover me!",
},
bs3_01_arnhem_a_e_38=
{
displaytime= 1.164,
text = "Good job! This way!",
},
bs2_01_arnhem_a_e_25=
{
displaytime= 3.001,
text = "Germans! We've got to hold them off the glider!",
},
bs3_01_arnhem_a_e_25=
{
displaytime= 1.544,
text = "Man that MG! Now!",
},
tod_01_arnhem_a_e_36=
{
text = "Hold the Germans off of the crashed glider.",
},
bs3_01_arnhem_a_e_27=
{
displaytime= 1.309,
text = "Germans to the right!",
},
bs3_01_arnhem_a_e_28=
{
displaytime= 0.962,
text = "On your left!",
},
bs3_01_arnhem_a_e_29=
{
displaytime= 1.104,
text = "Down on the street!",
},
bs3_01_arnhem_a_e_30=
{
displaytime= 0.998,
text = "To the right!",
},
bs3_01_arnhem_a_e_31=
{
displaytime= 1.27,
text = "More to your left!",
},
bs3_01_arnhem_a_e_32=
{
displaytime= 1.646,
text = "He's got a Panzerschreck!",
},
bs3_01_arnhem_a_e_41=
{
displaytime= 1.293,
text = "That's the last of them!",
},
bs4_01_arnhem_a_e_42=
{
displaytime= 1.11,
text = "Thanks for the assist!",
},
bs4_01_arnhem_a_e_43=
{
displaytime= 1.681,
text = "Medic! See to these wounded!",
},
bs3_01_arnhem_a_e_33=
{
displaytime= 2.262,
text = "Come on! Let's keep moving towards the bridge!",
},
}

```


My job's in Arnhem, by the way  .
## Post #3
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2008-03-23T20:10:39+00:00
- Post Title: Call Of Duty Roads To Victory PSP .RES Text file!!

Can i extract the .txt file translate it to my language an reinsert it into the .res file? will the translate works?

Thanxk for help me!

Sorry my english!
## Post #4
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2008-03-24T20:02:32+00:00
- Post Title: Call Of Duty Roads To Victory PSP .RES Text file!!

someoone?
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-03-24T23:54:11+00:00
- Post Title: Call Of Duty Roads To Victory PSP .RES Text file!!

> Reply from caws
>
> Can i extract the .txt file translate it to my language an reinsert it into the .res file? will the translate works?

Thanxk for help me!

Sorry my english!

Well, you can do that, if you know how to handle stuff like this. It is not automated yet. I just posted the format of the file. You can do it manually in a hex editor though. Perhaps if and when I have time I will create a plugin for MultiEx Commander that can do what you ask for.
## Post #6
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2008-03-25T02:32:53+00:00
- Post Title: Call Of Duty Roads To Victory PSP .RES Text file!!

> Reply from Mr.Mouse
>
> caws wrote:Can i extract the .txt file translate it to my language an reinsert it into the .res file? will the translate works?

Thanxk for help me!

Sorry my english!

Well, you can do that, if you know how to handle stuff like this. It is not automated yet. I just posted the format of the file. You can do it manually in a hex editor though. Perhaps if and when I have time I will create a plugin for MultiEx Commander that can do what you ask for.

thx, i will wait for this plugin!!!
## Post #7
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2008-08-02T16:39:05+00:00
- Post Title: Call Of Duty Roads To Victory PSP .RES Text file!!

Up
