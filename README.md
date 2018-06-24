About
============================================
**Ragdoll tools** is an addon for generating ragdolls in Blender

<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/img0.PNG"><br><br>
</div>



Getting started
============================================

* Install addon.
* Read this manual.
* Setup scene like this and select armature.


<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/img8.PNG"><br><br>
</div>



* Press ``Spacebar``  ,find  **Ragdoll tools pie menu** and press ``Enter``.
* From pie menu choose **Generate hitboxes**.Press ``F6`` to play with settings.
* Select generated hitboxes  (select one of them and ``Shift-G`` -> **Group** -> **hit_box_group** ).
* Start pie menu again and choose **Generate rigid body constraints** .
* Go to **Properties** -> **Scene** -> **Rigid Body Cache** -> **Bake All Dynamics**
* Start pie menu  and choose **Bake**.
* Start pie menu  and choose **Disconnect**.Then press ``F6`` and check **Delete hitboxes**.
* Play animation



Generate hitboxes
============================================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Generate hitboxes**

<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/s1.png"><br><br>
</div>


This operator generates hitboxes from mesh object or bones.

To generate hitboxes from mesh you should select exactly one mesh object and at least one armature, then set **Generate from :** to **Mesh**
Hitbox shape is based on vertex group,so your mesh should have vertex group with the same names as bones in armatures have,otherwise,nothing happens.
If yor model already parented to armature,you have it.And if not ,you can get them py parenting your object to armature with automatic weights,for example.

Output hitbox shape can be of several different types.

Here how they looks:



<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/modes.png"><br><br>
</div>




To generate hitboxes from bones you should select at least one armature and set **Generate from :** to **Bones**
Hitboxes generated this way can have box or capsule shape.

If you in **Object Mode** all visible bones of all selected armatures are involved in generation.
If you in **Pose mode** , only visible bones of active armature are involved.

You can change size and shape of the generated hitboxes by pressing   ``F6`` after you call operator.


By default,after generation hitboxes connects with the correspondent bones.
If some bones are already connected , hitboxes will not be generated for them.


**What does the connection means**

When bone and hitbox are connected in hitbox rigid body settings appears property **Follow bone**.

<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/img9.PNG"><br><br>
</div>

If it is checked the hit box copies the movement of the bone and if not the bone copies the movement of the hitbox.

But here is some limitation.If hitbox of any bone has **Follow bone** property unchecked,this property should be unchecked  for all  hitboxes that are connected to children of this bone.
If this condition is not satisfied,simulation will be unstable.

Also,when bone follows the hitbox,it is slightly behind ,but this doesn't affects baked animation

Connect existing objects to the bones
=====================================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Connect**


<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/img2.png"><br><br>
</div>



This operator connects selected mesh objects to the nearest visible bones in selected armatures if you are in **Object Mode** or to the nearest visible  bones in active armature  if you are in **Pose mode**

If some bones or objects  are already  connected,they are ignored.

Do not forget to make objects rigid body and add them to group with other hitboxes.





Generate rigid body contraints
==============================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Generate rigid body contraints**



<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/s2.png"><br><br>
</div>



This operator generates rigid body constraints between selected rigid bodies.
Works similar to Blender's  standart  **Tool Shelf** -> **Physics** -> **Connect** operator but with extra properties.

Also has a mode for generating constraints from hierarchy of bones connected to hitboxes.

Bake
====

``Spacebar`` -> **Ragdoll tools pie menu** -> **Bake**

<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/img4.png"><br><br>
</div>


This operator bakes visual transformations into keyframes for connected hitboxes and bones.
Baking usually takes a long time, depending on the number of items that are baked, and the length of the animation.


Disconnect  hitboxes from the bones
===================================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Disconnect**


<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/img3.png"><br><br>
</div>


This operator deletes helpers, drivers and constraints that maintained connection of hitboxes and bones and optionally removes hitboxes


Set rigid body settings
===================================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Set rigid body settings**


<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/img6.png"><br><br>
</div>

This operator modifies  rigid body settings of selected objects

Set rigid body constraint settings
===================================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Set rigid body constraint settings**



<div align="left">
<img   src= "https://raw.githubusercontent.com/xbodya13/random/master/img7.png"><br><br>
</div>


This operator modifies  rigid body settings of selected objects



