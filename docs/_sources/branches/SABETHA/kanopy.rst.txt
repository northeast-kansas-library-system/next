Kanopy Allowed attribute at SABETHA
===================================

Whenever a patron logs into an outside service like Kanopy or Hoopla or Lynda.com, that web service talks to our catalog through a connection called SIP2 to verify that the patron has an account and that they are allowed to access their service.  The information that is transmitted across this connection includes some parts of the patron's contact information including the patron's home library.  The problem we have with Kanopy, however, is that, because of the way the receiving end of the Kanopy SIP2 connection is configured, Kanopy cannot determine what the patron's home library is through the normal SIP2 process.  Because of this, we need to send the patron's home library through an alternate route.  To make this happen, we've created a new field in the "Permissions" section on a patron's account called "Kanopy (SABETHA)."

The new "Kanopy (SABETHA)" permission will have 3 options

- [blank]
- Not allowed
- Allowed (Sabetha, Mary Cotton Library)

These three options will only be available to staff logged in at SABETHA in order to prevent staff at other libraries from granting permission to access the Mary Cotton Library's Kanopy service to their patrons.

This will affect staff and patrons in two ways:

#. When staff at SABETHA create a new account for a patron, the patron's "Kanopy (SABETHA)" permission needs to be set to "Allowed (Sabetha, Mary Cotton Library)" if their home library is SABETHA or "Not allowed" if their home library is not SABETHA.  This should happen automatically when a new patron is created.
#. If staff at another library change a patron's home library, staff at SABETHA will need to update the patron's "Kanopy (SABETHA)" settings to "Allowed (Sabetha, Mary Cotton Library)" if the patron's new home library is SABETHA or"Not allowed" if the patron's new home library is no longer SABETHA.  This process cannot happen automatically because only SABETHA staff have access to the "Kanopy (SABETHA)" permission settings.  Reports will be set up to help SABETHA staff manage this process.

Creating a new account
----------------------

When logged in at Mary Cotton Library, click on "Patrons"

.. image:: ../SABETHA/images/kanopy.sabetha.010.png

Then click on the appropriate category on the "New patron" button

.. image:: ../SABETHA/images/kanopy.sabetha.020.png

Then go through your normal process for creating a new patron

.. image:: ../SABETHA/images/kanopy.sabetha.030.png

By default, the patron's home library should be set to SABETHA and the patron's "Kanopy (SABETHA)" permission should, by default, be set to "Sabetha, Mary Cotton Library"

.. image:: ../SABETHA/images/kanopy.sabetha.040.png

If you change the patron's home library from to anything besides SABETHA, the "Kanopy (SABETHA)" permission should automatically switch to "Not allowed"

.. only:: html

   .. image:: ../SABETHA/images/kanopy.sabetha.050.gif

However, if you chage a patron's "Kanopy (SABETHA)" permission manually, the patron's home library will not update automatically.


Running reports to manually update Kanopy Permission
----------------------------------------------------

SABETHA patrons without Kanopy access
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If a new patron with a SABETHA home library is added at a library not logged in as SABETHA, the new patron's "Kanopy (SABETHA)" settings will be left blank and the patron will not be able to access Kanopy.  In order to identify these patrons, staff at SABETHA will need to regularly run report 3368.

.. image:: ../SABETHA/images/kanopy.sabetha.060.png

.. image:: ../SABETHA/images/kanopy.sabetha.070.png

Non-SABETHA patrons with Kanopy access
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If an existing patron who has Kanopy access changes their home library, that patron's Kanopy access needs to be removed from their account manually.  If the change to their account happens and staff is not logged in at SABETHA, staff will not be able to remove the "Kanopy (SABETHA)" status.  In order to identify these patrons, staff at SABETHA will need to regularly run report 3371.

.. image:: ../SABETHA/images/kanopy.sabetha.080.png

.. image:: ../SABETHA/images/kanopy.sabetha.070.png
