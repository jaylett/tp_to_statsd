# TP to statsd

Simple utility that pulls counts of TP entities by process, type and
state and blasts them into statsd gauges for your graphing pleasure.

Set the process or processes using `--process` one or more times
(doing this is recommended, as story state names overlap between
processes in TP, making the monitoring less helpful otherwise).

Set the entity types you care about using `--type` one or more
times. The script knows how to pluralize simple forms ("Bug" ->
"Bugs") and has an override for "UserStory" -> "Userstories", but
others you may have to update the code (and PR please!).

You need to set the API base URI, username and password, either by
`--api-base`, `--user` and `--password`, or the `TP_API_BASE`,
`TP_USER` and `TP_PASSWORD` environment variables.

Statsd can be configured using environment variables as well:
`STATSD_HOST` and `STATSD_PORT`, plus `STATSD_PREFIX` for prefixing the
keys and `STATSD_MAXUDPSIZE` if you have weird network issues to work
round. (The defaults are dependent on the `statsd` python package, but
should be sensible.)

## License and contact

MIT license; [source is on github][Package source]; please report bugs
there.

James Aylett

  [Package source]: https://github.com/jaylett/tp_to_statsd
