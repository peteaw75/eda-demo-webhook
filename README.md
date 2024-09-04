# eda-demo-webhook

Trigger messages  
curl -H 'Content-Type: application/json' -d "{\\"message\\": \\"Ansible is alright\\"}" hlaaeda01.idm.lokidev.xyz:5000  
curl -H 'Content-Type: application/json' -d "{\\"message\\": \\"Message A\\"}" hlaaeda01.idm.lokidev.xyz:5000  
curl -H 'Content-Type: application/json' -d "{\\"message\\": \\"Message B\\"}" hlaaeda01.idm.lokidev.xyz:5000  

~~~
'Content-Type: application/json' -d "{\"message\": \"Test-Restart webserver\", \"server\": \"hlrhel803.idm.lokidev.xyz\"}" hlaaeda01.idm.lokidev.xyz:5000
~~~
