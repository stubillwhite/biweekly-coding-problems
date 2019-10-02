# RSS Feed Pulse

This week we're writing a simple application to check RSS feeds.


There are a few complications and extensions that can

- Some of the feeds are probably dead now and will return an error
- Checking one feed at a time is a nice simple solution, but you could
  parallelize the checks if you wanted to run more quickly
- If a feed is still active then it would be nice to know when it was last
  updated, and how frequently it is being updated. Ideally, we could report the
  frequency of update in some human-friendly form, like "3 posts per week" or
  "1 post per month" instead of "0.02 posts per day"
