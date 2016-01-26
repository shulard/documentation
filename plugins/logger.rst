Logger Plugin
=============

The ``LoggerPlugin`` converts requests, responses and exceptions to strings and logs them with a PSR3_ compliant logger::

    use Http\Discovery\HttpClientDiscovery;
    use Http\Client\Plugin\PluginClient;
    use Http\Client\Plugin\LoggerPlugin;
    use Monolog\Logger;

    $loggerPlugin = new LoggerPlugin(new Logger('http'));

    $pluginClient = new PluginClient(
        HttpClientDiscovery::find(),
        [$loggerPlugin]
    );

By default it uses ``Http\Message\Formatter\SimpleFormatter`` to format the request or the response into a string,
which will be used in the log message but you can use any formatter implementing the
``Http\Message\Formatter`` interface::

    $formatter = new \My\Formatter\Implemenation();

    $loggerPlugin = new LoggerPlugin(new Logger('http'), $formatter);

.. _PSR3: http://www.php-fig.org/psr/psr-3/
