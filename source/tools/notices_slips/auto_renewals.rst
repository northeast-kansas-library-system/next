.. include:: /images.rst

Notification of automatic renewal
==========

Notice information
----------

- Recipient:
    - This notice is e-mailed a borrower's :term:`first valid email<First valid email>` address

- Sender:
    - The "from" address on this email will match the email address for the library where the item was checked out

- Trigger:
    -

- Enable/disable:
    - The only way to disable this notice is to remove all of the :term:`valid email<First valid email>` addresses from the borrower's account

- CSS:
    - The css for this notice is embedded in the notice

Notice details:
----------

- General
   - Library: * All libraries (default)
   - Module: circulation
   - Code: AUTO_RENEWALS
   - Name: Notification of automatic renewal

- Email
   - Type: HTML
   - Message subject: Automatic renewal notice


Message template:
^^^^^^^^^^^

.. code-block:: html

    <html>

    <head>
      <title>[% branch.branchname %] - Automatic renewal notice</title>
      <!-- Notice code: AUTO_RENEWALS; Library: All; -->

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

          <p>[% branch.branchname %] - Automatic renewal notice (card number ending in [% borrower.cardnumber.substr(-6) FILTER upper %]):</p>
          [% IF checkout.auto_renew_error %]
          <p>The following item <span style="text-transform: uppercase;">[% biblio.title %]</span> has not automatically renewed because
          [% IF checkout.auto_renew_error == 'too_many' %]
          it has been renewed the maximum number of times possible.</p>
          [% ELSIF checkout.auto_renew_error == 'on_reserve' %]
          this item is on hold for another borrower.</p>
          [% ELSIF checkout.auto_renew_error == 'restriction' %]
          your account has been restricted by the library.</p>
          [% ELSIF checkout.auto_renew_error == 'overdue' %]
          there are overdue items on your account.</p>
          [% ELSIF checkout.auto_renew_error == 'auto_too_late' %]
          it's too late to renew this item.</p>
          [% ELSIF checkout.auto_renew_error == 'auto_too_much_oweing' %]
          your total unpaid fees are too high.</p>
          [% END %]
          [% ELSE %]
          <p>The following item, <span style="text-transform: uppercase;">[% biblio.title %]</span>, has been automatically renewed and is now due on [% checkout.date_due | $KohaDates as_due_date => 1 %]</p>
          [% END %]

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
