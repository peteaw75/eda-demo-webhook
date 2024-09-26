# eda-demo-webhook
Demo showing EDA receiving events from external sources e.g. monitoring applications and responding automatically based on conditions/logic.
## Trigger messages

### No action since conditions did not match
~~~
curl -H 'Content-Type: application/json' -d "{\"message\": \"Test-Restart webserver\"}" hlaaeda01.idm.lokidev.xyz:5000
~~~

### EDA action triggered as conditions met.
~~~
curl -H 'Content-Type: application/json' -d "{\"message\": \"Restart webserver\", \"server\": \"hlrhel801.idm.lokidev.xyz\"}" hlaaeda01.idm.lokidev.xyz:5000
~~~

### No action since conditions did not match
~~~
curl -H 'Content-Type: application/json' -d "{\"message\": \"Test-Restart webserver\", \"server\": \"hlrhel803.idm.lokidev.xyz\"}" hlaaeda01.idm.lokidev.xyz:5000
~~~

### EDA action triggered since conditions matches. Error running the playbooks as hlrhel801 does not have the http service installed.
~~~
curl -H 'Content-Type: application/json' -d "{\"message\": \"Restart webserver\", \"server\": \"hlrhel802.idm.lokidev.xyz\"}" hlaaeda01.idm.lokidev.xyz:5000
~~~
### EDA action trigger with authentication token
~~~
curl -H 'Authorization: Bearer Redhat!' -H 'Content-Type: application/json' -d "{\"message\": \"Restart webserver\", \"server\": \"hlrhel801.idm.lokidev.xyz\"}" hlaaeda01.idm.lokidev.xyz:5000
~~~
