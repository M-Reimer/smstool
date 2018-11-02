SMSTOOL
=======

SMSTOOL is an extremely simple and lightweight tool to send and receive SMS (short message service) via serial connection to a connected GSM modem (surfstick).

It is written in Python 3. The only dependency is the "serial" module.

Unlike other applications, that require you to run a daemon in background and do some kind of message spooling, SMSTOOL just connects to your modem for as long as a message has to be sent or retrieved.
