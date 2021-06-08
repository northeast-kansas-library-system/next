.. include:: /images.rst

Circulation history overview
============================

.. include:: \patrons\circulation_history\circulation_history.rst

.. include:: \opac\borrower_accounts\reading_history.rst


FAQ
---

- Q: Why do we delete circulation history after 13 months?
- A:
  # The primary reason is to minimize the size of the database.  If we had been saving borrower history for all borrowers since 2008 when the shared catalog began operation, the amount of data stored in the database would cause significant performance problems with the catalog.  Keeping 13 months worth of data allows us to keep enough data to run reports for the previous year.
  #. A secondary reason is to help maintain borrower privacy.  By Kansas law, a borrower's circulation history is considered confidential.  Keeping
