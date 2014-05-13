API Authentication
==================

Authentication for version one of the Curb API is simple and only
requires the explicit generation of an API key and API secret that are
base64 encoded and used in the ``Authorization: Basic
QWxhZGRpbjpvcGVuIHNlc2FtZQ==``

.. note:: cURL automatically Base64 encodes the authorization header for you!

Here is a basic example in Python that returns a list of series::

    import requests
    user = "4f//y1YFy5PpFLW"
    pass = "GrSCMg45heb7Y.IK.iogIOeQAi2C4yb./iPT6hnZ5UZwpTS1z4qWu"

    # This is important, it defines the API version and return format
    accept = "application/vnd.curb.v1+json"

    r = requests.get("https://api.energycurb.com/series",
                     auth=(key, sec),
                     headers={"accept": accept})
