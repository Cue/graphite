Tools That Work With Graphite
=============================

Diamond
-------
`Diamond`_ is a Python daemon that collects system metrics and publishes them to Graphite. It is
capable of collecting cpu, memory, network, I/O, load and disk metrics. Additionally, it features
an API for implementing custom collectors for gathering metrics from almost any source.


jmxtrans
--------
`jmxtrans`_ is a powerful tool that performs JMX queries to collect metrics from Java applications.
It is requires very little configuration and is capable of sending metric data to several
backend applications, including Graphite.


statsd
------
`statsd`_ is a simple daemon for easy stats aggregation, developed by the folks at Etsy.


Ganglia
-------
`Ganglia`_ is a scalable distributed monitoring system for high-performance computing systems
such as clusters and Grids. It collects system performance metrics and stores them in RRD,
but now there is an
`add-on <https://github.com/ganglia/ganglia_contrib/tree/master/graphite_integration/>`_
that allows Ganglia to send metrics directly to Graphite. Further integration work is underway.


collectd
--------
`collectd`_ is a daemon which collects system performance statistics periodically and provides
mechanisms to store the values in a variety of ways, including RRD. To send collectd merics into carbon/graphite, use:

- Jordan Sissel's node collectd-to-graphite_ proxy
- Joe Miller's perl collectd-graphite_ plugin
- Gregory Szorc's python collectd-carbon_ plugin
- Scott Sanders's C collectd-write_graphite_ plugin

Graphite can also read directly from `collectd`_'s RRD files. RRD files can
simply be added to ``STORAGE_DIR/rrd`` (as long as directory names and files do not
contain any ``.`` characters). For example, collectd's
``host.name/load/load.rrd`` can be symlinked to ``rrd/collectd/host_name/load/load.rrd``
to graph ``collectd.host_name.load.load.{short,mid,long}term``.


Logster
-------
`Logster`_ is a utility for reading log files and generating metrics in Graphite or Ganglia.
It is ideal for visualizing trends of events that are occurring in your application/system/error
logs. For example, you might use logster to graph the number of occurrences of HTTP response
code that appears in your web server logs.


Rocksteady
----------
A system that ties together Graphite, `RabbitMQ`_, and `Esper`_. Developed by
AdMob (who was then bought by Google), this was released by Google as open source
(http://google-opensource.blogspot.com/2010/09/get-ready-to-rocksteady.html).
Learn more here, http://code.google.com/p/rocksteady/


.. _Diamond: http://opensource.brightcove.com/project/Diamond/
.. _jmxtrans: http://code.google.com/p/jmxtrans/
.. _statsd: https://github.com/etsy/statsd
.. _Ganglia: http://ganglia.info/
.. _collectd: http://collectd.org/
.. _collectd-to-graphite: https://github.com/loggly/collectd-to-graphite
.. _collectd-carbon: https://github.com/indygreg/collectd-carbon
.. _collectd-graphite: https://github.com/joemiller/collectd-graphite
.. _collectd-write_graphite: https://github.com/jssjr/collectd-write_graphite
.. _Logster: https://github.com/etsy/logster
.. _RabbitMQ: http://www.rabbitmq.com/
.. _Esper: http://esper.codehaus.org/
