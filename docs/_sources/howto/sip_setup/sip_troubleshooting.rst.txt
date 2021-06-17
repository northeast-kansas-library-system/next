.. include:: /images.rst

SIP information
===============

SIP stands for Standard Interchange Protocol.  It is a protocol developed by 3M in the 1990s to allow the self-check systems they were developing to talk to different integrated library systems.  You can download version 2 of the SIP guide at https://nextkansas.org/cgi-bin/koha/opac-retrieve-file.pl?id=9cca6b92ec3c24b6d7047c7dfcd173dd

SIP applications
----------------

Next Search Catalog is currently using SIP for the following integrated applications:

- 3rd party self-check machines BASEHOR
- Hoopla
- Overdrive
- Kanopy
- Tutor.com
- Linkedin Learning
- Libki
- ShareIt
- PC Reservation
- Cybrarian
- There may be others

SIP server and login information
--------------------------------

The connection information and a list of current SIP usernames and passwords is available to NEKLS staff on the NEKLS Wiki.

Whenever possible, ask ByWater Solutions to create a new login when a library adds a new service or a new device that requires a SIP connection.  SIP logs contain very little information, so the best practice to help with troubleshooting SIP problems is to create a separate login for every device and every service at every library so that the different equipment and services at each library can be identified by SIP username in the SIP logs.

The best practice is to create usernames that include the name of the library and the name of the service the connection will be used for.  A good example is sip_sco_basehor which designates SIP, SelfCheckOut, and BASEHOR all in the login name.  A bad example is sipterm4.

SIP whitelisting
----------------

ByWater Solutions began requiring whitelisting for IPs connecting to SIP in 2020.  This means that if a library is using a 3rd party self-check system or PC Reservation and their network IP address changes, those SIP enabled services will stop working.

Troubleshooting SIP problems
----------------------------

There is a SIP testing tool available from the Central Library Consortium of Ohio at https://clcohio.org/sip-testing-tool/  If you use this tool, you must use the port for the socket connection to the SIP server.

You can test SIP across a telnet connection by using a terminal to establish a telnet connection to the server via the telnet port.

The most common SIP related problems are:

#. The SIP server is down.  Generally, if this is the problem, **all** of the SIP services at all libraries will fail to work as expected.
#. The network address at the library has changed and the whitelist needs to be updated.
#. There is an internet connectivity problem between the service and the SIP server.

The most common problems in solving SIP problems are:

#. Asking ByWater for help via e-mail or a ticket on their RT tracker.  It's best to phone about SIP problems.
#. If the issue is that the library's IP has changed, this can be further complicated by our legacy telnet connections.  Very few libraries sill use telnet connections for SIP.  Because of this, when asked to update the whitelist for the SIP server, ByWater Solutions will often update the whitelist for the socket connections but not the telnet connections.
