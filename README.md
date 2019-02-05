# RasFlic
Automate use of flic buttons in some python extensible way

## Setup and Running

### Onetime Setup

On your raspberry pi, git clone this repro

    git clone --recursive https://github.com/gordonwatts/RasFlic.git

### After booting

You need to get the Flic bluetooth server running. The Flic SDK will not share the bluetooth
controller - you'll have to add another one if you need it. This is for running as a regular user. Please
get the relative paths right below!

    cd <dir where you can store the bt database files>
    sudo sudo setcap cap_net_admin=ep RasFlic/externals/fliclib-linux-hci/bin/armv6l/flicd
    RasFlic/externals/fliclib-linux-hci/bin/armv6l/flicd -f flic-db.sqlite3 &

### Pairing Buttons

This has to be done each time you either delete the database or add a new button. See the ``Running`` instructions
on the [library webpages](https://github.com/50ButtonsEach/fliclib-linux-hci).

### Automating startup

Once you've cloned this, you can automate its running so it starts automatically after boot.

## Adding new commands
