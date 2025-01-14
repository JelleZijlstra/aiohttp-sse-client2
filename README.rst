This is a fork of the `aiohttp-sse-client <https://github.com/rtfol/aiohttp-sse-client>`__
project by Jason Hu. The motivations for the fork are:

* Better error messages when the request fails (`#190 <https://github.com/rtfol/aiohttp-sse-client>`__)
* Update the library to support new Python versions

The fork will be retired if the upstream package comes back alive.

Fork changelog
--------------

* 0.3.0 (February 7, 2023)

  * Drop support for Python 3.6
  * Support Python 3.10 and 3.11
  * Include response body in exception for non-200 response codes

Original README follows:

==========
SSE Client
==========


.. image:: https://img.shields.io/pypi/v/aiohttp_sse_client.svg
        :target: https://pypi.python.org/pypi/aiohttp_sse_client

.. image:: https://img.shields.io/travis/com/rtfol/aiohttp-sse-client.svg
        :target: https://travis-ci.com/rtfol/aiohttp-sse-client

.. image:: https://readthedocs.org/projects/aiohttp-sse-client/badge/?version=latest
        :target: https://aiohttp-sse-client.readthedocs.io/en/latest/?badge=latest
        :alt: Documentation Status

.. image:: https://pyup.io/repos/github/rtfol/aiohttp-sse-client/shield.svg
     :target: https://pyup.io/repos/github/rtfol/aiohttp-sse-client/
     :alt: Updates


A Server-Sent Event python client base on aiohttp, provides a simple interface to process `Server-Sent Event <https://www.w3.org/TR/eventsource>`_.

* Free software: Apache Software License 2.0
* Documentation: https://aiohttp-sse-client.readthedocs.io.


Features
--------

* Full asyncio support
* Easy to integrate with other aiohttp based project
* Auto-reconnect for network issue
* Support python 3.6 and above

Usage
--------
.. code-block:: python

    from aiohttp_sse_client2 import client as sse_client

    async with sse_client.EventSource(
        'https://stream.wikimedia.org/v2/stream/recentchange'
    ) as event_source:
        try:
            async for event in event_source:
                print(event)
        except ConnectionError:
            pass

Credits
-------

This project was inspired by `aiosseclient <https://github.com/ebraminio/aiosseclient>`_,
`sseclient <https://github.com/btubbs/sseclient>`_, and `sseclient-py <https://github.com/mpetazzoni/sseclient>`_.

This package was created with Cookiecutter_ and the `audreyr/cookiecutter-pypackage`_ project template.

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _`audreyr/cookiecutter-pypackage`: https://github.com/audreyr/cookiecutter-pypackage
