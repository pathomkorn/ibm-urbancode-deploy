#Register UCD Agent as a Linux Service

* Edit UCD agent start script
```bash
# vi /opt/ibm-ucd/agent/bin/init/agent
AGENT_USER=root
AGENT_GROUP=root
```
* Register UCD agent as a service
```bash
# ln -s /opt/ibm-ucd/agent/bin/init/agent /etc/init.d/ibm-ucd-agent
# chkconfig --add ibm-ucd-agent
# service ibm-ucd-agent start
```
