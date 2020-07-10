Script reference
###################

.. toctree::
   :maxdepth: 2

   reference.rst


SAVE-LOAD **doesn't work**
*******************************************

``level_save``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **path** : Path to save file to.

Description:
Serialize all objects to JSON, then save in a given location. 

``level_load``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **path** : File path to load.

Description:
Read JSON file then deserialize into object.

draw
*******************************************

``fx_text``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **x** : X position of text box.
- **x** : X position of text box.
- **text** : Text to display.
- **halign** : Text horizontal alignment.
- **valign** : Text vertical alignment.
- **gui** : Draw on gui.
- color : Text color.
- font : Text font.
- width : Text box width (default none).

Description:
Draw text box on the given position. Text, box alignment is calculated automatically.


function
*******************************************

ds/ ``ds_list_create_from_array``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **array** : Array of data.

Description:
Create ds_list containing all members in the given array.

ds/ ``array_create_from_list``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **list** : List of data.

Description:
Create array containing all members in the given ds_list.

``check_object``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **object** : Object to check.

Description:
Quick way to check if object is not undefined, noone and exist (Use before calling instance variable to aviod crash.)

``check_objects``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **objects** : Objects to check (multiple up to 16 objects.)

Description:
Check of all objects given existed.

``in_range``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **var** : Value to check.
- **from** : First bound to check.
- **to** Second bound to check.
- include_from : From inclusive (default false)
- include_to : To inclusive (default false)

Description:
Check if given value fall in between from and to.

``lerp_float``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **from** : Value to lerp from.
- **to** : Value to lerp to.
- **speed** : Lerping speed (higher = slower).
- precise : Use precise. (default false)

Description:
Lerp smoothly to a given value. Usually return back to ``from`` variable, for example : ``a = lerp(a, b, 5)``

``string_digit_decimal``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **string** : String to check.

Description:
Remove all letter (except decimal point) from the string. 

``string_start_with``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **str** : String to check.
- **sta** : Starting string.

Description:
Check if string ``str`` started with ``sta`` or not.


block
*******************************************

``block_move``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **block** : Block to move.
- **dx** : Move X.
- **dy** : Move Y.

Description:
Move block recursively (move all connected block after it too.)

``block_get_next``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **from_block** : Block to find next.
- get_in_block : Get block in container (default false)

Description:
Get block connected after ``from_block``. ``get_in_block`` if true will select block inside container, if false will select block after ``end_block``. 

``block_execute_start``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Description:
Start executing on the current block.

``block_execute_next``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Argument:
- **from_block** : Block to execute next.

Description:
Find next block to execute. Most of the time it will just find the parent of the ``connecting`` variable of ``conn_after``.

.. note::
    This script shouldn't be edit unless to add new block with unconventional block flow.

``block_check_connectors``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **block** : Block to check.

Description:
Check all connector of that block for connection.

``block_draw_text_syntax``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **x** : X position to draw.
- **y** : Y position to draw.
- **string** : Text to draw.

Description:
Draw string at x, y with syntax coloring.


statement
*******************************************

input evaluation/ ``shunting_yard``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **statement** : String to evaluate.

Description:
Convert single string into reverse polish notation using shunting yard algorithm in ds_queue form. 

input evaluation/ ``shunting_evaluate``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **output** : Output queue (from ``shunting_yard``)
- **eval_stack** : Evaluated stack.
- **variable_scope** : Evaluator scope array (``block_scope``).

Description:
Calculate value from ``shunting_yard``. If done correctly the result will be the only data in ``eval_stack``.

input evaluation/ ``block_statement_eval``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **str** : Statement string.
- **var_scope** : Block scope to search variable for.

Description:
Evaluate and return an equation. Return 0 if failed.  

input evaluation/ ``equation_eval``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **sign** : Symbol
- **var** : Value array

Description:
Calculate value respective to ``sign``.

input evaluation/ ``variable_assign_scope``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **var_str** : Variable string.
- **val** : Value to assign to.

Description:
Assign value to variable, create new variable if not existed. This script doesn't  have ``var_scope``, but use ``block_scope`` directly, will change in the next update. 

``function_collect``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Description:
Search and collect all function blocks into ``function_map``.

``variable_get_scope``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **var_str** : Variable string.
- **var_scope** : Block scope to search for.

Description:
Find value of variable in the given scope.

``to_string``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **val** : Value

Description:
Convert value to string.

``show_autocomplete``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **x** : X position to show.
- **y** : Y position to show.
- **str** : String to check for.

Description:
Open autocomplete form at x, y, and search for string ``str``.

``autocomplete_collect``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Description:
Search and collect all variables into autocomplete ``auto_var`` list.


actor
*******************************************

``move_try``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **object** : Actor to move.
- **dx** : distance to move in X axis.
- **dy** : distance to move in Y axis.

Description:
Move actor by dx, dy if that place is movable.

``actor_display``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Arguments:
- **actor** : Actor to show text.
- **string** : String to display.

Description:
Make actor clear latest text and display new string.