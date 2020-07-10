How-to
###################

.. toctree::
   :maxdepth: 2

   howto.rst

Create new block
*****************************

- Duplicate o_block_temp.
- Edit :ref: `blocks`.
- Edit event_user(0, 1, 2).
- Add block to o_builder ``blocks`` array.
- Add thumbnail sprite.

Create actor block
*****************************

- Create new object, set parent to p_actor.
- Edit :ref: `elements:Actors`
- Create text drawing, image surface.
- Add actor to o_builder ``map_elements`` array.
- Add thumbnail sprite.

.. note::
    If the actor is drawable. You have to create ``display_surface`` surface to draw on.

o_builder blocks array
==============================

o_builder has 2 arrays, ``blocks``, and ``map_elements`` for code blocks and elements respectively. Both array use the same syntax.

``["object", "thumbnail sprite", "filter", "build multiple"]``

- **object** : Object to build
- **thumbnail** sprite : thumbnail
- **filter** : see ``fitler_th``, ``map_filter_th`` for filter type (filter use bitwise, so you can make object exist in multiple filter.)
- **build multiple** : (for element) build object by clicking instead of drag and drop.