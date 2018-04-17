############################
Ingesting data into MagicBox
############################

Importing new data sets to MagicBox is important for expanding coverage and how we retrieve new data insights.
This document explains how we ingest and import new data to MagicBox.


*********************
School data ingestion
*********************

Data for schools comes in CSV files with a specific naming scheme.
We developed a Ruby on Rails-based CRUD [#]_ application, `Project Connect`_ to ingest this data.

There are two admin interfaces for Rails applications:

- Rails Admin

- Active Admin

Active Admin has an `import plugin`_ for uploading CSVs with ``before_batch_import`` support.
We chose Active Admin for this reason.

.. image:: /_static/data-ingesting-import-csv-rails.png


********************
School data database
********************

MagicBox needed a database to manage large amounts of school data and process it quickly.
To do this, MagicBox uses a relational database, `PostgreSQL`_, to store data.
PostgreSQL was chosen because it was used in a tutorial for building a similar use case as ours (thus, a relational database is not a "married" idea).

All school data is stored in a single table named ``schools``.
This keeps things simple at the expense of some repeated values in the database.

Inserted data
=============

When data is imported, new data is inserted alongside the imported data.
Four new types of important data are added:

- Provider / owner of school CSV data

- Organization that received school data

- Identity of uploader

- If uploader chooses to remain private

.. image:: /_static/data-ingesting-added-columns.png

These values are not included with the data.
We use the ``before_batch_import`` hook in Active Admin to parse file names, insert this data, and assign values.

.. figure:: /_static/data-ingesting-code-inserting-data.png

   Implementation of how data is modified before imported. See `schools.rb`_


.. [#] Create, Read, Update, Delete
.. _`Project Connect`: https://github.com/unicef/project-connect
.. _`import plugin`: https://github.com/activeadmin-plugins/active_admin_import
.. _`PostgreSQL`: https://www.postgresql.org/
.. _`schools.rb`: https://github.com/unicef/project-connect/blob/master/app/admin/schools.rb
