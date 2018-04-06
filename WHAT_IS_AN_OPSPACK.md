# What is an Opspack?

## Basics of Opspacks

An Opspack is an integration in Opsview Monitor to add extra functionality by monitoring the state, performance, or system health for a particular technology or service.

For example, an Opspack may monitor:

* CPU load
* Disk space
* Memory usage

The aim of an Opspack is for a user to be able to add it to a host in Opsview Monitor, and it will provide everything the user needs to monitor that host without any further configuration.

An Opspack consists of a plugin, configuration file and info file. The plugins can be written in almost any programming language and should contain the logic for how to retrieve an interpret the data from the technology/service being monitored. The config file describes how the plugins should be used. The info file just provides name and version for the Opspack.

## Service Checks, Metrics and Statuses

An Opspack will consist of several service checks, each of them should include a status and relevant metrics. When monitoring a service, a status can be returned based on the metric's current value. There are four statuses available from the result of a metric:

  * OK
  * WARNING
  * CRITICAL
  * UNKNOWN

For example, if we were to monitor the amount of free disk space on a server, we can define what values will trigger the above statuses. The psuedocode for how our plugin would define this is as follows:

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

## How to create an Opspack

For information on how to create your own Opspack, see the following guide: [How to create your own Opspack](https://github.com/opsview/Opsview-Integrations/blob/master/CREATE_OPSPACK.md)
