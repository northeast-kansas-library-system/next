.. include:: /images.rst

Kanopy Allowed attribute at BASEHOR
===================================

Whenever a patron logs into an outside service like Kanopy or Hoopla or Lynda.com, that web service talks to our catalog through a connection called SIP2 to verify that the patron has an account and that they are allowed to access their service.  The information that is transmitted across this connection includes some parts of the patron's contact information including the patron's home library.  The problem we have with Kanopy, however, is that, because of the way the receiving end of the Kanopy SIP2 connection is configured, Kanopy cannot determine what the patron's home library is through the normal SIP2 process.  Because of this, we need to send the patron's home library through an alternate route.  To make this happen, we've created a new field in the "Permissions" section on a patron's account called "Kanopy (BASEHOR)."

The new "Kanopy (BASEHOR)" permission will have 3 options

- [blank]
- Not allowed
- Allowed (Basehor Community Library)

These three options will only be available to staff logged in at BASEHOR in order to prevent staff at other libraries from granting permission to access the Basehor Community Library's Kanopy service to their patrons.

This will affect staff and patrons in two ways:

#. When staff at BASEHOR create a new account for a patron, the patron's "Kanopy (BASEHOR)" permission needs to be set to "Allowed (Basehor Community Library)" if their home library is BASEHOR or "Not allowed" if their home library is not BASEHOR.  This should happen automatically when a new patron is created.
#. If staff at another library change a patron's home library, staff at BASEHOR will need to update the patron's "Kanopy (BASEHOR)" settings to "Allowed (Basehor Community Library)" if the patron's new home library is BASEHOR or"Not allowed" if the patron's new home library is no longer BASEHOR.  This process cannot happen automatically because only BASEHOR staff have access to the "Kanopy (BASEHOR)" permission settings.  Reports will be set up to help BASEHOR staff manage this process.

Creating a new account
----------------------

When logged in at Basehor Community Library, click on "Patrons"

  |kanopy.basehor.010.png|

Then click on the appropriate category on the "New patron" button

  |kanopy.basehor.020.png|

Then go through your normal process for creating a new patron

  |kanopy.basehor.030.png|

By default, the patron's home library should be set to BASEHOR and the patron's "Kanopy (BASEHOR)" permission should, by default, be set to "Basehor Community Library"

  |kanopy.basehor.040.png|

If you change the patron's home library from to anything besides BASEHOR, the "Kanopy (BASEHOR)" permission should automatically switch to "Not allowed"

  .. only:: html

     |kanopy.basehor.050.gif|

However, if you chage a patron's "Kanopy (BASEHOR)" permission manually, the patron's home library will not update automatically.


Running reports to manually update Kanopy Permission
----------------------------------------------------

BASEHOR patrons without Kanopy access
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If a new patron with a BASEHOR home library is added at a library not logged in as BASEHOR, the new patron's "Kanopy (BASEHOR)" settings will be left blank and the patron will not be able to access Kanopy.  In order to identify these patrons, staff at BASEHOR will need to regularly run report 3522.

  |kanopy.basehor.060.png|

  |kanopy.basehor.070.png|

Non-BASEHOR patrons with Kanopy access
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If an existing patron who has Kanopy access changes their home library, that patron's Kanopy access needs to be removed from their account manually.  If the change to their account happens and staff is not logged in at BASEHOR, staff will not be able to remove the "Kanopy (BASEHOR)" status.  In order to identify these patrons, staff at BASEHOR will need to regularly run report 3523.

  |kanopy.basehor.080.png|

  |kanopy.basehor.070.png|
