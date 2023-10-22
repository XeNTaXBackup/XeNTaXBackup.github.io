## Post #1
- Username: okeoii
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 27, 2018 5:44 pm
- Post datetime: 2018-10-27T09:46:30+00:00
- Post Title: Move bind to controller weapons in kh2 model viewer!

Hey does anyone know how to fix some of the bind to controller weapon mdlx? Like rikus is backwards.
## Post #2
- Username: cyberq3000
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 10, 2017 8:09 am
- Post datetime: 2018-12-11T03:58:52+00:00
- Post Title: Move bind to controller weapons in kh2 model viewer!

You have to edit the BindPresent.xml file located in the same folder the model viewer is located.  Rikus right hand joint should be 163.  I think i had to add Riku in the notes.  Your going to have to do the same for other characters that don't have the weapon with the model.


An example would be this.

  <item>
    <display-name>Riku</display-name>
    <body-mdlx>P_EH000.mdlx</body-mdlx>
    <body-mset>P_EH000.mset</body-mset>
    <right-hand-mdlx>W_EH000.mdlx</right-hand-mdlx>
    <right-hand-mset>W_EH000.mset</right-hand-mset>
    <right-hand-joint>163</right-hand-joint>
  </item>


After you save the file and reopen the modelviewer, Riku should be under one of the presets where you Bind Controller.
