# What is a Monitoring Plugin?



Monitoring plugins are the most common and popular way of monitoring hosts. Monitoring plugins can be written in any language, from bash and C to Perl and Python, meaning anyone who can script can create plugins! In essence, a monitoring plugin is a translator that resides between Opsview Monitor and the item we wish to monitor. The plugin speaks both languages; It knows how to speak to Opsview in Opsview Monitor's language, and it knows how to talk to the Host in the Host's language.

## Overview of a Monitoring Plugin

A typical monitoring plugin will consist of the following stages:

### Accepting Arguments/Flags

The monitoring plugin should be able to accept flags when run from the command line. Most monitoring plugins require input in order to run, such as the IP address of the host you are monitoring, the port to use, authentication credentials, etc.

### Retrieval of Metrics

The monitoring plugin should use the API for the technology/service it is monitoring to be able to retrieve metrics for it. This will depend on what the monitoring plugin is monitoring, but should contain the logic specific to how this technology works.

### Evaluation and Output of Metrics

Once the metrics are retrieved, the plugin should interpret them how desired and evaluate the status and summary based on the metrics. There may be several different modes of how to use the plugin depending on which metrics you want to output.

## Opsview Plugin Libraries

To help create a monitoring plugin, the following libraries can be used to standardise the output and make it as easy as possible:

| Language | Source |
|:---------|--------|
| Go       | [go-plugin](https://github.com/opsview/go-plugin) |
| Perl     | [perl-plugin](https://github.com/opsview/monitoring-plugin-perl) |
| PowerShell | [powershell-plugin](https://github.com/opsview/monitoring-plugin-powershell) |
| Python   | [plugnpy](https://github.com/opsview/plugnpy) |

## Further Information

For more details on what monitoring plugins are and how they work in Opsview Monitor, see our documentation on the Knowledge Base: [Monitoring Plugins](https://knowledge.opsview.com/docs/monitoring-plugins)
