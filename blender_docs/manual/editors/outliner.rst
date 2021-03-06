
********
Outliner
********

.. figure:: /images/editors_outliner.png

   The Outliner editor.


The *Outliner* is a list that organizes data in the blend-file.
i.e. the scene data and also the User Preferences.

.. rubric:: Usage

- View the data in the scene.
- Select and deselect objects in the scene.
- Hide or show an object in the scene.
- Enable or disable selection (to make an object "unselectable" in the 3D View).
- Enable or disable the rendering of an object.
- Delete objects from the scene.
- Unlink data (equivalent to pressing the *X* button next to the name of a data-block).
- Easily select which render layer to render.
- Easily select which render pass to render (for example, you can choose to render just the *Specular* pass).


Tree View
=========

Each row in the *Outliner* shows a data-block. You can click the plus-sign to the
left of a name to expand the current data-block and see what other data-blocks it contains.

You can select data-blocks in the *Outliner*,
but this will not necessarily select the data-block in the scene.
To select the data-block in the scene, you have to activate it.


Selecting and Activating
------------------------

Single selection does not require any pre-selection: just work directly with :kbd:`LMB`
(and/or :kbd:`RMB` - contextual menu, see below) *inside* the name/icon area.

When you select an object in the list this way,
it is selected and becomes the active object in all other 3D Views.


Activating a data-block
^^^^^^^^^^^^^^^^^^^^^^^

To "activate" the data-block with :kbd:`LMB` on the *icon* of the data-block.
Activating the data-block will automatically switch to the relevant mode.
For example, activating the mesh data of the cube will select the cube
and enter *Edit Mode* while activating the object data of the
cube will select the cube and enter *Object Mode* (see right).


Selecting a group of data-blocks
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Useful when you want to select/deselect a whole bunch of data-blocks.
For this you must prepare the selection using, to your liking:

- :kbd:`RMB` or :kbd:`LMB`,
- :kbd:`Shift-RMB` or :kbd:`Shift-LMB`,
- :kbd:`RMB` and drag or :kbd:`LMB` and drag,

all *outside* the name/icon area. Those pre-selected have their line in a lighter color.
You then can (de)select them with a :kbd:`RMB` *on* the name/icon area,
which brings on a context menu (see bellow).

.. figure:: /images/editors_outliner_column-icons.png

   Selection of a data-block.


Context menu
^^^^^^^^^^^^

Show the context menu for a data-block with :kbd:`RMB` on the icon or name.
Depending on the type of the pre-selected data-block(s), you will have all or part of the following options:

- *Select*.
- *Deselect*.
- *Delete* :kbd:`X`.
- *Unlink* - To unlink a data-block from its "owner" (e.g., a material from its mesh).
- *Make Local* - To create a "local" duplicate of this data-block.

.. note::

   Some data-block types will not have a context menu at all!


Object-level Restrictions
-------------------------

The three following toggles, in the right side of the *Outliner* editor,
are only available for objects:

Visibility (eye icon)
   Toggles the visibility of the object in the 3D View.
   :kbd:`V` will toggle this property for any objects that are selected in the *Outliner*.
Selectability (mouse cursor icon)
   This is useful for if you have placed something in the scene
   and do not want to accidentally select it when working on something else.
   :kbd:`S` will toggle this property for any objects that are selected in the *Outliner*.
Rendering (camera icon)
   This will still keep the object visible in the scene, but it will be ignored by the renderer.
   :kbd:`R` will toggle this property for any objects that are selected in the *Outliner*.


Header
======

View Menu
---------

Sort Alphabetically
   Sort the entries alphabetically.
Show Restriction Columns
   Toggles the three columns of `Object-level Restrictions`_.

Show Active
   Centers the Tree View to selected object :kbd:`.`.
Show/Hide One Level
   Expand one level down in the tree :kbd:`NumpadPlus` and :kbd:`NumpadMinus` to collapse.
Show Hierarchy
   To collapse all levels of the tree :kbd:`Home`.


Display Mode
------------

The editors header has a select menu that let you filter what the Outliner should show. It helps to narrow the
list of objects so that you can find things quickly and easily.

All Scenes
   Shows *everything* the *Outliner* can display (in all scenes, all layers, etc.)
Current Scene
   Shows everything in the current scene.
Visible Layers
   Shows everything on the visible (currently selected) layers in the current scene.
   Use the :doc:`layer </editors/3dview/object/properties/relations/layers>` buttons
   to make objects on a layer visible in the 3D View.
Selected
   Lists the object(s) that are currently selected in the 3D View.
   See :doc:`selecting in the 3D View </editors/3dview/object/selecting>` for more information.
Active
   Lists only the active (often last selected) object.
Same Types
   Lists only those objects in the current scene that are of the same types as those selected in the 3D View.
Groups
   Lists only :doc:`Groups </editors/3dview/object/properties/relations/groups>` and their members.
Sequence
   Lists :doc:`data-block </data_system/data_blocks>`
   that are used by the :doc:`Sequencer </editors/sequencer/index>`.
Blender File
   Lists all data in the current blend-file.
Data-Blocks
   Lists every :doc:`data-block </data_system/data_blocks>` along with any properties that they might have.
User Preferences
   Lists options that can be found in the :doc:`User Preferences </preferences/index>`
   along with some other settings.
Orphan Data
   Lists :doc:`data-blocks </data_system/data_blocks>`
   which are unused and/or will be lost when the file is reloaded.


Searching
---------

You can search the view for data-blocks,
by using Search field in the header of the *Outliner*,
The *Search* menu lets you toggle the following options:

- Case Sensitive Matches Only
- Complete Matches Only


.. Edit menu for data-blocks


Example
=======

.. figure:: /images/editors_outliner_example.png

   The Outliner with different kind of data.

