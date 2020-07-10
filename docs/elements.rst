Element
###################

.. toctree::
   :maxdepth: 2

   element.rst

Element, or level element, are object in the level that is not code block.

Actors
*****************************

Actors are elements that can assign logic, code block directly. Every actor will automatically generate o_block_start on creation.

important actor variables
==============================

+-----------------------+----------------+------------------------------------------+
| name                  | type           | description                              |
+=======================+================+==========================================+
| xstart, ystart        | real           | Staring x, y position                    |
+-----------------------+----------------+------------------------------------------+
| ia_start              | real           | Staring image angle                      |
+-----------------------+----------------+------------------------------------------+
| move_speed            | real           | Movement speed (should be higher than 0) |
+-----------------------+----------------+------------------------------------------+
| is_drawable           | boolean        | Can the actor draw image.                |
+-----------------------+----------------+------------------------------------------+

.. note::
    Text displaying and image drawing algorithm need to be implement per actor.

Items
*****************************

Items are elements that can be interact by the player, but doesn't have any logic in itself, for example, a button. Item will generate state getting function
(``get("object_state")``) when created.


Props
*****************************

Props are other element that cannot be assign any logic in it, but actor can interact with props, for example, solid props can prevent object from moving, etc.