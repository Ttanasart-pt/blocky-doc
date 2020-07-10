Code block
###################

.. toctree::
   :maxdepth: 2

   block.rst
   
.. blocks:

Concept
*****************************

- Each block create connector object before, after it.
- On executation, block start user_event(0)
- While executing run user_event(1) 
- On finish, run user_event(2), and search for next block connected to connector.

p_block (object)
*****************************

Parent object of all blocks.

o_block_temp (object)
*****************************

Template block, duplicate this object if you want to create new block.

important block variables
*****************************

+-----------------------+----------------+------------------------------------+
| name                  | type           | description                        |
+=======================+================+====================================+
| block_w               | real           | block width                        |
+-----------------------+----------------+------------------------------------+
| block_h               | real           | block height                       |
+-----------------------+----------------+------------------------------------+
| block_display         | string         | text to display                    |
+-----------------------+----------------+------------------------------------+
| block_save            | boolean        | save block or not                  |
+-----------------------+----------------+------------------------------------+
| block_value           | array          | default value                      |
+-----------------------+----------------+------------------------------------+
| block_in_value        | array          | default internal value             |
+-----------------------+----------------+------------------------------------+
| is_block              | boolean        | is this block a container          |
+-----------------------+----------------+------------------------------------+
| is_height_child       | boolean        | inherit height of children blocks  |
+-----------------------+----------------+------------------------------------+
| is_connect_before     | boolean        | has connector before it            |
+-----------------------+----------------+------------------------------------+
| is_connect_after      | boolean        | has connector aftee it             |
+-----------------------+----------------+------------------------------------+

``block_display`` (variable)
*****************************
Use {n} to refer to block_value[n]. Don't forget to assign default value for block_value[n] in create script too.