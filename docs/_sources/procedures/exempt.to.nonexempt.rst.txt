Update TEACHER to PU_TEACH \|\| ASSOCIATE to A_ASS \|\| STUDENT to PU_STU
=========================================================================

- Permission needed:  Superlibrarian
- Time needed:  1 to 4 hours of uninterrupted work (depends on the size of the library, their rule set, and number of accounts)

#. Go to *Home > Administration > Patron categores* and change the PU_TEACH/A_ASS/PU_STU limitations to include the library that wants to use the category
#. Go to *Home > Administration > Patron categores* and change the TEACHER/ASSOCIATE/STUDENT limitations to remove the library that wants to stop using the category
#. Go to *Home > Administration > Circulation and fine rules* and add rules for PU_TEACH/A_ASS/PU_STU to match the old TEACHER/ASSOCIATE/STUDENT rules
#. Go to *Home > Tools > Overdue notice/status triggers* and make sure notice triggers for the new categories have been set up
#. Identify borrowers with a report

   ..
     [TODO] needs report information

#. Change borrowers using the batch patron modification tool

   ..
     [Todo] needs information on how to use the batch modification tool

#. Go to *Home > Administration > Circulation and fine rules*  and delete the TEACHER/ASSOCIATE/STUDENT rules that are no longer needed for the libarary that has dropped the category
