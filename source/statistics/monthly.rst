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

1. Total items owned 2021.01.01
  - This data comes from in thhe "Total items at end of month" column from December of the previous year.

2. Total items at the beginning of the month
  - Data gathered from the "START_I" column of Report 2881
  - This report counts items in the items table where the date accessioned was before the first day of the previous month and it counts items in the deleted items table where the date accessioned was before the first date of the previous month and the date deleted was after the first day of the month (i.e. the item was during the month).

3. Total items at end of month
  -Data gathered from the "END_I" column of Report 2881
  - This report counts items in the items table where the date accessioned was before the last day of the previous month and it counts items in the deleted items table where the date accessioned was before the last day of the previous month and the date deleted happened after that date (i.e. the item was deleted during the month you ran the report).

4. Items added this month
  - Data gathered from the "ITEMS_ADDED" column of Report 2881
  - This report counts items in the items and in the deleted items table where the date accessioned was during the previous month.

5. Items deleted this month
  - Data gathered from the "ITEMS_DELETED" column of Report 2881
  - This report counts items in the deleted items table where the timestamp is sometime during the previous month.

6. Total titles at end of month
  - Data gathered from the "TOTAL_HOLDINGS" column of Report 2881
  - This report counts distinct biblionumbers in the items table.  It also counts distinct biblionumbers in the deleted items table where the deleted item had been added before the last day of the month and deleted after the new month began.

7. Bibliographic records added this month
  - Data gathered from the "HOLD_ADD_L_M" column of Report 2881
  - This report counts distinct biblionumbers in the items table where the data in the biblios table indicates that the bibliographic record was created in the previous calendar month.

8. Bibliographic records deleted this month
  - Data gathered from the "HOLD_DEL_L_M" column of Report 2881
  - This report counts distinct biblionumbers in the deleted items table where the data in the deleted biblios table indicates that the bibliographic record was deleted in the previous calendar month.

9. Check-outs and renewals this month
  - Data gathered from the "CHECKOUT_RENEW_LM" column of Report 2880
  - This report counts rows from the statistics table where the timestamp indicates the transaction happened during the previous month and the statistic type is "issue" or "renew."

10. Check-outs this month
  - Data will be gathered from a new report

11. Renewals this month Returns this month
  - Data will be gathered from a new report

12. Adult checkouts and renewals this month
  - Data gathered from the "CR_ADULT_LM" column of Report 2880
    - This report counts rows from the statistics table where the timestamp indicates the transaction happened during the previous month, the item's location was like "%ADULT%" and the statistic type is "issue" or "renew."

13. Youth checkouts and renewals this month
  - Data gathered from the "CR_YOUTH_LM" column of Report 2880
  - This report counts rows from the statistics table where the timestamp indicates the transaction happened during the previous month, the item's location was NOT like "%ADULT%" and the statistic type is "issue" or "renew."

14. DVD checkouts and renewals this month
  - Data will be gathered from a new report

15. Hoopla Checkouts this month
  - Data is gathered from a monthly report sent to us from Midwest Tapes

16. Patron accounts used to checkout items this month
  - Data gathered from the "PATRON_LM" column of Report 2880
  - This report counts distinct borrowernumbers in the statistics table where the statistic type is "issue," "renew," or "localuse."

17. Total patrons at end of month
  - Data gathered from the "TOTAL_BORROWERS" column of Report 2898
  - This report counts rows in the borrowers table where the dateenrolled field is on or before the last day of the previous month.

18. Patrons added this month
  - Data gathered from the "B_ADDED_LM" column of Report 2898
  - This report counts rows in the borrowers table where the dateenrolled field is in the previous month.

19. Patrons renewed this month
  - Data gathered from the "B_RENEWED_LM" column of Report 2898
  - This report counts rows in the borrowers table where the date_renewed field is in the previous month.

20. Patrons deleted this month
  - Data gathered from the "B_DELETED_LM" column of Report 2898
  - This report counts rows in the action logs that indicate a borrower was deleted and the timestamp is in the previous month.

21. Next ILLs loaned this month
  - Data gathered from the "NX_ILL_LOANED_LM" column of Report 2880
  - This report counts rows in the branchtransfer table where the sending library matched your library and the datesent field occured during the previous month.
  - This report will be updated in 2021 due to changes in the branchtransfers that will make the report more accurate.

22. Next ILLs borrowed this month
  - Data gathered from the "NX_ILL_BORROWED_LM" column of Report 2880
  - This report counts rows in the branchtransfer table where the receiving library matched your library and the datearrived field occured during the previous month.
  - This report will be updated in 2021 due to changes in the branchtransfers that will make the report more accurate.

Fiscal year spreadsheets
^^^^^^^^^^^^^^^^^^^^^^^^

These spreadsheets contain the exact same data as the monthly spreadsheet except they are set to a July 1 - June 30 fiscal year.


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
