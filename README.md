# Welcome to *Mixtapes*

Mixtapes is a live tracklisting service for DJs and their listeners. *NOTE: This is a work-in-progress document that is subject to change.*

## What it is

Mixtapes brings back the essence of DJing by *promoting the music you care about*. Mixtapes hooks into [Serato Scratch Live](http://serato.com/scratchlive) and broadcasts the tracklisting in real time using a desktop client that quietly runs in the background.

Your listeners can follow your set via a web interface to get to know relevant information about the music you are playing in real time. This way you can really promote and support the artists whose music you love.

## What it isn't

It's not a new [Mixcloud](http://mixcloud.com/) or [Soundcloud](www.soundcloud.com). We are not planning on hosting mixes, there are other much better and well thought out sites for this purpose. We might embed players from these sites but that's about it.

## Target audience

In 2014 we are living in times where producer DJs rule most of the world of DJing. This is really sad because regardless of how talented these people can be, their primary goal is to promote mainly their own work.

Mixtapes is aimed at real DJs who like to educate their listeners, share information on tracks, releases that they care about. It's also aimed at listeners who are always hungry for discovering good music.

Having said that, Mixtapes could be considered a *music discovery service* (like Last.fm or Spotify) but with an important distinction: Most of these well known sites out there are based on automated algorithms. These can be quite useful however these are missing an important point: **Results of algorithm-generated playlists won't get you far**. Curation - and so DJing - implies a personal choice. Mixtapes empowers DJs and builds on top of exactly that.

Are you a DJ? Have you found a new amazing producer? You’ll be able to share new discoveries with your followers in real time.

## Getting in touch

You can contact me via Twitter by mentioning the [@mixtapescc](http://twitter.com/mixtapescc) user.

<a href="https://twitter.com/mixtapescc" class="twitter-follow-button" data-show-count="false">Follow @mixtapescc</a>
<script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+'://platform.twitter.com/widgets.js';fjs.parentNode.insertBefore(js,fjs);}}(document, 'script', 'twitter-wjs');</script>

## Planned usage

* Download the desktop client
* Register a profile on Mixtapes (probably within the client itself)
* Start playing your set and share the URL of your playlist

## Architecture

The Mixtapes service is built using the following main components:

#### The client

The client is an application that runs on your computer that has Serato plugged into. It's silently running in the background and parsing the Serato playlist whilst you are playing your mix. All done automatically. It's heavily based on the super-cool [SSLScrobbler tool](https://github.com/ben-xo/sslscrobbler) written by [Ben XO](https://github.com/ben-xo). It's currently written in PHP but I'm planning on porting it to a native Mac OS X app.

*(source code available [here](https://github.com/mixtapes/client))*

#### The API

The client would be pretty useless on its own, so there's a JSON REST API backend that it authenticates with. The API then stores the playlist information and broadcasts updates to the Mixtapes website. The API is written in [Ruby On Rails](http://rubyonrails.org/) with a [MongoDB](http://www.mongodb.org/) back-end for storing playlists as easy JSON-style documents.

*(source code available [here](https://github.com/mixtapes/api))*

#### The Mixtapes website

This is where you'd be sending your listeners. The Mixtapes website is where the live tracklisting information is displayed, along with the currently played track and all its metadata. It updates live as you play, shows the biography of the arthist whose track you are playing right now.

Main areas of focus:

* The live tracklisting info (what track is played right now, when it started, whose track it is, etc)
* The biography of the artist whose tune is played right now (using the [Last.fm API](http://www.last.fm/api)?)
* An embedded HTML5 player to listen to the mix straight from the same interface.

## Contribution guidelines

Want to help me building this service? Cool! Please see [this separate document](How-to-contribute.md) for the contribution guidelines. I'm looking for deveopers, graphics/UX designers and broadcasters to help building this tool and to make it the bast as it could be.

## Planned features

* Support for Traktor DJ session broadcasting
* Embeddable tracklisting widgets for external sites
* Collaborative tracklist writing for mixes that are not broadcasted live (to replace the fiddly way of building tracklists on forums)
* Automatically parsing tracklisting information from your Soundcloud uploads.
* QR code generation for scheduled sets to print on flyers so that people can follow tracklisting in clubbing environemtns

## Licensing

The code and all its components will be made 100% open source and will be available on [Github](https://github.com/mixtapes). It will be using the [Attribution-NonCommercial-ShareAlike Creative Commons License](http://creativecommons.org/licenses/by-nc-sa/4.0/).

![CC BY-NC-SA](./images/creative-commons-symbol.png "Attribution-NonCommercial-ShareAlike Creative Commons License")
