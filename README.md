# pulseaudio-example

This is a simple example on how to create a snap that uses the PulseAudio
snap. The snap contains the pulseaudio-example command, which is a simple
application that can play wav files and is based on pacat-simple.c, which is an
example taken from the PA repository.

Use snapcraft to create the snap. After that we can test by doing:

$ snap install pulseaudio
$ snap install --dangerous pulseaudio-example_1_amd64.snap
$ snap connect pulseaudio-example:home :home
$ sudo pulseaudio-example /var/snap/pulseaudio-example/common/<file.wav>
