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

    [%- USE KohaDates -%]

    <html>

    <head>
      <title>[% branch.branchname %] - Library Renewal Receipt</title>
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
          This digital receipt only includes items renewed on [% today | $KohaDates %].<br />
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
