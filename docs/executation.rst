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

``block_execute_next``
**********************************

Argument:
- block : Block to find.

Description:
Find next block to execute. Most of the time it will just find the parent of the ``connecting`` variable of ``conn_after``.

.. note::
    This script shouldn't be edit unless to add new block with unconventional block flow.

``variable_get_scope`` 
**********************************

Argument:
- var_str : Variable string.
- var_scope : Block scope to search for.

Description:
Find value of variable in the given scope.

.. note::
    ``block_scope`` iterate from last member to first, and break when found. Thus "local" variable will return before global var.

``variable_assign_scope`` 
**********************************

Argument:
- var_str : Variable string.
- val : Value to assign to.

Description:
Assign value to variable, create new variable if not existed. This script doesn't  have ``var_scope``, but use ``block_scope`` directly, will change in the next update. 

``block_statement_eval`` 
**********************************

Argument:
- str : Statement string.
- var_scope : Block scope to search variable for.

Description:
Evaluate any equation. Return 0 if failed.  
