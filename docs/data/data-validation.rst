###############
Data validation
###############

Data validation ensures correct and consistent data is processed and aggregated for use in MagicBox.
The validated data is used by implementations of the MagicBox API, such as `magicbox-maps`_.

This article explains how we verify values, identify duplicates, and merge multiple records into one.


************
How we do it
************

.. figure:: https://cdn-images-1.medium.com/max/800/1*WEBHVGUmqRVleyMNNCLp3A.gif

   How `magicbox-latlong-admin-server`_ validates coordinate pairs

Data validation is performed by `magicbox-latlong-admin-server`_.
The server verifies a pair of latitude / longtitude coordinates are located within the country indicated by the beginning of a file name.

The `data validation program`_ processes every ten minutes as a cron job.
It runs a programatic version of this query:

.. code-block:: sql
   :emphasize-lines: 2

   // Do a select on all schools that have not been geo validated
   "SELECT id, lat, lon, country_code FROM schools WHERE date_geo_validated IS null AND lat IS NOT null AND lon IS NOT null"

.. image:: https://cdn-images-1.medium.com/max/1000/1*5cHXnEW4C3qKKAIh0aIbhw.png


Adding new attributes
=====================

After the data is validated, the `magicbox-latlong-admin-server`_ updates attributes for some data.
The attributes are only added if the engine returns an admin area ID for the target country (see :doc:`../administrative-boundaries`).

#. ``date_geo_validated``: To ``CURRENT_TIMESTAMP``

#. ``coords_within_country``: true or false


************
Why we do it
************

Some CSV files we import and aggregate contain tens of thousands of records.
Data validation is an expensive operation.
We chose not to verify each school's coordinates in the ``before_batch_import`` hook for this reason.

Instead, we opted for the `data validation program`_ to run as a cron job every ten minutes to accomplish this.


.. _`magicbox-maps`: https://github.com/unicef/magicbox-maps
.. _`magicbox-latlong-admin-server`: https://github.com/unicef/magicbox-latlong-server
.. _`data validation program`: https://github.com/unicef/validate_geo_coordinates
