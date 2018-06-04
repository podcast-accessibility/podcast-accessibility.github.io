---
layout: page
title: Accessible media players
permalink: /accessible-media-players/
sidebar_link: false
---

One of the items you have to consider to improve your podcast's accessibility is which player you'll use. Many of the players available through major podcasting platforms are not accessible. Providing alternatives is important.

* [Basic features](#basic)
* [Advanced features](#advanced)
* [Players](#players)
* [Implementing accessible players](#implementing)
* [What if you can't?](#whatif)

## Basic accessibility features of media players {#basic}

* All controls can be reached via keyboard
* All controls can be activated via keyboard
* Focus is visible on all controls
* Labels for each control is clear and available to screen readers
* Media does not autoplay
* No [keyboard traps](https://www.w3.org/TR/UNDERSTANDING-WCAG20/keyboard-operation-trapping.html)

## Advanced accessibility features of media players {#advanced}

* Ability to add synchronized transcripts
* Ability to add described video (for video files)
* Ability to show/hide captions (for video files)

## Some accessible media players {#players}

The following list is not exhaustive but should get you started

* [AblePlayer](https://ableplayer.github.io/ableplayer/) - Used on the [W3C's WAI Perspective videos](https://www.w3.org/WAI/perspective-videos/) and on [The A11y Rules Podcast](https://a11yrules.com).
* [JW Player](https://www.jwplayer.com/) - Claims accessibility conformance. But was lacking a few things to be fully accessible in my testing for implementation on the A11y Rules Podcast's site.
* [OzPlayer](http://www.accessibilityoz.com/ozplayer/) - Not tested by us but creators of the product have good accessibility experience.
* YouTube media player (the HTML5 version, not the Flash version). May cause issues with embedding on a site.

## Implementing an accessible media player on your podcast website {#implementing}

There are too many different services to provide detailed information about implementing an accessible media player on your site. I'll be happy to help in as much as I'm able to if you [ping me on Twitter](http://twitter.com/vavroom)

## What if your podcasting platform's player is not accessible? {#whatif}

If the podcasting platform you use doesn't provide an accessible player, and there are no solution to swap for a different player, you may wish to contact the provider and point out that the player is not accessible and that you need them to improve the accessibility. This may not lead anywhere, but if enough people voice the need for accessibility, it may become a feature that is implemented in their player.
