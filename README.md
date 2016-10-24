# listen-namespace

## 1. Introduction

A simple RSS namespace extensions for podcast feeds.

The goal is to create a spec that would behave like a trackback for audio listening behavior.  Podcast clients and apps that implement the namespace will allow podcast hosts to track user engagement in a detailed way.

The way the namespace works is pretty straightforward.  There are 4 new elements you can add to **item** tags in your feed: **play**, **pause**, **seek** and **finish**.  Each element will contain a callback url that will get triggered when the user plays an episode, pauses an episode, seeks within an episode and finishes listening to an episode.

## 2. Conventions

In this documentation, the key words MAY, MUST, MUST NOT, OPTIONAL, RECOMMENDED, REQUIRED, SHALL, SHALL NOT, SHOULD and SHOULD NOT are to be interpreted as described in [RFC 2119](http://www.ietf.org/rfc/rfc2119.txt).

## 3. Declaration

The Listen namespace requires the "http://www.kyleshank.com/listen.dtd" declaration in the RSS element.

    <rss xmlns:listen="http://www.kyleshank.com/listen.dtd">

Sample feeds demonstrate how to incorporate elements from this namespace in an [RSS 2.0](https://raw.githubusercontent.com/kyleshank/listen-namespace/master/example/podcast.xml) feed.

## 4. listen:play

The play element, when present in an [item](http://www.rssboard.org/rss-specification#hrelementsOfLtitemgt), identifies the item's play URL (OPTIONAL).

An RSS 2.0 feed MUST define the URL as the element's value.

    <listen:play>http://example.podcast.com/episode/100/play</listen:play>

An item MUST NOT contain more than one play element.

## 5. listen:pause

The pause element, when present in an [item](http://www.rssboard.org/rss-specification#hrelementsOfLtitemgt), identifies the item's pause URL (OPTIONAL).

An RSS 2.0 feed MUST define the URL as the element's value.

    <listen:pause>http://example.podcast.com/episode/100/pause</listen:pause>

An item MUST NOT contain more than one pause element.

## 6. listen:seek

The seek element, when present in an [item](http://www.rssboard.org/rss-specification#hrelementsOfLtitemgt), identifies the item's seek URL (OPTIONAL).

An RSS 2.0 feed MUST define the URL as the element's value.

    <listen:seek>http://example.podcast.com/episode/100/seek</listen:seek>

An item MUST NOT contain more than one seek element.

## 7. listen:finish

The finish element, when present in an [item](http://www.rssboard.org/rss-specification#hrelementsOfLtitemgt), identifies the item's finish URL (OPTIONAL).

An RSS 2.0 feed MUST define the URL as the element's value.

    <liste:finish>http://example.podcast.com/episode/100/play</listen:finish>

An item MUST NOT contain more than one finish element.

## 8. License

Copyright 2016 Kyle Shank. Redistribution and reuse of this document is permitted under the terms of the Creative Commons Attribution-ShareAlike 3.0 license.

## 9. Credits

The Listen namespace for RSS was created by Kyle Shank.

## 10. Example

Here is what an example podcast RSS feed would look like:

    <?xml version="1.0" encoding="UTF-8"?>
    <rss version="2.0" xmlns:itunes="http://www.itunes.com/dtds/podcast-1.0.dtd" xmlns:atom="http://www.w3.org/2005/Atom" xmlns:listen="http://www.kyleshank.com/listen.dtd">
      <channel>
        <title>Release Notes</title>
        <description>A podcast about a thing (this thing) that makes podcasts.</description>
        <link>http://notes.fans.fm</link>
        <language>en-us</language>
        <copyright>2016 Kyle Shank</copyright>
        <atom:link href="http://feeds.fans.fm/2.xml" rel="self" type="application/rss+xml"/>
        <itunes:subtitle>A podcast about a thing (this thing) that makes...</itunes:subtitle>
        <itunes:summary>A podcast about a thing (this thing) that makes podcasts.</itunes:summary>
        <itunes:author>Kyle Shank</itunes:author>
        <itunes:explicit>no</itunes:explicit>
        <itunes:category text="Technology">
        </itunes:category>
        <itunes:owner>
          <itunes:email>kyle@fans.fm</itunes:email>
          <itunes:name>Kyle Shank</itunes:name>
        </itunes:owner>
        <itunes:image href="https://s3.amazonaws.com/fansfm_production/db083380-24e5-0134-7874-0f16ad195fd9.jpg"/>
        <item>
          <title>1.0 - Welcome to FANS.FM!</title>
          <description>FANS.FM is a podcasting platform that lets you start a podcast for free, get deep analytics about your audience and earn revenue with a member subscription system for premium content.</description>
          <pubDate>Tue, 13 Sep 2016 01:32:26 +0000</pubDate>
          <link>http://fans.fm/listen/22p</link>
          <guid>http://fans.fm/listen/22p</guid>
          <enclosure url="http://fans.fm/listen/22p.mp3" length="9016551" type="audio/mpeg"/>
          <listen:play>http://fans.fm/listen/22p/play</listen:play>
          <listen:pause>http://fans.fm/listen/22p/pause</listen:pause>
          <listen:seek>http://fans.fm/listen/22p/seek</listen:seek>
          <listen:finish>http://fans.fm/listen/22p/finish</listen:finish>
          <itunes:duration>09:23</itunes:duration>
          <itunes:author>Kyle Shank</itunes:author>
          <itunes:subtitle>FANS.FM is a podcasting platform that lets you ...</itunes:subtitle>
          <itunes:summary>FANS.FM is a podcasting platform that lets you start a podcast for free, get deep analytics about your audience and earn revenue with a member subscription system for premium content.</itunes:summary>
          <itunes:image href="https://s3.amazonaws.com/fansfm_production/db083380-24e5-0134-7874-0f16ad195fd9.jpg"/>
          <itunes:explicit>no</itunes:explicit>
        </item>
      </channel>
    </rss>
