# pulseaudio-example

This is a simple example on how to create a snap that uses the PulseAudio
snap. The snap contains the pulseaudio-example command, which is a simple
application that can play wav files and is based on pacat-simple.c, which is an
example taken from the PA repository.

Use snapcraft to create the snap. After that we can build in a classic system:

$ git clone https://github.com/canonical-system-enablement/pulseaudio-example.git
$ cd pulseaudio-example
$ snapcraft

Then copy over 'pulseaudio-example_1_amd64.snap', the generated snap, to a Core
system and install, along pulsaudio:

$ snap install pulseaudio
$ snap install --dangerous pulseaudio-example_1_amd64.snap
$ snap connect pulseaudio-example:home :home

You can play a wav file doing:

$ sudo pulseaudio-example /var/snap/pulseaudio-example/common/<file.wav>
