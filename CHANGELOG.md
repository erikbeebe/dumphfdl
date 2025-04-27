# CHANGELOG

## Version 1.6.1 (2024-02-03)

* Compatibility fix for liquid-dsp 1.6.0 and later

## Version 1.6.0 (2023-12-14)

* HFDL system table version updated to 52.

## Version 1.5.0 (2023-09-10)

* Added `--prettify-json` command line option which enables prettification of
  JSON payloads in libacars >= 2.2.0. This currently applies to OHMA messages
  only.

* The lifetime of the Aircraft_ID to ICAO hex code mapping cache can now be
  changed using `--aircraft-cache-ttl <number_of_seconds>` option.

## Version 1.4.1 (2023-03-26)

* Fixed a bug which caused incorrect decoding of some uplink MPDUs
  containing multiple LPDUs destined to the same aircraft (thx Dick,
  acarslogger)

## Version 1.4.0 (2022-11-14)

* Added support for periodic noise floor reporting via Etsy StatsD. This
  allows long-term noise floor monitoring and trending on all monitored
  HFDL channels. Enable with `--noise-floor-stats-interval <interval_seconds>`
  command line option (together with `--statsd address:port`, of course).
* Better handling of network errors when producing output to networked
  outputs (TCP, UDP, ZMQ). When the message delivery fails, the message
  now gets requeued and redelivered when the connection is reestablished.
* A few optimizations resulting in slightly lower CPU usage.

## Version 1.3.0 (2022-03-16)

* Added support for formatting decoded messages as JSON.

## Version 1.2.1 (2022-02-26)

* Fixed a bug that caused manual gain settings to be ineffective on devices
  which have auto gain enabled by default. dumphfdl now turns off AGC
  explicitly before setting gain elements.

## Version 1.2.0 (2021-11-17)

* Noise floor and signal level estimates are now computed and printed in
  message headers.
* Added --freq-as-squawk option which uses squawk field in the Basestation feed
  to convey HFDL channel frequency on which the position information has been
  received.
* The program can now decode data from I/Q samples piped onto standard input.
  This allows interoperation with I/Q data sources like GNURadio or KiwiSDR.
* Added `--read-buffer-size` option for setting input buffer size when decoding
  from an I/Q file or from standard input.
* Slightly better sensitivity.

## Version 1.1.0 (2021-10-29)

* Improved sensitivity (less CRC errors)
* Reduced CPU usage
* The program now builds and runs under MacOS

## Version 1.0.0 (2021-10-15)

* First public release
