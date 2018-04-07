.. IAMGREATPROLISOK documentation master file, created by
   sphinx-quickstart on Thu Apr  5 15:53:05 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

About
============================================
Tools for making ragdoll


.. image:: img0.png


Getting started
============================================

* Install addon.
* Read this manual.
* Setup scene like this and select armature.


.. image:: img8.png




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

.. image:: img1.png

This operator generates hitboxes  from visible bones of the selected armatures if you in **Object Mode** or from visible bones of the active armature only if you in **Pose mode**
You can change size and shape of the generated hitboxes by pressing   ``F6``.


By default,after generation hitboxes connects with the correspondent bones.
If some bones are already connected , hitboxes will not be generated for them.


**What does connection means**

When bone and hitbox are connected in hitbox rigid body settings appears property **Follow bone**.

.. image:: img9.png

If it is checked the hit box copies the movement of the bone and if not the bone copies the movement of the hitbox.

But here is some limitation.If hitbox of any bone has **Follow bone** property unchecked,this property should be unchecked  for all  hitboxes that are connected to children of this bone.
If this condition is not satisfied,simulation will be unstable.

Also,when bone follows the hitbox,it is slightly behind ,but this doesn't affects baked animation

Connect existing objects to the bones
=====================================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Connect**


.. image:: img2.png



This operator connects selected mesh objects to the nearest visible bones in selected armatures if you are in **Object Mode** or to the nearest visible  bones in active armature  if you are in **Pose mode**

If some bones or objects  are already  connected,they are ignored.

Do not forget to make objects rigid body and add them to group with other hitboxes.





Generate rigid body contraints
==============================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Generate rigid body contraints**



.. image:: img5.png



This operator generates rigid body constraints between selected rigid bodies.
Works similar to Blender's  standart  **Tool Shelf** -> **Physics** -> **Connect** operator but with extra properties.

Also has a mode for generating constraints from hierarchy of bones connected to hitboxes.

Bake
====

``Spacebar`` -> **Ragdoll tools pie menu** -> **Bake**


.. image:: img4.png


This operator bakes visual transformations into keyframes for connected hitboxes and bones.
Baking usually takes a long time, depending on the number of items that are baked, and the length of the animation.


Disconnect  hitboxes from the bones
===================================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Disconnect**


.. image:: img3.png


This operator deletes helpers, drivers and constraints that maintained connection of hitboxes and bones and optionally removes hitboxes


Set rigid body settings
===================================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Set rigid body settings**


.. image:: img6.png

This operator modifies  rigid body settings of selected objects

Set rigid body constraint settings
===================================

``Spacebar`` -> **Ragdoll tools pie menu** -> **Set rigid body constraint settings**



.. image:: img7.png


This operator modifies  rigid body settings of selected objects



