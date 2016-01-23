Cookie Plugin
=============

The `CookiePlugin` allow you to store cookies information in a `CookieJar` and reuse them on consequent requests according
to `RFC 6265`_ specification::

    use Http\Discovery\HttpClientDiscovery;
    use Http\Message\CookieJar;
    use Http\Client\Plugin\PluginClient;
    use Http\Client\Plugin\CookiePlugin;

    $cookiePlugin = new CookiePlugin(new CookieJar());

    $pluginClient = new PluginClient(
        HttpClientDiscovery::find(),
        [$cookiePlugin]
    );

.. _RFC 6265: https://tools.ietf.org/html/rfc6265
