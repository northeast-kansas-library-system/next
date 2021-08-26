.. include:: /images.rst

MEMBERSHIP_EXPIRY / Account expiration / Your Library Card Expires Soon
=======================================================================

Notice information
------------------

- Recipient: This notice is e-mailed to the primary e-mail address of any borrower with a primary e-mail address

- Trigger: This e-mail is sent 30 days before a borrower's account is set to expire
    - The 30 day period is set by the global system preference MembershipExpiryDaysNotice

- Enable/disable: The only way to disable this notice is to remove the primary e-mail address from the borrower's account

- CSS: The css for this notice is embedded in the notice


Notice details:
---------------

- General
   - Library: * All libraries (default)
   - Module: members
   - Code: MEMBERSHIP_EXPIRY
   - Name: Account expiration

- Email
   - Type: HTML
   - Message subject: Your Library Card Expires Soon


Message template:
^^^^^^^^^^^^^^^^^

.. code-block:: html

    <html>

    <head>
      <title>[% branch.branchname %] - </title>
      <!-- Notice code:  MEMBERSHIP_EXPIRY; Library: master; -->

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

          <p>[% borrower.firstname %] [% borrower.surname %]:</p>
          <p>
            Your library card will expire on [% borrower.dateexpiry %]. Please call us at [% branch.branchphone %] or visit us at [% branch.branchname %] to renew your account.
          </p>

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
