SMSTOOL
=======

SMSTOOL is an extremely simple and lightweight tool to send and receive SMS messages (short message service) via serial connection to a connected GSM modem (surfstick).

It is written in Python 3. The only dependency is the "serial" module.

Unlike other applications, that require you to run a daemon in background and do some kind of message spooling, SMSTOOL just connects to your modem for as long as a message has to be sent or retrieved.

Usage
-----

### Reading SMS

There are two possible commands to read pending SMS:

    smstool read
    smstool fetch

While the "read" command will just print all pending SMS messages, "fetch" will also take care of cleaning up the SMS storage space on your modem by deleting all read messages. Be sure to redirect the output to a file when using "fetch".

### Sending SMS

To send SMS, use the following command:

    smstool send NUMBER MESSAGE

NUMBER is the number you want to send to and MESSAGE is the message to send.

Configuration file
------------------

By default smstool tries to open your modem on /dev/ttyUSB0 with a baud rate of 115200.

To change the defaults, you may save a configuration file to $HOME/.config/smstool.conf with the following content:

    [smstool]
    baudrate=115200
    device=/dev/ttyUSB0

And edit these settings for your needs.

Known limitations
-----------------

* No support for "multi part" messages. The parts are received as separate messages!
* Not all GSM characters supported
