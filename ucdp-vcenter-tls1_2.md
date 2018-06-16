# Connect Blueprint Designer with vCenter 6.7 with TLS 1.2

* By default, IBM Cloud Discovery service enables only TLS 1.0.

* Investigate by observe `/var/log/ibm-cloud-discovery-service/ibm-cloud-discovery-service.log` file

```
WARNING: EOF occurred in violation of protocol (_ssl.c:579) [in /usr/lib/python2.7/site-packages/clouddiscoveryservice/resources/clouds/vmware.py:59]
```

* Solve issue by modify `/usr/lib/python2.7/site-packages/clouddiscoveryservice/resources/clouds/vmware.py` file by changing `ssl.PROTOCOL_TLSv1` to `ssl.PROTOCOL_TLSv1_2`

* Restart IBM Cloud Discovery service

```
systemctl restart ibm-cloud-discovery.service
```