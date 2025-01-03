# Paracon-PGP: A Modified Version of Paracon
## Overview & Updates
This is a modified version of Martin Cooper's Paracon that is intended for encrypted communications.

Paracon-PGP is a packet radio terminal that uses RSA to encrypt the information/payload section of AX.25 packets. This application is intended for those involved in amateur radio, also known as HAM radio. Users should use this program responsibly and only in jurisdictions where such encryption practices are compliant with local laws and regulations.

### ADDED FEATURES
- Users running Paracon-PGP are given a new public and private key every session
- The information contained in the first 'I' frame type received will be saved as the second-party public key
- All outgoing messages are encrypted with a second-party public key
- All incoming messages are decrypted with users's private key

### UPDATES
- All 'I' frame information/payload sections are displayed in the connections window

## Paracon-PGP Instructions
This application works the same as Paracon; however, after connecting to a user, the user must send out their public key before conversing. Additionally, GnuPG must be installed before use; GnuPG can be downloaded from https://gnupg.org/download/index.html.

To send out your public key, users must send the word "pub". 

```pub```

This will automatically send out your public key. Assuming the second party is using Paracon-PGP, this key will be automatically saved. Inversely, the other user must send theirs as well. 

After both users have public keys, any messages sent will be sent encrypted and then decrypted on the receiving end, leaving the monitor window to display the decrypted message on the recipient's screen.

**Paracon-PGP Author**: Thomas McLaughlin, KC3YTX

**Paracon Author**: Martin F N Cooper, KD6YAM

**License**: MIT License

<br>
<br>

# PyHam Paracon

## Overview

Paracon is a packet radio terminal for Linux, Mac and Windows. It is focused
on simplicity and ease of use, and incorporates the core functionality that
most packet users need without trying to include all of the bells and whistles
that few would use.

Key features of Paracon include:

- Multiple simultaneous AX.25 connected mode sessions, allowing for connections
  to multiple BBS or other remote nodes.
- Unproto (UI, or datagram) AX.25 mode, allowing for keyboard-to-keyboard chat
  or other non-connected uses.
- Text-based console application looks and behaves the same on all supported
  platforms (Linux, Mac, Windows).
- Uses the AGWPE protocol to communicate with any server implementing that
  protocol. Tested and supported with Direwolf, ldsped and AGWPE.
- Self-contained executable requires only a Python installation to run, without
  the need to install any additional dependencies.

**Author**: Martin F N Cooper, KD6YAM  
**License**: MIT License

## Installation

**Important**: This application requires Python 3.7 or later.

Download the latest release from GitHub.

1. Go to the
   [latest release](https://github.com/mfncooper/paracon/releases/latest)
    page.
2. In the *Assets* section, click on the Paracon `.pyz` file to download it.

You may download the `.pyz` file to any directory of your choosing. If you
are running on Linux or Mac, you may wish to place it in a directory that is
on your path.

The source code is available from the
[GitHub repository](https://github.com/mfncooper/paracon):

```console
$ git clone https://github.com/mfncooper/paracon
```

## Running

Before running Paracon, ensure that you have an AGWPE server (e.g. Direwolf,
ldsped or AGWPE) installed and running either on the same system or on a
remote system to which you have access. If you do not already have such a
server set up, see [References](#references) below for more information.

Note that Paracon will create its configuration and log files in your *current
directory* when you start it, not the directory in which the ``.pyz`` file is
located.

To start Paracon, open a terminal window (Command Prompt or PowerShell on
Windows), change directory to a suitable location for your configuration and
log files, and type the following:

```console
$ python3 <path-to-pyz-file>/paracon_<version>.pyz
```

Depending upon your particular system, you may need to substitute `python`
for `python3` in the above command line, and of course backslash for slash
if you are running on Windows.

On Linux and Mac, you can make the file directly executable, so that if you
have placed it in a directory that is on your path, you can simply type:

```console
    $ paracon_<version>.pyz
```

To enable this, you will need to set the necessary file permission using:

```console
    $ chmod u+x paracon_<version>.pyz
```

## Libraries 

pip install urwid

pip install pyham_ax25

pip install pyham_pe

pip install python-dotenv

## Documentation

Full documentation is available
[online](https://paracon.readthedocs.io/en/latest/)
and includes the following:

<dl>
<dt><b>User Guide</b></dt>
<dd>The User Guide takes you through all of the functionality of Paracon,
from starting it the first time to using connected mode sessions and more.</dd>
</dl>

## Discussion

If you have questions about how to use this application, the documentation
should be your first point of reference. If the User Guide doesn't answer your
questions, or you'd simply like to share your experiences or generally discuss
this application, please join the community on the
[Paracon Discussions](https://github.com/mfncooper/paracon/discussions)
forum.

Note that the GitHub Issues tracker should be used only for reporting bugs or
filing feature requests, and should not be used for questions or general
discussion.

## References

<dl>
<dt>Direwolf</dt>
<dd>Direwolf is probably the most widely used AGWPE server, and includes its
own performant and robust AX.25 protocol stack. It is available for
Linux, Mac and Windows. Open source.<br>
<a href="https://github.com/wb2osz/direwolf">https://github.com/wb2osz/direwolf</a></dd>
<br>
<dt>ldsped</dt>
<dd>ldsped is an alternative AGWPE server that runs on Linux, and relies on
the Linux native AX.25 protocol stack. Open source.<br>
<a href="https://www.on7lds.net/42/node/2">https://www.on7lds.net/42/node/2</a></dd>
<br>
<dt>AGWPE</dt>
<dd>AGWPE is the original implementation of the protocol, and runs on
Windows. Both free (AGWPE) and paid (Packet Engine Pro) versions are
available. Proprietary; closed source.<br>
<a href="https://www.sv2agw.com/Home/downloads#packetenginePro">https://www.sv2agw.com/Home/downloads#packetenginePro</a></dd>
</dl>

## About PyHam

The PyHam name was borne of a need for unique names for Python packages that
were created for ham radio enthusiasts who are also software developers. Those
packages were themselves created out of a desire for a simpler way of building
sophisticated ham radio applications without the need to always start from
scratch. Paracon is one such application.

See the [PyHam home page](https://pyham.org) for more information, and a
list of currently available libraries and applications.
