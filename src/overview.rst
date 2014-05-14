Overview of Curb's API
======================

Curb's API stores all data as a time-series using ISO compatible
timestamps and a value that can either be a double, float, or integer.

Curb supports downsampling or "rolling up" data using a specified
function (mean, sum, count, etc...) and a `time duration
<http://en.wikipedia.org/wiki/ISO_8601#Durations>`_ as well as
upsampling or "interpolation" of data (good for filling in gaps).
