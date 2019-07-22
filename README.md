# dokku-haproxy

**haproxy tcp load balancer for dokku**

## Installation

Install the plugin:

```bash
dokku plugin:install https://github.com/reinventit/dokku-haproxy.git
```

### Credits
This plugin is largely inpsired on the HAPRoxy plugin found here:
https://github.com/256dpi/dokku-haproxy

Reason why you could use this plugin over the original HAProxy plugin is that this plugin is integrated with the default proxy management from Dokku and automatically exposes tcp ports defined in the dockerfile


### Installation Notes
 * This plugin will expose the stats interface on port 9090, its up to you to allow or block this port in your firewall.

## Usage

The plugin hooks into the default proxy management of dokku and can work alongside the vhost-nginx plugin for serices that expose TCP ports. Probably the best use cases for this plugin are:
* When an external reverse proxy is used in front of Dokku. Using HAProxy will not impact headers such as forwarder-for etc.
* When using dokku to run (micro)services that expose (multiple) TCP ports
