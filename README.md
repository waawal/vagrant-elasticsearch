# Elasticsearch on Vagrant
Precise64 (Ubuntu 12.04 LTS)

## Instructions

* Install Vagrant
* Install Ansible
* Clone this repo
* Run `vagrant up` from inside this directory

You should now have a `elasticsearch` server up and running and reachable 
from your host machine on *http://localhost:9200*

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

    TASK: [elasticsearch | Ensure Elasticsearch 0.90.x repository is installed] ***
    changed: [default]

    TASK: [elasticsearch | Ensure elasticsearch is installed] *********************
    changed: [default] => (item=openjdk-7-jre-headless,elasticsearch)

    TASK: [elasticsearch | Ensure elasticsearch config is in place] ***************
    changed: [default]

    NOTIFIED: [elasticsearch | restart elasticsearch] *****************************
    changed: [default]

    PLAY RECAP ********************************************************************
    default                    : ok=7    changed=6    unreachable=0    failed=0


<img src="http://developer.rackspace.com/images/2013-11-04-welcome-to-performance-cloud-servers/simba.gif" width="100%" />
