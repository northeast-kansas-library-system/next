.. include:: /images.rst

Renewal Receipt (Digest)
==========

Notice information
----------

- Recipient:
    - This notice is e-mailed a borrower's :term:`first valid email<First valid email>` address

- Sender:
    - The "from" address on this email will match the email address for the library where the item was checked out

- Trigger:
    - This email is sent when an item is renewed and the system preference " RenewalSendNotice" is set to "Send"

- Enable/disable:
    - This e-mail is disabled by default for newly created borrowers
    - This e-mail can be enabled or disabled by checking the "Email" checkbox next to "Email check-out receipt" in a borrower's messaging preferences
    - Borrowers can enable/disable this notice in the OPAC

- CSS:
    - The css for this notice is embedded in the notice

Notice details:
----------

- General
   - Library: * All libraries (default)
   - Module: circulation
   - Code: RENEWAL
   - Name: Renewal Receipt (Digest)

- Email
   - Type: HTML
   - Message subject: Library renewal receipt


Message template:
^^^^^^^^^^^

.. code-block:: html

<html>

<head>
  <title>[% branch.branchname %] - Library Renewal Receipt</title>
  <!-- Notice code: RENEWAL; Library: All; -->
</head>

<body>

  <div id="message_content">

    <h2>[% branch.branchname %] - Library Check-out Receipt</h2>
    <p>The following items were renewed today on your library account.</p>
    <p>This digital receipt only includes items renewed on your library account today.</p>
    ----
    <p>
      [% biblio.title %]<br />
      Barcode: [% item.barcode %]<br />
      Date due: [% item.onloan | $KohaDates %]
    </p>
    ----

  </div>

  <footer>

    <p>Thank you,</p>
    <p>
      [% branch.branchname %]<br />
      [% branch.branchaddress1 %]<br />
      [% branch.branchcity %], [% branch.branchstate %] [% branch.branchzip %]
    </p>
    <p>You can access your account on-line at <a href="https://nextkansas.org">https://nextkansas.org</a> 24 hours a day.</p>
    <p>Visit our library's website at: <a href="[% branch.branchurl %]">[% branch.branchurl %]</a></p>
    <p>If you no longer wish to receive these e-mails or if you have any questions, please contact us by phone at <strong><ins>[% branch.branchphone %]</ins></strong>.</p>

  </footer>

</body>

</html>
