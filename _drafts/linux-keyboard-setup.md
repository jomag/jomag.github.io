Keyboard setup
==============

This is my procedure to get the keyboard to work as I prefer in any modern Linux distribution:

Disable opening the shell with the 'win' or 'super' key
-------------------------------------------------------

To completely disable the functionality, use dconf:

    dconf write /org/gnome/mutter/overlay-key '""'

To return it to normal behaviour, reset it:

    dconf reset /org/gnome/mutter/overlay-key


