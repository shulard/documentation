History Plugin
==============

The `HistoryPlugin` notifies a Http\Client\Plugin\Journal of all successful and failed calls. As an example,
HttplugBundleThis use this plugin for collecting responses or exceptions associated with requests::

    use Http\Discovery\HttpClientDiscovery;
    use Http\Client\Plugin\PluginClient;
    use Http\Client\Plugin\HistoryPlugin;

    $historyPlugin = new HistoryPlugin(new \My\Journal\Implementation());

    $pluginClient = new PluginClient(
        HttpClientDiscovery::find(),
        [$historyPlugin]
    );


This plugin only collect data after resolution, for logging purpose it's best to use the `LoggerPlugin` which logs
as soon as possible.
