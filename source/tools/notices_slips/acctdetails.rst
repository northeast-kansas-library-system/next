.. include:: /images.rst

ACCTDETAILS / Account Details Template - DEFAULT / Welcome to the library
=========================================================================

Notice information
------------------

- Recipient: This notice is e-mailed to the This notice is e-mailed a borrower's :term:`first valid email<First valid email>` address of any *new* borrower with a primary e-mail address

- Trigger: This e-mail is sent when a new account is created.
    - This e-mail is only sent once - it is not sent when accounts are renewed or modified
    - If staff tries to create an account and the process fails the first time staff clicks on "Save" for any reason, this message will not be sent.  Common reasons creating an account fails are: required information is not filled out; card number already exists, username already exists, the borrower's age is not allowed by the borrower category, etc.

- Enable/disable: The only way to disable this notice is to remove the primary e-mail address from the borrower's account

- CSS: The css for this notice is embedded in the notice

Notice details:
---------------

- General
   - Library: * All libraries (default)
   - Module: members
   - Code: ACCTDETAILS
   - Name: Account Details Template - DEFAULT

- Email
   - Type: HTML
   - Message subject: Welcome to the library


Message template:
^^^^^^^^^^^^^^^^^

.. code-block:: html

    <html>

    <head>
      <title>[% branch.branchname %] - </title>
      <!-- Notice code: ACCTDETAILS; Library: All; -->

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

          <p>Hello [% borrower.firstname %] [% borrower.surname %].</p>
          <p>Congratulations on getting a new library card at [% branch.branchname %].</p>
          <p>[% branch.branchname %] is a member of the Next Search Catalog library consortium and you can find our online catalog at <a href="https://nextkansas.org">https://nextkansas.org</a>. From the catalog you can search for library materials,
            access
            your account, request materials, see what's checked out on your account, and renew materials.</p>
          <p>You can also visit your home library's website at <a href="[% branch.branchurl %]">[% branch.branchurl %]</a>. From there you can learn more about your home library including hours and contact information.</p>
          <p>Your new Next Search Catalog account details are:</p>
          <ul>
            <li>Name: <strong><ins>[% borrower.firstname %][% IF borrower.othernames %] ([% borrower.othernames %])[% END %], [% borrower.surname %]</strong></ins></li>
            <li>Address: <strong><ins>[% borrower.address %][% IF borrower.address2 %] / [% borrower.address2 %][% END %] / [% borrower.city %], [% borrower.state %] [% borrower.zipcode %]</strong></ins></li>
            <li>Phone number: <strong><ins>[% borrower.phone %]</strong></ins></li>
            <li>Library card number: <strong><ins>[% borrower.cardnumber %]</strong></ins></li>
            <li>User ID: <strong><ins>[% borrower.userid %]</strong></ins></li>
          </ul>
          <h2>Your home library is:</h2>
          <p>[% branch.branchname %] / [% branch.branchaddress1 %] / [% branch.branchcity %], [% branch.branchstate %]<br /> [% branch.branchphone %]<br /> [% branch.branchemail %]</p>
          <p><span style="background-color: #FFFF00">Please contact your home library at the address, phone number, or e-mail address listed above for any of the following reasons:</span>
            <ul>
              <li>Your contact information as listed above is incorrect</li>
              <li>You do not want to receive e-mails from the library at this address</li>
              <li>If you have any other questions</li>
            </ul>
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
