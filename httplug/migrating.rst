Migrating to HTTPlug
====================

If you currently use a concrete HTTP client implementation or the Ivory HTTP Adapter,
migrating to HTTPlug should not be very hard.

Migrating from Ivory HTTP Adapter
---------------------------------

The monolithic Ivory package has been separated into several smaller, more specific packages.

Instead of ``Ivory\HttpAdapter\PsrHttpAdapter``, use ``Http\Client\HttpClient``.
The HttpClient simply has a method to send requests.

If you used the ``Ivory\HttpAdapter\HttpAdapter``, have a look at :ref:`client-common`
and use the ``Http\Client\Utils\HttpMethodsClient`` which wraps any HttpClient
and provides the convenience methods to send requests without creating
RequestInterface instances.

Migrating from Guzzle
---------------------

Replace usage of ``GuzzleHttp\ClientInterface`` with ``Http\Client\HttpClient``.
The ``send`` method is called ``sendRequest``.
Instead of the ``$options`` argument, configure the client appropriately during set up.
If you need different settings, create different instances of the client.
You can use :doc:`/plugins/index` to further tune your client.

If you used the ``request`` method, have a look at :ref:`client-common` and
use the ``Http\Client\Utils\HttpMethodsClient`` which wraps any HttpClient and
provides the convenience methods to send requests without creating
RequestInterface instances.
