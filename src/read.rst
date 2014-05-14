Reading Data from the API
=========================

Read multiple series in bulk, from single series, or statistical
summary data for given series. *A maximum of 10,000 items will be
returned per-request.*

.. note:: All read methods except for **Summary** support unit value
          transformations.


Read Single
-----------

Read from a single series using its key, a given periodicity, time
range, rollup function, and (optional) transformation function.

.. centered:: GET /series/key/{key}/segment/

+-------------+---------------------------------------------------------------------------------+
| start       | Specifies the start date of the dataset (ISO8601): 2012-01-08T00:21:54.000+0000 |
+-------------+---------------------------------------------------------------------------------+
| end         | Specifies the end date of the dataset (ISO8601): 2012-01-09T00:21:54.000+0000   |
+-------------+---------------------------------------------------------------------------------+
| fold        | **Allowed values**: sum, min, max, mean, stddev, count                          |
+-------------+---------------------------------------------------------------------------------+
| period      | Periodicity of the data being requested: PT1H, P1W, PT37H                       |
+-------------+---------------------------------------------------------------------------------+
| transform   | **Allowed values**: kw                                                          |
+-------------+---------------------------------------------------------------------------------+
| interpolate | **Allowed values**: linear, zoh (if not specified, no interpolation happens)    |
+-------------+---------------------------------------------------------------------------------+
| tz          | Timezone for output: America/Chicago, America/Detroit, America/New_York         |
+-------------+---------------------------------------------------------------------------------+

Example
^^^^^^^^
.. centered:: GET /series/key/key1/segment/?start=2012-01-08&end=2012-01-09&period=PT6H&fold=mean&interpolate=linear

.. code-block:: javascript

        {
           "series":{
              "id":"01868c1a2aaf416ea6cd8edd65e7a4b8",
              "key":"key1",
              "name":"",
              "tags":[
                 "temp"
              ],
              "attributes":{
                 "temp":"1"
              }
           },
           "data":[
              {
                 "t":"2012-01-08T00:00:00.000+0000",
                 "v":4.00
              },
              {
                 "t":"2012-01-08T06:00:00.000+0000",
                 "v":3.00
              },
              {
                 "t":"2012-01-08T12:00:00.000+0000",
                 "v":2.00
              },
              {
                 "t":"2012-01-08T18:00:00.000+0000",
                 "v":3.00
              }
           ],
           "rollup":{
              "period":"PT6H",
              "fold":"mean",

           },
           "tz":"UTC",
           "interpolate": "linear"
        }


Read Bulk
---------

.. warning:: This method is not implemented for public consumption yet
             but will be soon.

Read from multiple series' using the given periodicity, time range,
rollup function, and (optional) transformation function.

Read Summary
------------

.. warning:: This method is not implemented for public consumption yet
             but will be soon.

Request a aggregate statistics on a specific series key.
