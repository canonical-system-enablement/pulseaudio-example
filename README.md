# pacat-simple

This is a simple example on how to configure a snap that uses the PulseAudio
snap. pacat-simple.c is an example taken from the PA repository.

Use snapcraft to create the snap. After that we can test by doing:

$ snap install pulseaudio
$ snap install --dangerous pacat-simple_1_amd64.snap
$ snap connect pacat-simple:home :home
$ sudo pacat-simple /var/snap/pacat-simple/current/<file.wav>
