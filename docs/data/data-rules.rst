####################
Data ingestion rules
####################

This document explains how the format we receive data in.
It also details how certain flags, or rules, are applied to the data when ingested.


***************
Available flags
***************

There are two flags available.
These flags are applied to data when ingested.

- **Private data**: Data is private and is only accessible to UNICEF and uploading organization

- **Anonymity**: Uploading organization chooses to remain anonymous

These flags are not inside of the data sets.
The flags must be applied when the data is ingested.


.. seealso::

   See :doc:`data-ingesting` for more information about data ingestion.


**********************
School data file names
**********************

School mapping data is provided in a unique file name format.
Some information must be gathered from the file name.
See this example::

    BR-ProCo-0-MCTIC-0.csv

There are five parts to the file name.

#. **BR**: Country code (BR is Brazil)
#. **ProCo**: Partner (ProCo is `Project Connect <https://github.com/unicef/project-connect>`_)
#. **0**: Sets privacy of data (0 is public, 1 is private)
#. **MCTIC**: Provider (MCTIC is `Ministério da Ciência, Tecnologia, Inovação e Comunicação <http://www.mctic.gov.br>`_)
#. **0**: Sets privacy of uploader (0 is public, 1 is anonymous)


*******
Caveats
*******

Code is not yet written to enforce rules.
We still need to implement permissions based on user information forwarded from Auth0.
