# What is an Opspack?

An Opspack is an integration in Opsview Monitor which allows you to monitor the status, performance and system health for a particular technology or service you wish to monitor.

Opspacks are used as templates for how a host should be monitored and they provide multiple service checks by default to monitor the different aspects of the host. For example, an Opspack may monitor:

* CPU load
* Disk capacity
* Memory usage

The aim of an Opspack is for a user to be able to apply it to a host in Opsview Monitor and it will provide everything the user needs to monitor that host without any further configuration.

An Opspack consists of a monitoring plugin, configuration file and info file:

* The monitoring plugin can be written in almost any programming language and contains the logic for how to retrieve and interpret the data from the technology/service being monitored

* The configuration file describes how the plugins should be used and which service checks the Opspack provides

* The info file provides the type of host the Opspack is for and the version number for the Opspack

## Service Checks, Metrics and Statuses

An Opspack will consist of several service checks, each of them should include a status and relevant metrics. When monitoring a service, a status can be returned based on the metric's current value. There are four statuses available from the result of a metric:

  * OK
  * WARNING
  * CRITICAL
  * UNKNOWN

For example, if we were to monitor the amount of free disk space on a server, we can define what values will trigger the above statuses. The pseudocode for how our plugin would define this is as follows:

```
if (free_disk >= 10GB):
  plugin_status = "OK"

elif (free_disk < 7.5GB):
  plugin_status = "CRITICAL"

elif (free_disk < 10GB ):
  plugin_status = "WARNING"

else:
  plugin_status = "UNKNOWN"
```

The output for a service check should be in the following format:

`OK - Disk Space is OK | free_disk=12GB`

The left side of the output is a status and summary message, the right side is used for performance data

## Where to Find Opspacks

Many Opspacks are provided by default in your Opsview Monitor system and can be used straight away. Check the **Host Templates** section for Opspacks you already have available.

If your Opsview Monitor system does not have an Opspack for what you need to monitor, then check our latest list of Opspacks here: [Opspacks on GitHub](https://github.com/opsview/Opsview-Integrations/blob/master/README.md)

Opspacks can also be found on our website: [Opsview Integrations](https://www.opsview.com/integrations)

Any Opspacks you download will have the .opspack (or .tar.gz) extension and can be imported into your Opsview Monitor system through the **Host Templates** section of Opsview Monitor.

## How to Create an Opspack

If you need to monitor a type of host that doesn't have an Opspack yet, then it is possible to create your own Opspack within Opsview Monitor

For information on how to create your own Opspack, see the following guide: [How to create your own Opspack](https://github.com/opsview/Opsview-Integrations/blob/master/CREATE_OPSPACK.md)
