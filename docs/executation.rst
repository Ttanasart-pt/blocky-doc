Code executation
###################

.. toctree::
   :maxdepth: 2

   executation.rst

Concept
*****************************

- All executation start at o_block_start.
- When started, o_block_start run script block_execute_start
- On each block:
    * user_event(0) run once the block is called. 
    * user_event(1) run every step the block is executing.
    * user_event(2) run once when the block finish executing.
    * block_execute_next called for next block.

``block_scope`` (variable)
*****************************

``block_scope`` is an array contain blocks that has ``variable_map`` inside. ``block_scope`` is used to find variable value and target actor. 

.. note::
    ``block_scope`` iterate from last member to first, and break when found. Thus "local" variable will return before global var.