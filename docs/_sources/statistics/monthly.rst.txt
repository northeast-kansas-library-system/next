.. include:: /images.rst

Monthly statistical data
=======================

Spreadsheet reports
-------------------

The Next Search Catalog Coordinator endeavors to publish statistics for the prior month by the 5th workday of each month.

The data to generate these spreadsheets are collected monthly and saved in spreadsheets to make the data more accurate.  Because we purge older data from our system regularly, it is very difficult to gather data reliably and accurately once the data gets older.  Since we purge some data when it is more than 13 months old (in an effort to keep the database size as small as possible - which improves the speed of the system) for some questions, it is impossible to gather the data to answer those questions after 13 months have passed.  By gathering data into spreadsheets regularly, data can be saved outside of the dynamic MYSQL database in the system.

Monthly statistics - Excel spreadsheet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Spreadsheets exist for 2017, 2018, 2019, and 2020

This spreadsheet has 16 visible tabs

- YTD totals
- Items added summary
- Items weeded summary
- Monthly tabs (1 tab for each month of the year)
- NEKLS executive board
- Intranetmain


The columns for each monthly tab represent the following data:

#. Total items owned 2021.01.01 (column B)

    - This data comes from in the "Total items at end of month" column from December of the previous year.

#. Total items at the beginning of the month (column C)

    - Data gathered from the "START_I" column of Report 3418
    - This report counts items in the items table where the date accessioned was before the first day of the previous month and it counts items in the deleted items table where the date accessioned was before the first date of the previous month and the date deleted was after the first day of the month (i.e. the item was added **and** deleted during the same month).

#. Total items at end of month (column D)

    -Data gathered from the "END_I" column of Report 3418
    - This report counts items in the items table where the date accessioned was before the last day of the month and it counts items in the deleted items table where the item was in the catalog at the end of the last month but was deleted before the report was run (i.e. items that were deleted at the beginning of the month you're running the report).

#. Items added this month (column D)

    - Data gathered from the "ITEMS_ADD_L_M" column of Report 3418
    - This report counts items in the items and in the deleted items table where the date accessioned was during the previous month.

#. Items deleted this month (column F)

    - Data gathered from the "ITEMS_DEL_L_M" column of Report 3418
    - This report counts items in the deleted items table where the timestamp is sometime during the previous month.  Because this report relies on the timestamp in the deleted items table, the data may be inaccurate in months when a Koha upgrade took place.

#. Total titles at end of month (column G)

    - Data gathered from the "TOTAL_HOLDINGS" column of Report 3418
    - This report counts distinct biblionumbers in the items table.  It also counts distinct biblionumbers in the deleted items table where the deleted item had been added before the last day of the month and deleted after the new month began.

#. Bibliographic records added this month (column H)

    - Data gathered from the "HOLD_ADD_L_M" column of Report 3418
    - This report counts distinct biblionumbers in the items table where the data in the biblios table indicates that the bibliographic record was created in the previous calendar month.

#. Bibliographic records deleted this month (column I)

    - Data gathered from the "HOLD_DEL_L_M" column of Report 3418
    - This report counts distinct biblionumbers in the deleted items table where the data in the deleted biblios table indicates that the bibliographic record was deleted in the previous calendar month.  Like deleted items, because this report relies on the timestamp in the deleted biblios table, the data may be inaccurate in months when a Koha upgrade took place.

#. Check-outs and renewals this month (column J)

    - Data gathered from the "CHECKOUT_RENEW_LM" column of Report 3419
    - This report counts rows from the statistics table where the timestamp indicates the transaction happened during the previous month and the statistic type is "issue" or "renew."

#. Check-outs this month (column K)

    - Data gathered from the "CHECKOUT_LM" column of Report 3419

#. Renewals this month (column L)

    - Data gathered from the "RENEW_LM" column of Report 3419

  #. Returns this month (column M)

      - Data gathered from the "RETURN_LM" column of Report 3419

#. Adult checkouts and renewals this month (column N)

    - Data gathered from the "CR_ADULT_LM" column of Report 3419
    - This report counts rows from the statistics table where the timestamp indicates the transaction happened during the previous month, the item's location was like "%ADULT%," "BALDADULT," "LVPLADULT," or "PAOLAADULT" and the statistic type is "issue" or "renew."

#. Youth checkouts and renewals this month (column O)

    - Data gathered from the "CR_YOUTH_LM" column of Report 3419
    - This report counts rows from the statistics table where the timestamp indicates the transaction happened during the previous month, the item's location was NOT like "%ADULT%" and the statistic type is "issue" or "renew."  If an item has a shelving location of "CART," "PROC," or any other non-ADULT shelving location, it will be recorded in this column.

#. Video Disc checkouts and renewals this month (column P)

    - Data gathered from the "CR_VIDEO_DISC_LM" column of Report 3419
    - This report counts rows from the statistics table where the timestamp indicates the transaction happened during the previous month, the item's item type was like "NVID%," and the item's collection code was "DVD," "BLU-RAY," "COMBO," or "TVSERIES."

#. Hoopla Checkouts this month (column Q)

    - Data is gathered from a monthly report sent to us from Midwest Tapes

#. Borrower accounts used to checkout items this month (column R)

    - Data gathered from the "BORROWER_ACCT_USED_LM" column of Report 3420
    - This report counts distinct borrowernumbers in the statistics table where the statistic type is "issue," "renew," or "localuse."
    - If a borrower uses the library on the 1st, the 5th, and the 20th, they will be counted as 1 borrower for the month.  This gives you an idea of how many people with library cards are borrowing materials in the entire month.

#. Total borrowers at end of month (column S)

    - Data gathered from the "TOTAL_BORROWERS" column of Report 3420
    - This report counts rows in the borrowers table where the home library equals your library and the dateenrolled field is on or before the last day of the previous month.

#. Borrowers added this month (column T)

    - Data gathered from the "B_ADDED_LM" column of Report 3420
    - This report counts rows in the borrowers table where the home library equals your library and the dateenrolled field is in the previous month.

#. Patrons renewed this month (column U)

    - Data gathered from the "B_RENEWED_LM" column of Report 3420
    - This report counts rows in the borrowers table where the home library equals your library and the date_renewed field is in the previous month.

#. Patrons deleted this month (column V)

    - Data gathered from the "B_DELETED_LM" column of Report 3420
    - This report counts rows in the action logs that indicate a borrower with your home library was deleted and the timestamp is in the previous month.

#. Next ILLs loaned this month (column W)

    - Data gathered from the "NX_ILL_LOANED_LM" column of Report 3421
    - This report counts rows in the branchtransfer table where the sending library matched your library and the datesent field occured during the previous month.

#. Next ILLs borrowed this month (column X)

    - Data gathered from the "NX_ILL_BORROWED_LM" column of Report 3421
    - This report counts rows in the branchtransfer table where the receiving library matched your library and the datearrived field occured during the previous month.

#.

Fiscal year spreadsheets
^^^^^^^^^^^^^^^^^^^^^^^^

These spreadsheets contain almost the exact same data as the monthly spreadsheet except they are set to a July 1 - June 30 fiscal year.  The biggest difference will be that the January-June date in the Fiscal year spreadsheet will follow the format for the previous year's monthly spreadsheet.  If any changes are made to the calendar year spreadsheet in January (such as new columns), those changes will not be incorporated into the fiscal year spreadsheet until June.


Circulation statistics by item type - Excel spreadsheet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Spreadsheets exist for 2020
- This spreadsheet contains a tab for each month and a tab for YTD totals.
- This spreadsheet is generated by report 3393 - this is a big report that should only be run after hours.
- Staff at any library can run report 3128 to generate the same data for their individual library.
- The report that generates this data counts rows in the statistics table where the statistic type is "issue" or "renew."  The ADULT, YA, CHILDREN'S, and OTHER columns break those same numbers down based on the item's permanent location as recorded in the statistics table.  The report then groups all of the data by the item's item type as recorded in the statistics table.

Circulation statistics by collection code - Excel spreadsheet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Spreadsheets exist for 2019 and 2020
- This spreadsheet contains a tab for each month and a tab for YTD totals.
- This spreadsheet is generated by report 3394 - this is a big report that should only be run after hours.
- Staff at any library can run report 3159 to generate the same data for their individual library.
- The report that generates this data counts rows in the statistics table where the statistic type is "issue" or "renew."  The ADULT, YA, CHILDREN'S, and OTHER columns break those same numbers down based on the item's permanent location as recorded in the statistics table.  The report then groups all of the data by the item's collection code as recorded in the statistics table.

Request statistics - Excel spreadsheet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Spreadsheets exist for 2018, 2019, and 2020
- This spreadsheet contains a tab for each month and a tab for annual totals.
- This spreadsheet is generated by report 2975
- The columns on this report represent the following:

  - PLACED_LM = the number of requests that were placed in the previous calendar month.
  - FILLED_LM = the number of requests that were checked out to library patrons in the previous calendar month - regardless of when the requests were initially placed.
  - CNX_FROM_HOLD_SHELF_LM = the number of items that were waiting for a patron to pick them up at the time the request was cancelled during the previous calendar month - regardless of when the requests were initially placed. These requests could only have been cancelled by staff.
  - CNX_IN_TRASIT_LM = the number of items that were in transit from one library to its destination at the time the request was cancelled during the previous calendar month - regardless of when the requests were initially placed. These requests could only have been cancelled by staff.
  - CNX_BEFORE_ACTION_LM = the number of items that were cancelled before any item was shipped or waiting or possibly even pulled from the shelf to fill the requests during the previous calendar month - regardless of when the requests were initially placed. These requests could have been cancelled by staff or by patrons.
  - CNX_TOTAL_LM = the total number of items that were cancelled during the previous calendar month - regardless of when the requests were initially placed.
  - PLACED_BY_STAFF= the total number of requests placed last month that were created by staff members.
  - PLACED_BY_PATRON = the total number of requests placed by patrons via the OPAC.
