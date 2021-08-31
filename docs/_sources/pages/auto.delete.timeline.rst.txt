Timeline for automatic deletion of items
========================================

#. Patron checks out an item and a due date is assigned to the item (the due date may be updated if the patron renews the item)
#. X days after an item's due date, the patron is sent a first overdue notice
  - the number of days varies by library and is determined in the "Overdue notices/status triggers" tool on a library-by-library basis
3. 35 days after an item's due date, the patron is sent a second overdue notice saying that the item will be declared "Lost" in 10 more days
#. 45 days after an item's due date, the patron is sent a third overdue notice saying that they are being billed for the replacement cost of the item
#. 46 days after an item's due date at between 12:01 a.m. and 2:00 a.m., the item's status is changed from "checked out" to "Lost (more than 45 days overdue)"
  - when the status is changed to "Lost (more than 45 days overdue)" the item is removed from the list of items checked out to the patron and the patron is billed for the replacement cost of the item as recorded in the item record (Marc field 952$v)
6. 13 months after the item has been declared "Lost (more than 45 days overdue) the system will automatically delete the item record
  - At this time, a copy of the item's record is moved from the "items" table in the database to the "deleteditems" table
  - ** some libraries have policies and processes in place to manually delete these items before the 13 month automatic deletion has been triggered
7. 13 months after the item data has been moved from "items" to "deleteditems" the system will automatically delete the data from the "deleteditms" table - this is done to reduce the size of the database

Notes
-----

If an item does not have an amount set in the "Cost, replacement price" field (Marc 952$v), the patron will not receive a bill for the item.  Since the system will not send a bill to a patron for $0.00, if the item has no price, no bill will be generated.  If you want to know which items at your library have a $0.00 or empty replacement cost field, run report 3362.

Borrowers with the following patroncategories will not be automatically billed.  The names of these categories were recently updated to add the word (exempt) in order for staff to more easily identify them.  If you want to a count of how many borrowers at your library belong to each of these categories, please run report 3361.

+------------+----------------------------------------+
| Code       | Category Name                          |
+============+========================================+
| INHOUSE    | In-House Use by Library Staff (exempt) |
+------------+----------------------------------------+
| ILL        | Interlibrary Loan (exempt)             |
+------------+----------------------------------------+
| ASSOCIATE  | Library associate (exempt)             |
+------------+----------------------------------------+
| STUDENT    | Student (exempt)                       |
+------------+----------------------------------------+
| STAFF      | SYSTEM login only (exempt)             |
+------------+----------------------------------------+
| TEACHER    | Teacher/Faculty/Administrator (exempt) |
+------------+----------------------------------------+
