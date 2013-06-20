Graphite datasource for Network Weathermap
==========================================

Simple plugin for php-weathermap that adds the ability to source information from Graphite

### Install 

Install to `lib/datasources`


### Usage 

TARGET graphite:(graphite_server)|in|(out)|(type)
  
    e.g. graphite:graphite.example.net:82|network.net1.router1_example_net.int.xe_0_0_2.outbytes|network.net1.router1_example_net.int.xe_0_0_2.inbytes|interface

    e.g. graphite:graphite.example.net:82|network.net1.router1_example_net.int.xe_0_0_2.rx|network.net1.router1_example_net.int.xe_0_0_2.tx|

- host - graphite server to use, if empty it will use the value define below to keep the weathermap conf clean
- in   - string of the ressource to graph
- out  - (optionnal) string of the ressource to graph for the other direction
- type - (optionnal) if set to "interface" will add "scale(scaleToSeconds(nonNegativeDerivative($targetIn),1),8)" to get the numbers as bytes per seconds. (Doesn't work yet if the counter wraps). You can also add the operators directly to the in or out value.

