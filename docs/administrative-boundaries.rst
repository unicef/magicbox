#########################
Administrative boundaries
#########################

UNICEF uses **administrative boundaries** (or administrative areas) to
define geographic areas in MagicBox and related projects. Administrative
boundaries (ABs) extend the concepts of a country, state, or region.
Examples of an administrative boundary may be…

-  Country
-  State
-  Province
-  County
-  Municipality
-  And more…

ABs come from `GADM <http://gadm.org/>`__ and the `Humanitarian Data
Exchange <https://data.humdata.org/>`__ (HumData), databases of global
administrative areas. In addition, more ABs may come from other sources
like municipal governments. These databases make it easier to work with
this data in GIS or related software.


******
Levels
******

Levels are a hierarchy system to explain different concepts of
administrative boundaries. For example, a city may belong to a
municipality, which belongs to a country. Levels help us explain this
hierarchy.

UNICEF uses this system of levels:

-  **Level 0**: Countries
-  **Level 1**: States
-  **Level 2**: Counties
-  **Level 3**: Municipalities
-  And so on…


***************
Why we use them
***************

Different definitions of geographic areas by different nations makes
worldwide geographic mapping a challenge. Not everyone uses the same
names for regions. In MagicBox projects, each region, or **shape**, is
assigned an ``admin_id``.

An ``admin_id`` is an interpretation of a political border for a
specific time. They point to a specific shape in a shapefile that
represents an individual country. Time is a part of the admin ID to
ingest historical data. For example, mobility or temperature might
require a series from an earlier date where a region was known by a
different name.

See the following example of an AB for Afghanistan, with an
``admin_id``.

.. figure:: https://cdn-images-1.medium.com/max/800/1*wAatd2Qiu5vXYmatpVCcmg.png
   :alt: Example of an administrative boundary for Afghanistan

   Example of an administrative boundary for Afghanistan

To understand where ``afg_1_11_102-gadm2–8`` points to, note that
Afghanistan has three **levels** of administrative boundaries. The
``admin_id`` has three integers, one per admin level:

.. figure:: https://cdn-images-1.medium.com/max/800/1*hGHSrnLcyXdPDDvXje_UsQ.png
   :alt: Afghanistan has three levels of administrative boundaries

   Afghanistan has three levels of administrative boundaries


***********************
Naming string explained
***********************

First integer
=============

The first integer is ``1`` because Afghanistan is the first country in
GADM's database.

.. figure:: https://cdn-images-1.medium.com/max/800/1*9WTComzFpXK2yUk8lNXg8A.png
   :alt: The first few countries in GADM's database

   The first few countries in GADM's database


Second and third integer
========================

Afghanistan has 34 shapes at level one and 320 shapes in level two.

.. figure:: https://cdn-images-1.medium.com/max/800/1*4POtdmBjmF1JZtbuhutDOA.png
   :alt: Afghanistan: Higher level administrative boundaries

   Afghanistan: Higher level administrative boundaries


Putting it together
===================

Thus, ``afg_1_11_102-gadm2–8`` indicates any population value attached
to it is related to:

-  First country in the gadm collection
-  11th shape in the admin level 1 shapefile
-  102nd shape in the admin level 2 shapefile

.. figure:: https://cdn-images-1.medium.com/max/800/1*k6TaJ4I0zk39f24yG_d_WQ.png
   :alt: Putting it together: What the admin ID represents

   Putting it together: What the admin ID represents
