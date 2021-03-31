.. include:: /images.rst

Next - Patrons - Phantom restrictions bug
=========================================


There is a bug in Koha that is creating "phantom" restrictions.

You can identify these restrictions when you open a borrower's account and see a message that says there's a restriction but when you click on the "View restrictions" button, there are no restrictions listed.

This is what the problem looks like:
------------------------------------

|phantom_restrictions_0010.png|


This is the solution:
---------------------

1. In the restrictions tab, click on "Add manual restriction"

  |phantom_restrictions_0020.png|

2. Click on the "Add restriction" button (you can, optionally, make a note about the restriction)

  |phantom_restrictions_0030.png|

3. Then click on "Remove" restriction

  |phantom_restrictions_0040.png|

4. Click "Yes" in the pop-up window to confirm that you do want to remove the restriction

  |phantom_restrictions_0050.png|

5. All restrictions should now be gone

  |phantom_restrictions_0060.png|


What causes this problem:
-------------------------

We believe this is caused by Koha community bug `26208 <https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=26208>`_

This bug causes the removal of restrictions to fail when multiple items are checked out and 1 or more of them is overdue long enough to cause an automatic restriction and then the items are renewed.

There are many things that happen in the database when an item is renewed.  Similarly there are many things that happen in the database when a restriction is added or removed automatically.  As a part of the restriction process, data is added to a field in the borrowers table in a field called "debarments" and there is also a new line added to a table called "borrower_debarments."  In some situations the sequence of events that is happening behind the scenes removes the restriction data from one table, but not the other when items are renewed - but not all of the time - only in certain circumstances.

For the example in the screenshots above:

- The borrower's account was blocked on March 1 when two of the items they had checked out were overdue for more than 35 days and they were sent a "Library account blocked" email.

  |phantom_restrictions_0110.png|
|
- The two items were renewed on March 2.

  |phantom_restrictions_0130.png|
|
- The restriction was removed from the table in the database called "borrower_debarments" but it was not removed from the table called "borrowers."  This is a known bug in Koha and the Koha community is working to solve the problem.  In fact, a patch has been created.  If possible the patch will be added to our system as soon as possible.  It is possible, however, that we may have to wait for the next upgrade for this problem to be permanently fixed.

  The reason that the solution listed above works is because, when you add the new restriction to an account, Koha has to update both tables - borrowers and borrowers_debarments.  When Koha updates those tables, the process of adding and removing debarments recognizes that there is a discrepancy between the two tables and fixes it.  That way when you take off the new restriction, the phantom restriction is no longer there.

  |phantom_restrictions_0140.png|

Report and weekly administrative process to alievate the problem
----------------------------------------------------------------

There is now a process to help identify borrowers that may be affected by this bug and to remove the phantom restrictions.

#. Run report 3482.
#. If the report identifies any results, click on the down arrow in the "Batch operaitions with X visible records" button and choose "Batch patron modification."
#. Once the batch patron modification tool has loaded, check the checkbox to the right of "Restriction expiration" and "Restriction comment" and run the tool.
#. Running the tool should remove the data causing the phantom restriction warnings.  You can test to see if phantom restrictions have been removed by running report 3482 again.
