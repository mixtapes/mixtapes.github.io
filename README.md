# Mixtapes

A live tracklisting service for DJs and listeners.

## What it is

Mixtapes brings back the essence of DJing by promoting the music you care about.

If you play using Serato (or Traktor - planned feature) it broadcasts the tracklisting live using a desktop client that quietly runs in the background.

Your listeners can follow your set on a web interface to get to know important information about the artist and the song that you are playing in real time. This not only helps your listeners to discover music in real time but also allows you to support the artists whose music you love.

## What it isn't

It's not a new [Mixcloud](http://mixcloud.com/) or [Soundcloud](www.soundcloud.com). We are not planning on hosting mixes, there are other much better and well thought out sites for this purpose. We might embed players from these sites but that's about it.

## How to use

* Download the desktop client
* Register a profile on Mixtapes (probably within the client itself)
* Start playing your set and share the URL of your playlist

## Architecture

The Mixtapes service is built using 2 main components:

#### The client

The client is an application that runs onyour computer that has Serato plugged into. It's silently running in the background and is parsing the Serato playlist whilst you are playing your mix. All done automatically. It's heavily based on the cool [SSLScrobbler tool](https://github.com/ben-xo/sslscrobbler) written by [Ben XO](https://github.com/ben-xo). It's currently written in PHP but I'm planning on porting it to a native Mac OS X app.

#### The API

The client (mentioned above) is sending information to a JSON REST API backend that it authenticates with. Currently written in [Ruby On Rails](http://rubyonrails.org/) with a [MongoDB](http://www.mongodb.org/) back-end for storing playlists in easy JSON-style documents.

#### The Mixtapes website

The information is displayed on a web interface to listeners who can see your tracklists live. It updates live as you play.

Main areas of focus:

* The live tracklisting info (what track is played right now, when it started, whose track it is, etc)
* The biography of the artist whose tune is played right now (using the [Last.fm API](http://www.last.fm/api)?)
* An embedded HTML5 player to listen to the mix straight from the same interface.

## How to contribute

Please see [this separate document](How-to-contribute.md) for the contribution guidelines. We are looking for deveopers, graphics/ux designers and broadcasters to help building this tool.

## Planned features

* Support for Traktor DJ session broadcasting
* Embeddable tracklisting widgets for external sites
* Collaborative tracklist writing for mixes that are not broadcasted live (to replace the fiddly way of building tracklists on forums)
* Automatically parsing tracklisting information from your Soundcloud uploads.
* QR code generation for scheduled sets to print on flyers so that people can follow tracklisting in clubbing environemtns

## Licensing

The code and all its components will be made 100% open source and will be available on [Github](https://github.com/mixtapes). It will be using the [Attribution-NonCommercial-ShareAlike Creative Commons License](http://creativecommons.org/licenses/by-nc-sa/4.0/).

![CC BY-NC-SA](./images/creative-commons-symbol.png "Attribution-NonCommercial-ShareAlike Creative Commons License")
