
******************
Particle Edit Mode
******************

Using *Particle Edit Mode* you can edit the key-points (Keyframes)
and paths of *Baked*
:doc:`Hair </physics/particles/hair/index>`,
:doc:`Particle </physics/particles/index>`,
:doc:`Cloth </physics/cloth/index>`, and
:doc:`Soft Body </physics/soft_body/index>` simulations.
(You can also edit and style hair before baking).

Since working in Particle Edit Mode is pretty easy and very similar to working with vertices in the
3D View, we will show how to set up a particle system and then give a reference of the
various functions.


Usage
=====

.. tip:: Only Frames Baked to Memory are Editable!

   If you cannot edit the particles, check that you are not baking to a
   :doc:`Disk Cache </physics/particles/properties/cache>`.


Setup for Hair Particles
------------------------

#. Create a *Hair* particle system.
#. Give it an initial velocity in the *Normal* direction.
#. Create a simulation
#. Check the *Hair Dynamics* box.

.. figure:: /images/physics_particle_mode.png

   Editing hair strands in Particle Edit Mode.

.. figure:: /images/physics_particle_mode_example.gif

   Editing a baked particle simulation's particle paths in Particle Edit Mode.


Setup for Particle, Cloth, and Soft Body Simulations
----------------------------------------------------

#. Use *Emitter* particles, or a cloth/soft-body simulation
#. Create a simulation by setting up objects and or emitters,
   set your time range (use a small range if you are just starting out and experimenting),
   set up the simulation how you want it, using :kbd:`Alt-A` to preview it.


Bake the Simulation
-------------------

Once you are happy with the general simulation, :doc:`bake </physics/particles/properties/cache>`
the simulation from object mode. The simulation must be baked to enable editing.


Edit the Simulation
-------------------

Switch to *Particle Edit* from the *Mode select menu* in the header
of the *3D View* to edit the particle's paths/Keyframes.
You may need to press :kbd:`T` from within the 3D View to see the *Particle Edit* panel.
Move to the frame you want to edit and use the various *Particle Edit* tools to edit your simulation.
Work slowly, previewing your changes with :kbd:`Alt-A`, and save often so that you can go back to the previous
version should something happen, or that you do not like the latest changes you have made.

.. tip:: To be able to clearly see what you are working on:

   #. Open the Options panel in the Tool shelf.
   #. Select *Point select mode* (see below) in the header of the 3D View.
      This will display key points along the particle path.


Selecting
=========

- Single: :kbd:`RMB`.
- All: :kbd:`A`.
- Linked: Move the mouse over a keypoint and press :kbd:`L`.
- Border select: :kbd:`B`.
- First/last: :kbd:`W` :menuselection:`--> Select First / Select Last`.

You may also use the *Select* Menu.

.. tip:: Selections

   Selections are extremely useful for modifying only the particles that you want.
   Hover over a particle path and press :kbd:`L` to link-select it,
   hover over the next and press :kbd:`L` to add that path to the selection.
   To remove a path, hold :kbd:`Shift` and press :kbd:`L`. To Deselect all press :kbd:`A`.

   The method to select individual points is the same as in edit mode.
   :kbd:`RMB` to select, :kbd:`Shift-RMB` to add/remove a point from the selection.


Select Modes
------------

.. figure:: /images/physics_particles_mode_select-modes.png

   Select Modes.

Path
   No keypoints are visible, you can select/deselect only all particles.
Point
   You see all of the keypoints.
Tip
   You can see and edit (including the brushes) only the tip of the particles, i.e. the last keypoint.


Brush
=====

With the buttons you can select the type of "Comb" utility you want to use.
Below the brush types, their settings appear:

None
   No special tool, just edit the keypoints as "normal" vertices.
Comb
   Moves the keypoints (similar to "proportional editing").
Smooth
   Parallels visually adjacent segments.
Add
   Adds new particles.

   Count
      The number of new particles per step.
   Interpolate
      Interpolate the shape of new hairs from existing ones.
   Steps
      Amount of brush steps
   Keys
      How many keys to make new particles with.
Length
   Scales the segments, so it makes the hair longer with *Grow* or shorter with *Shrink*.
Puff
   Rotates the hair around its first keypoint (root).
   So it makes the hair stand up with *Add* or lay down with *Sub*.

   Puff Volume
      Apply puff to unselected end-points, (helps maintain hair volume when puffing root)
Cut
   Scales the segments until the last keypoint reaches the brush.

Weight
   This is especially useful for softbody animations, because the weight defines the softbody *Goal*.
   A keypoint with a weight of 1 will not move at all,
   a keypoint with a weight of 0 subjects fully to softbody animation.
   This value is scaled by the *GMin* to *GMax* range of softbody goals...

   .. Not more true, I think: '''Weight is only drawn for the complete hair (i.e. with the value of the tip),
      not for each keypoint, so it's a bit difficult to paint'''


Options
-------

Common Options:
   Radius
      Set the radius if the brush.

      .. tip:: Brush Size

         Press :kbd:`F` to resize the brush while working.

   Strength
      Set the strength of the brush effect (not for Add brush).
   Add/Sub Grow/Shrink
      Sets the brush to add the effect or reverse it.
Deflect Emitter,
   Do not move keypoints through the emitting mesh.

   Distance
      The distance to keep from the Emitter.
Keep
   Length
      Keep the length of the segments between the keypoints when combing or smoothing the hair.
      This is done by moving all the other keypoints.
   Root
      Keep first key unmodified, so you cannot transplant hair.
X Mirror
   Enable mirror editing across the local x axis.
Draw
   Path Steps
      Drawing steps, sets the smoothness of the drawn path.
   Show Children
      Draws the children of the particles too.
      This allows to fine tune the particles and see their effects on the result,
      but it may slow down your system if you have many children.


Editing
=======

.. warning:: Beware of Undo!

   Using *Undo* in *Particle Edit Mode* can have strange results. Remember to save often!


Moving keypoints or particles
-----------------------------

- To move selected keypoints press :kbd:`G`, or use one of the various other methods to grab vertices.
- To move a particle root you have to turn off Keep *Root* in the Tool Shelf.
- You can do many of the things like with vertices, including scaling,
  rotating and removing (complete particles or single keys).
- You may not duplicate or extrude keys or particles,
  but you can subdivide particles which adds new keypoints
  :kbd:`W` :menuselection:`--> Subdivide`or :kbd:`Numpad2`.
- Alternatively you can rekey a particle
  :kbd:`W` :menuselection:`--> Rekey` or :kbd:`Numpad1` and choose the number of keys.

How smoothly the hair and particle paths are displayed depends on the *Path Steps*
setting in the Tool Shelf. Low settings produce blocky interpolation between points,
while high settings produce a smooth curve.


Mirroring Particles
-------------------

If you want to create an X-Axis symmetrical haircut you have to do following steps:

- Select all particles with :kbd:`A`.
- Mirror the particles with :kbd:`Ctrl-M`, or use the :menuselection:`Particle --> Mirror` menu.
- Turn on *X-Axis Mirror Editing* in the *Particle* menu.

It may happen that after mirroring two particles occupy nearly the same place.
Since this would be a waste of memory and rendertime,
you can *Remove doubles* either from the *Specials* :kbd:`W`
or the *Particle* menu.


Hiding/Unhiding
---------------

Hiding and unhiding of particles works similar as with vertices in the 3D View.
Select one or more keypoints of the particle you want to hide and press :kbd:`H`.
The particle in fact does not vanish, only the key points.

Hidden particles (i.e. particles whose keypoints are hidden)
do not react on the various brushes. But:

If you use *Mirror Editing* even particles with hidden keypoints may be moved,
if their mirrored counterpart is moved.

To un-hide all hidden particles press :kbd:`Alt-H`.


Unify Length
------------

This tool is used to make all selected hair uniform length by finding the average length.
