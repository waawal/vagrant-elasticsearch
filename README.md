# Elasticsearch on Vagrant
precise64 (Ubuntu 12.04 LTS)

This is a Vagrant machine provisioned with Ansible.
It is made for development rather than deployment, a couple of very useful plugins
has been included to aid you in your development.

## Instructions

* Install [Vagrant](http://www.vagrantup.com/)
* Install [Ansible](http://docs.ansible.com/intro_installation.html)
* Clone this repo
* Run `vagrant up` from inside the repository directory

You should now have a `elasticsearch` server up and running and reachable 
from your host machine on

    http://localhost:9200

## Plugins

### Inquisitor
[polyfractal/elasticsearch-inquisitor](https://github.com/polyfractal/elasticsearch-inquisitor)

[http://localhost:9200/_plugin/inquisitor/](http://localhost:9200/_plugin/inquisitor/)

### Paramedic
[karmi/elasticsearch-paramedic](https://github.com/karmi/elasticsearch-paramedic)

[http://localhost:9200/_plugin/paramedic/index.html](http://localhost:9200/_plugin/paramedic/index.html)

### Bigdesk
[lukas-vlcek/bigdesk](https://github.com/lukas-vlcek/bigdesk)

[http://localhost:9200/_plugin/bigdesk/](http://localhost:9200/_plugin/bigdesk/)

### Head
[mobz/elasticsearch-head](https://github.com/mobz/elasticsearch-head)

[http://localhost:9200/_plugin/head/](http://localhost:9200/_plugin/head/)

---

You can install your own plugins with the standard elasticsearch plugin executable:

    $ sudo /usr/share/elasticsearch/bin/plugin -install elasticsearch/elasticsearch-analysis-icu/2.0.0

## License

MIT

---

    $ vagrant up
    Bringing machine 'default' up with 'virtualbox' provider...
    [default] Importing base box 'precise64'...
    [default] Matching MAC address for NAT networking...
    [default] Setting the name of the VM...
    [default] Clearing any previously set forwarded ports...
    [default] Clearing any previously set network interfaces...
    [default] Preparing network interfaces based on configuration...
    [default] Forwarding ports...
    [default] -- 22 => 2222 (adapter 1)
    [default] -- 9200 => 9200 (adapter 1)
    [default] Booting VM...
    [default] Waiting for machine to boot. This may take a few minutes...
    [default] Machine booted and ready!
    [default] Setting hostname...
    [default] Mounting shared folders...
    [default] -- /vagrant
    [default] Running provisioner: ansible...

    PLAY [all] ********************************************************************

    GATHERING FACTS ***************************************************************
    ok: [default]

    TASK: [elasticsearch | Ensure python-pycurl is installed] *********************
    changed: [default]

    TASK: [elasticsearch | Ensure Elasticsearch apt signing key is installed] *****
    changed: [default]

    TASK: [elasticsearch | Ensure Elasticsearch 1.1.x repository is installed] *
    changed: [default]

    TASK: [elasticsearch | Ensure elasticsearch is installed] *********************
    changed: [default] => (item=openjdk-7-jre-headless,elasticsearch)

    TASK: [elasticsearch | Ensure elasticsearch config is in place] ***************
    changed: [default]

    TASK: [elasticsearch | Ensure head (Plugin) is installed] *********************
    changed: [default]

    TASK: [elasticsearch | Ensure Paramedic (Plugin) is installed] ****************
    changed: [default]

    TASK: [elasticsearch | Ensure Bigdesk (Plugin) is installed] ******************
    changed: [default]

    TASK: [elasticsearch | Ensure Inquisitor (Plugin) is installed] ***************
    changed: [default]

    NOTIFIED: [elasticsearch | restart elasticsearch] *****************************
    changed: [default]

    PLAY RECAP ********************************************************************
    default                    : ok=11   changed=10   unreachable=0    failed=0


---

<img src="http://developer.rackspace.com/images/2013-11-04-welcome-to-performance-cloud-servers/simba.gif" width="100%" />
