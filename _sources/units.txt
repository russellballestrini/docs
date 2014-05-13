Data Type Units
===============

The units of data stored by Curb is **Watts**, **Milli-Volt**, and **Volt
Ampere**. The primary unit value most users will be reading from the
API is Watts.

Basic transformations (converting to kw or kWh) on the units of the
values can be specified in the requests to the API, please refer to
:doc:`transformation`.

Periodicity and Time Ranges
---------------------------

When specifying the **periodicity** of a range request the `ISO 8601
Time Durations <http://en.wikipedia.org/wiki/ISO_8601#Durations>`_
standard is recognized; the default will always be one hour (``PT1H``)
if not specified.

Some common examples of periodicity specifications:

+--------------+----------+
| One Minute   | ``PT1M`` |
+--------------+----------+
| Five Minutes | ``PT5M`` |
+--------------+----------+
| One Hour     | ``PT1H`` |
+--------------+----------+
| One Day      | ``P1D``  |
+--------------+----------+
| Seven Days   | ``P7D``  |
+--------------+----------+
| One Week     | ``P1W``  |
+--------------+----------+
