##############
Access control
##############

Information about schools can be sensitive.
Potential bad actors could use school data for malicious purposes and terrorism.
How school data is shared outside of the API is important.

MagicBox uses `Auth0`_ to authenticate users and assign them roles.


******
Tokens
******

Auth0 creates tokens for users authenticating to the API.
A user may make a request with their token like this.

.. code-block:: bash

   curl -i localhost:8000/api/v1/schools/countries/GL -H "Token: Bearer xxxxxxxxxx9gek6Z5Ilnkx"

After receiving the token, UNICEF reviews the applicant before privileges are granted.
Once our API receives the token, we pass it to Auth0 which returns the user's profile and roles.

.. image:: /_static/data-access-control-receive-token.png


*****
Rules
*****

General rules can be assigned by email domain via Auth0.

.. figure:: /_static/data-access-control-code-email-domains.png

   Code that implements checking for the email domain of a user


.. seealso::

   See :doc:`data-rules` for more information about data rules.


.. _`Auth0`: https://auth0.com/
