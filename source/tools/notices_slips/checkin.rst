.. include:: /images.rst

Check-in Receipt email (Digest)
==========

Notice information
----------

- Recipient:
    - This notice is e-mailed a borrower's :term:`first valid email<First valid email>` address

- Trigger:
    - This notice is added to the message queue whenever an item that is checked out to a borrower is checked in
    - The message queue is currently set to send this message every :00, :15, :30, and :45 minutes past the hour, 24 hours per day

- Enable/disable:
    - This e-mail is disabled by default for newly created borrowers
    - This e-mail can be enabled or disabled by checking the "Email" checkbox next to "Email check-in receipt" in a borrower's messaging preferences
    - Borrowers can enable/disable this notice in the OPAC

- CSS:
    - The css for this notice is embedded in the notice

Notice details:
----------

- General
   - Library: * All libraries (default)
   - Module: circulation
   - Code: CHECKIN
   - Name: Check-in Receipt email (Digest)

- Email
   - Type: HTML
   - Message subject: Library Check-in Receipt


Message template:
^^^^^^^^^^^

.. code-block:: html

    <html>

    <head>
      <title>[% branch.branchname %] - Library Check-in Receipt</title>
      <!-- Notice code: CHECKIN; Library: All; -->

      <meta charset="UTF-8" />

      <style>
        * {
          font-family: Verdana, Arial, sans-serif;
        }

        body .notice {
          color: #000000;
          background-color: #ffffff;
          width: 90%;
          margin: 0;
          font-size: 12pt;
        }

        .notice p {
          font-size: 12pt;
          color: #000000;
        }

        .notice h1 {
          font-size: 1.6em;
          color: #000000;
        }

        .notice h2 {
          font-size: 1.5em;
          color: #000000;
        }

        .notice h3 {
          font-size: 1.4em !important;
          color: #000000;
        }

        .notice h4 {
          font-size: 1.3em !important;
          color: #000000;
        }

        .notice h5 {
          font-size: 1.2em;
          color: #000000;
        }

        .notice h6 {
          font-size: 1.1em;
          color: #000000;
        }
      </style>

    </head>

    <body>

      <div class="notice">

        <div id="notice_content">

          <h2>[% branch.branchname %] - Library Check-in Receipt</h2>
          <p>The following items were checked in today from your library account (card number ending in [% borrower.cardnumber.substr(-6) FILTER upper %]):</p>
          ----
          <p>
            [% biblio.title %]<br />
            Barcode: [% item.barcode %]<br />
            Date checked out: [% old_checkout.issuedate | $KohaDates with_hours => 1 %]<br />
            Date due: [% old_checkout.date_due | $KohaDates %]<br />
            Date returned: [% old_checkout.returndate | $KohaDates with_hours => 1 %]<br />
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

      </div>

    </body>

    </html>
