# How To Create Your Own Opspack

See Opsview Documentation on Creating Opspacks here: [Opspacks](https://knowledge.opsview.com/docs/host-templates-2)

## What is an Opspack

An Opspack is an integration in Opsview Monitor to add extra functionality by monitoring the state, performance, or system health for a particular technology or service.

## Creating an Opspack in Opsview Monitor

An Opspack is the same as a Host Template in Opsview Monitor. It should be possible to import an Opspack, apply it to a host and the user should need no further configuration for it to start monitoring that host.

Follow these steps to create an Opspack/Host Template within Opsview Monitor:

### Adding a New Host Template

* Navigate to the Host Template Settings section

![Host Template Settings](/docs/img/host_templates.jpg)

* Click 'Add New'. Fill in the name and description for your Opspack

![New Host Template](/docs/img/new_host_template.jpg)

### Add Service Checks

* Add the service checks you require to your Host Template

![Add Service Checks to Host Template](/docs/img/add_service_checks.jpg)

### Export Opspack

* In the Host Template Settings, select your Host Template and then click 'Export Opspack'. This will download the host template as a .opspack file

![Export Opspack](/docs/img/export_opspack.png)

## Creating an Opspack outside of Opsview Montior

If you don't want to use the user interface you can create your Opspack by creating the following folder structure

```
opspack-name
  > plugins
    > plugin.py
  > config.json
  > info
```  

- opspack-name is the directory for your opspack

- plugins directory includes all the monitoring plugins that the opspack uses

- config.json describes to Opsview Monitor how to use the plugins

- info contains the name and version for the Opspack

Upload your Opspack as described [here](https://github.com/opsview/Opsview-Integrations/blob/master/UPLOAD_OPSPACK.md), and it will create the opspack file for you in GitHub
