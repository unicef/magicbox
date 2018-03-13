######################
Querying MagicBox data
######################

The MagicBox API (`magicbox-open-api`_) serves different sets of data through
its API. Currently, five datasets are available.

- Cases
- Mobility
- Mosquitoes
- Population
- Schools

The benefit of querying this data is to analyze and cross different data sets
together. For example, this is done in `magicbox-maps`_, where population and
mosquito prevelance data are crossed together.

This document explains how the API works but does not document how to use it.
For more information on using the API, see the `magicbox-open-api`_ repository.


*****
Cases
*****

.. note::

   This section needs to be written.

********
Mobility
********

.. note::

   This section needs to be written.

**********
Mosquitoes
**********

.. note::

   This section needs to be written.

**********
Population
**********

.. note::

   This section needs to be written.

*******
Schools
*******

The MagicBox API also serves data about schools. The public repositories contain
sample data from private data sets; however, in the interest of the privacy and
safety of the schools, the full data sets are kept private.

How we do it
============

There are three endpoints for querying school data. They serve the following
data:

#. List of countries with school data
#. Schools in a country
#. Specific school data by ID value

The first endpoint returns a comma-seperated list of country codes. There is
available data about schools in the countries returned in the list.

The second endpoint returns an array of arrays, where

- First array returns column names (e.g. ``lat``, ``lon``,
  ``speed_connectivity``, ``type_connectivity``)
- Subsequent arrays return values for school records

The third endpoint returns column values from a specific school, as selected by
its ID number. Some of the values available are listed below:

- Address
- Network connectivity
- Number of teachers
- Number of students
- If electricity is available
- If running water is available
- And more

.. figure:: /_static/data-querying-school-data.png

  Example of output from third endpoint inside of a front-end utilizing the API 


*******
Caveats
*******

There are some caveats with querying the MagicBox API.

- Cannot specify or limit columns included in response
- Cannot request values where value is null
- Cannot use operators (e.g. greater than, less than, etc.)


.. _`magicbox-open-api`: https://github.com/unicef/magicbox-open-api
.. _`magicbox-maps`: https://github.com/unicef/magicbox-maps
