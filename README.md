# listen-namespace

A simple RSS namespace extensions for podcast feeds.

The goal is to create a spec that would behave like a trackback for audio listening behavior.  Podcast clients and apps that implement the namespace will allow podcast hosts to track user engagement in a detailed way.

The way the namespace works is pretty straightforward.  There are 3 new elements you can add to *item* tags in your feed: *play*, *pause* and *seek*.  Each element will contain a callback url that will get triggered when the user plays an episode, pauses an episode or seeks within an episode.

Here is what an example *item* would look like:

```<item>
      <title>1.0 - Welcome to FANS.FM!</title>
      <description>FANS.FM is a podcasting platform that lets you start a podcast for free, get deep analytics about your audience and earn revenue with a member subscription system for premium content.</description>
      <pubDate>Tue, 13 Sep 2016 01:32:26 +0000</pubDate>
      <link>http://fans.fm/listen/22p</link>
      <guid>http://fans.fm/listen/22p</guid>
      <enclosure url="http://fans.fm/listen/22p.mp3" length="9016551" type="audio/mpeg"/>
      <listen:play>http://fans.fm/listen/22p/play</listen:play>
      <listen:pause>http://fans.fm/listen/22p/pause</listen:pause>
      <listen:seek>http://fans.fm/listen/22p/seek</listen:seek>
      <itunes:duration>09:23</itunes:duration>
      <itunes:author>Kyle Shank</itunes:author>
      <itunes:subtitle>FANS.FM is a podcasting platform that lets you ...</itunes:subtitle>
      <itunes:summary>FANS.FM is a podcasting platform that lets you start a podcast for free, get deep analytics about your audience and earn revenue with a member subscription system for premium content.</itunes:summary>
      <itunes:image href="https://s3.amazonaws.com/fansfm_production/db083380-24e5-0134-7874-0f16ad195fd9.jpg"/>
      <itunes:explicit>no</itunes:explicit>
    </item>
