.. include:: /images.rst

Kanopy Allowed attribute at ATCHISON
===================================

Whenever a patron logs into an outside service like Kanopy or Hoopla or LinkedIn Learning, that web service talks to our catalog through a connection called SIP2 to verify that the patron has an account and that they are allowed to access their service.  The information that is transmitted across this connection includes some parts of the patron's contact information including the patron's home library.  The problem we have with Kanopy, however, is that, because of the way the receiving end of the Kanopy SIP2 connection is configured, Kanopy cannot determine what the patron's home library is through the normal SIP2 process.  Because of this, we need to send the patron's home library through an alternate route.  To make this happen, we've created a new field in the "Permissions" section on a patron's account called "Kanopy (ATCHISON)."

The new "Kanopy (ATCHISON)" permission will have 3 options

- [blank]
- Not allowed
- Allowed (Atchison Public Library)

These three options will only be available to staff logged in at ATCHISON in order to prevent staff at other libraries from granting permission to access the Atchison Public Library's Kanopy service to their patrons.

This will affect staff and patrons in two ways:

#. When staff at ATCHISON create a new account for a patron, the patron's "Kanopy (ATCHISON)" permission needs to be set to "Allowed (Atchison Public Library)" if their home library is ATCHISON or "Not allowed" if their home library is not ATCHISON.  This should happen automatically when a new patron is created.
#. If staff at another library change a patron's home library, staff at ATCHISON will need to update the patron's "Kanopy (ATCHISON)" settings to "Allowed (Atchison Public Library)" if the patron's new home library is ATCHISON or"Not allowed" if the patron's new home library is no longer ATCHISON.  This process cannot happen automatically because only ATCHISON staff have access to the "Kanopy (ATCHISON)" permission settings.  Reports will be set up to help ATCHISON staff manage this process.

Creating a new account
----------------------

When logged in at Atchison Public Library, click on "Patrons"

  |kanopy.atchison.010.png|

Then click on the appropriate category on the "New patron" button

  |kanopy.atchison.020.png|

Then go through your normal process for creating a new patron

  |kanopy.atchison.030.png|

By default, the patron's home library should be set to ATCHISON and the patron's "Kanopy (ATCHISON)" permission should, by default, be set to "Atchison Public Library"

  |kanopy.atchison.040.png|

If you change the patron's home library from to anything besides ATCHISON, the "Kanopy (ATCHISON)" permission should automatically switch to "Not allowed"

  .. only:: html

     |kanopy.atchison.050.gif|

However, if you chage a patron's "Kanopy (ATCHISON)" permission manually, the patron's home library will not update automatically.


Running reports to manually update Kanopy Permission
----------------------------------------------------

ATCHISON patrons without Kanopy access
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If a new patron with a ATCHISON home library is added at a library not logged in as ATCHISON, the new patron's "Kanopy (ATCHISON)" settings will be left blank and the patron will not be able to access Kanopy.  In order to identify these patrons, staff at ATCHISON will need to regularly run report 3520.

  |kanopy.atchison.060.png|

  |kanopy.atchison.070.png|

Non-ATCHISON patrons with Kanopy access
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If an existing patron who has Kanopy access changes their home library, that patron's Kanopy access needs to be removed from their account manually.  If the change to their account happens and staff is not logged in at ATCHISON, staff will not be able to remove the "Kanopy (ATCHISON)" status.  In order to identify these patrons, staff at ATCHISON will need to regularly run report 3521.

  |kanopy.atchison.080.png|

  |kanopy.atchison.070.png|
