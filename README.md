Sonos Web Controller
====================

NOTE! THIS IS A WORK IN PROGRESS! This is a really early alpha. Things might break from time to time, until I settle a final release that I consider stable for daily use. Until then only master branch will exist.

As a subtitute for the perl-based controller (www.purple.org) this project is aimed at giving similar controller as the native one, but in a browser.

Using node.js as backend, that will keep track of the state of the players, and WebSockets (socket.io) for a native feel (where the state of the players will be updated as soon as it changes).

Main focus will be to support the following:

 * Zone management
 * Volume control
 * Transport control (play/pause, rwd, fwd, seek)
 * Queue listing
 * Browsing favorites

Main target is to be able to run this on a raspberry pi, but any node.js compatible platform should work. I will only focus on supporting the following browsers:

* Chrome latest version (31 as of today)
* Firefox latest version (25 as of today)

For a screenshot of current progress, see: `http://upload.grabbarna.se/files/sonos-web-controller.png`

Currently, prev, next, play/pause and the progress bar works. Group volume works as well, but not as expected (and doesn't update). Track info, player state and progress bar updates instantly when controlled from another device, which was one of the main goals with this project.

settings.json
=============

To persist settings between updates, you can create a file called settings.json in the root folder (same level as server.js). Today this can take two arguments:

{
	"port": 8080,
	"cacheDir": "./cache"
}

The above are the defaults. Change them as you like and it will take precedence over the default ones.

This software is in no way affiliated nor endorsed by Sonos inc.

Change log
==========

 * 0.5.2 Supports settings.json for customization. Port and cacheDir to start with.
 * 0.5.0 Working player volume controls. Removed mute for the time being. Working shuffle/repeat/crossfade. requires sonos-discovery 0.7.x
 * 0.4.4 use md5 hash for cached image instead (fixes ENAMETOOLONG probably)
 * 0.4.2 Added dynamic favicon and title. Make sure to use sonos-discovery 0.6.1 or later to fix albumArtURI error
 * 0.4.1 Added cover art for now playing
 * 0.4.0 Now has working queue listing. Will tweak it for better performance later
 * 0.3.0 Lists favorites and possibility to replace queue with favorite/radio
 * 0.2.0 Now working group management (drag n' drop style)
 * 0.1.5 Master volume control now handles click for small increments
 * 0.1.4 Working master volume control (requires upgraded sonos-discovery 0.5.2)