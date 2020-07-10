Code executation
====================

Concept
--------------

- All executation start at o_block_start.
- When started, o_block_start run script block_execute_start
- On each block:
    * user_event(0) run once the block is called. 
    * user_event(1) run every step the block is executing.
    * user_event(2) run once when the block finish executing.
    * block_execute_next called for next block.

block_scope (variable)
--------------------------

Block scope is an array contain block that has "variable_map" inside. block_scope is used to find variable value and target actor. 

block_execute_next (script)
--------------------------------

arguments
- block : block to find.

description
A script to find next block to execute. This script shouldn't be edit unless to add new block with unconventional block flow.
