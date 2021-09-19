this will be only covering the non pipewire setup for using both pulseaudio and jackd



payru -S jackd2-git carla-git cadence-git non-mixer-git mididings-git pulseaudio pulseaudio-jack pulseaudio-alsa -y

once install has finished we need make sure our user is part of the audio group u can do this by running

groups

if u your user is not in audio group u need to make your user apart it by running 

sudo usermod -G audio {username}

once your in the audio group u will need to edit limits.conf 

sudo /etc/security/limits.conf

and then add the follow lines the before 

#audio group
@audio    -   rtprio    95
@audio    -   memlock   unlimited
