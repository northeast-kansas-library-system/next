2022.01.28 - Agenda and notes
=============================

2022.01.27 - 10:00 a.m. - 12:00 p.m. |ss| NEKLS office |se| + **meeting changed to online only** |br|
`Zoom link <https://kslib.zoom.us/j/93637660486?pwd=RTVQR20xVWIvTXpVQXBqTHBPUXpTZz09>`_ |br|
Zoom passcode 7858384090 |br|
No recording of this meeting will be made |br|


1. Announcements, news, brief items, etc.
  - Introductions
  - Additions to the agenda

2. Changes to passwords for "System login only" and "Library associate (exempt)"

  - Any "System login only" or "Library associate (exempt)" must meet these criteria:

      - New passwords must be between 14 and 89 characters long
      - 1 capital letter
      - 1 small letter
      - 1 numeral [0,1,2,3,4,5,6,7,8,9]
      - Passwords *may* contains spaces and punctuation
  - This only affects passwords that are changed after January 16, 2022
  - Directors can log in with their BRANCH_DIRECTOR account and update these passwords see `this YouTube video <https://youtu.be/ghYELKisCik>`_ or `this PDF <https://northeast-kansas-library-system.github.io/next/files/2105.training/2105.directorpasswordsearch.pdf>`_ for more information
  - A link to both of these documents is in a message on each director account

3. Upgrade problem 1 - Printing problems
  - This is a Firefox problem - not a Koha problem
  - Fix is at `this link <https://northeast-kansas-library-system.github.io/next/bugs/ff87_pop_up.html>`_
  - Greg and George can also remote in to perform this fix

4. Upgrade problem 2 - Placing multiple requests in the staff client
  .. Two libraries have reported this problem

5. Upgrade problem 3 - Item level requests
  .. Sort of patched - be aware

6. 2021 statistics - changes - plans for 2022
  - Errors in the SQL for reports from past years were discovered - some things were double-counted

  - The reports that were used this year are:
    - 2866, 2867, 2868, 3018
    - Circulation data was collected using the monthly reports

7. Changes to item types and item type codes - ongoing
  - IMLS wants separate statistics for realia at the end of the year
  - The easiest way to incorporate this change is by altering item type codes - some item type names also changed

8. Changes to item types - bibliographic frameworks
  - The list of available item types on the bibliographic frameworks has also changed
  - "Temporary" item types were removed

9. Best practice - What to do when an item is returned with "No barcode found" message
  - History of the problem - those darned Koha developers
  - What's being done - koha-US is funding an enhancement that will fix the problem
  - What to do in the meantime

      - Double check to make sure the item really is "No barcode found"
      - Run report 3009 - this report has been substantially updated
      - Does your library policy say anything on the subject?

10. New feature to be turned on after configuration - Hold waiting reminder
  - Koha can now send a "You still have a hold waiting" message X days after the item has been put on the hold shelf
  - Follows the same sending rules as the "Hold arrived" notices
  - These notices need to be set up and configured before we turn this feature on

11. Next meetings in 2022
  - January 27 (Thursday 10:00 a.m.) - online only
  - April 28 (Thursday 10:00 a.m.) - online only
  - August 30 (Tuesday 10:00 a.m.) - NEKLS office / online
  - November 17 (Thursday 10:00 a.m.) - Leavenworth Public Library / online

.. |ss| raw:: html

    <strike>

.. |se| raw:: html

    </strike>

.. |br| raw:: html

    <br />
