##################
Data visualization
##################

MagicBox is a full-stack application.
While the back-end API (`magicbox-open-api`_) serves the data and makes it available for querying, the `magicbox-maps`_ application visualizes the data inside a world map.


************
How we do it
************

`magicbox-maps`_ draws the plot points using OpenStreetMap `Leaflet`_ and `WebGL`_.
WebGL allows us to render up to `16 million clickable points`_ at once.

To do this inside of a `React`_ application like ``magicbox-maps``, we created `react-webgl-leaflet`_.
This React module enables us to render several plot points simultaneously, like we use for the school mapping data.
Every school is represented with a unique, clickable point.

.. figure:: /_static/data-visualization-webgl.png

   `react-webgl-leaflet`_ npm module

This is currently used for `magicbox-maps`_.


************
Why we do it
************

Originally, we began using `Leaflet`_ markers.
This worked well for Mauritania with 2,936 schools.
However, when we moved to Colombia with 49,020 schools, performance took a significant hit.
We experimented with a few other options, like heatmaps and clustering.

.. image:: /_static/data-visualization-method-comparison.png

In the end, we decided on using `WebGL`_, as explained above.


.. _`magicbox-open-api`: https://github.com/unicef/magicbox-open-api
.. _`magicbox-maps`: https://github.com/unicef/magicbox-maps
.. _`Leaflet`: http://leafletjs.com/
.. _`WebGL`: https://www.khronos.org/webgl/
.. _`16 million clickable points`: https://stackoverflow.com/questions/16830824/google-maps-using-three-js-and-webgl/27653983#27653983
.. _`React`: https://reactjs.org/
.. _`react-webgl-leaflet`: https://github.com/unicef/react-webgl-leaflet
