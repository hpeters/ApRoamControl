ApRoamControl is an access point station roaming control application written as a shell script.

It was created to overcome Android's severe lack of roaming between access points.

Android hangs onto an access point up to the point of connection failure before switching to a different access point
even though you might be standing right next to a much stronger one.

ApRoamControl tries to overcome this by monitoring the signal strength that each access point is receiving from the station.
If it finds that there is an access point with a significantly higher signal it will send the station a deauthication packet over
the access point it is currently connect to.

The Android station will then hopefully connect to the stronger accces point.
It is entirely up to the Android station what access point it connects to so it might not always connect to the strongest one.

I am not a programmer just an idiot with a keyboard that couldn't find anything simular already available
so I am sure things could be done better. If you make any modifications you think might be usefull we would
welcome looking at them and possibly adding them to ApRoamControl.

Don't expect ApRoamControl to be able to handle 20 access points and 200 clients. I have tested it with 5 clients and 3 access points
with a saturated single stream wifi N connection with no problem.
The hardware used was a tplink 841nd, tplink wdr3500, buffalo wzr-hp-ag300h and the server was an intel dual core atom processor based machine.
So as you can see none of them are exactly power houses.

The client part of ApRoamControl runs on access points running Openwrt with Atheros chipsets. It will probably work on others as well as
long as the wifi supports monitor mode.
The Server part of ApRoamControl was tested on a Debian based intel dual core atom processor machine.
I'm sure it could be modified to run on ther distros easly maybe even openwrt.

One (big) limitation is all access points have to be on the same channel this is because they have to be able to serve both clients(stations) and monitor the
clients at the same time therefore the wifi radio is not able to switch frequencies.

That means ApRoamControl wont work well in a wifi setup with multiple access points that is under a heavy traffic load.


harley@biterror.net
Harley Peters
