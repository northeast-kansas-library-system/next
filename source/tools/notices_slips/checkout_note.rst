.. include:: /images.rst

CHECKOUT_NOTE / Checkout note on item set by patron / Borrower reports problem with an item
===========================================================================================


Notice information
------------------

- Recipient:
    - The email address of the library where the item was checked out

- Sender:
    - The "from" address on this e-mail will match the system default email address as set in KohaAdminEmailAddress

- Trigger:
    - This notice is sent to a library when a borrower enters a "Report a problem" note through the OPAC on an item that's currently checked out to them.

- Enable/disable:
    - These notices cannot be disabled - they are sent to the library where the item was checked out, not to the borrower

- CSS:
    - The css for this notice is embedded in the notice


Notice template details
-----------------------

- General
   - Library: * All libraries (default)
   - Module: circulation
   - Code: CHECKOUT_NOTE
   - Name: Checkout note on item set by patron

- Email
   - Type: HTML
   - Message subject: Borrower reports problem with an item


Message template:
^^^^^^^^^^^^^^^^^

.. code-block:: html

    [%- USE KohaDates -%]

    <html>

    <head>
      <title>[% branch.branchname %] - Library renewal receipt</title>
      <!-- Notice code: RENEWAL; Library: All; -->

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

      <div id="message_content">

        <h2>[% branch.branchname %] - Library renewal receipt</h2>
        <p>The following items were renewed today on your library account (card number ending in [% borrower.cardnumber.substr(-6) FILTER upper %]).</p>
        <p>
          This digital receipt only includes items renewed on [% today | $KohaDates %] at [% SET time = today | $KohaDates with_hours => 1 %][% time.substr(-5) %].<br />
          ==============================
        </p>
        ----
        <p>
          [% biblio.title FILTER upper %][% IF biblio.subtitle %] : [% biblio.subtitle FILTER upper %][% END %]<br />
          Barcode: [% item.barcode %]<br />
          Date due: [% item.onloan | $KohaDates %]<br />
          ==============================
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
