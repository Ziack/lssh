# lssh ![status](https://travis-ci.com/jamestomasino/lssh.svg?branch=master) ![license](https://img.shields.io/badge/license-GPL3-blue.svg?style=flat-square)

    LSSH(1)                           General Commands Manual                          LSSH(1)

    NAME
           lssh - a wrapper for Lastpass CLI and ssh-agent

    SYNOPSIS
           lssh [ -hv ] [ssh key name]

    DESRIPTION
           lssh  quickly  activates  ssh keys by name, filling passwords via Lastpass CLI, and
           adding them to ssh-agent. Keys are activated for 1-hour at a time.

           The ssh key name provided to lssh will be used to look up both the key  itself  and
           the password for the key. If that key has a password, lssh will search Lastpass for
           an entry named `SSH: [ssh key name]' and autofill the password with the results. If
           that  entry  is not found, `[ssh key name]' will also be attempted before giving up
           on a password search. The key will be passed to the ssh-agent regardless.

    OPTIONS
           -h     Shows simple help.

           -v     Shows current version number.

    ENVIRONMENT VARIABLES
           SSH_KEY_LOCATIONS
                  List of folders containing ssh keys.

                  This environment variable can contain any number of folder paths, space sep‐
                  arated,  which  will  be  used  to  search for the ssh keys. The folders are
                  searched in order and the search stops at the first successful match.

                  Unless otherwise defined, this variable defaults to ~/.ssh/

           LASTPASS_USER
                  Login username to Lastpass. This is used to initiate a login if you are  not
                  already logged in when initiating lssh

    EXAMPLES
           If you have an ssh key located at ~/.ssh/work/id_rsa, it can be loaded by entering:

           $ lssh work

    DEPENDENCIES
           lpass  The Lastpass CLI client

           expect programmed dialogue with interactive programs

    AUTHOR
           James Tomasino

    version 2019.12.25                      25 Dec 2019                                LSSH(1)
