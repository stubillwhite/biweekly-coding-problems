# RSS Feed Statistics #

I've been using the same RSS feed reader for many years, and although it's great as an article reader, it's not great at
indicating when feeds stop being updated or become inaccessible. As a result, over the years the feed list has grown
full of cruft and in need of spring cleaning. We're going write something to check all the feeds and indicate whether
they're still active.

There is an [OPML](http://dev.opml.org/spec1.html) file containing the feeds I've been reading [here](TBD). We're going
to parse the file, retrieve the RSS for the feed from the URL if we can, and for each feed we'll calculate:

  * Whether it still exists
  * When it was last updated
  * How frequently it is updated (one article a month, two a week, etc.)

This is a nice problem for multi-threading and error handling. There are lots of areas where errors can occur: OPML
parsing, feed URL accessibility, request timeout, statistic calculation, and so on. There are also at least a couple of
versions of [RSS Specifications](http://www.rss-specifications.com/rss-specifications.htm) that sources will be using
and we'll need to handle. Ideally you'll want to separate out the error handling aspects from the happy path.


--

Hi, folks. I'd like to kick this off again with a slightly more open-ended problem to have a play with. This might be a
fun exercise to do with Cats or Akka, if you fancy.
