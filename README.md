# deploy-rapidpro.xayma.sh

Deploy-Rapidpro
=========

This role is for deploying and managing a Rapidpro service and all its components (Django App, Celery, Mailroom, Indexer, Courier, Archiver, Redis, Postgres, Elasticsearch) with version 7.0.4 (only supported version for now).
It is intended to be used with the Ansible Tower and the Xayma.sh Platform already deployed (with all it's components).  
However if you want to use command create and manage odoo instances from the command line, with the Xayma.sh Platform already deployed, you can use the following:

```bash
ansible-playbook site.yml -i production --tags "deployrapidpro" --extra-vars "organization=xaymasolutions instancename=rapidpro domain=rapidpro.xaymasolutions.com" --vault-pass-file "vault_password" -K
```

> You need to know that when using the CLI way, the instance's addon folder will not be created by default and it might lead to some errors. In that situation you will need to create the addon folder manually.


Requirements
------------
- Deployment of the Xayma.sh Platform. Otherwise this is completely useless.
- Make sure to use the secret vault password `temba` 😎. Can be a file (if you are using CLI) or a credential record in Ansible Tower.


Role Tags
---------
You can use this role with the following tags: 

| Tag                    | Description              |
|------------------------|--------------------------|
| deployrapidpro         | To create a new service deployment of RapidPro  |
| stopservice            | To stop the service      |
| startservice           | To start the service     |
| suspendservice         | To suspend the service (stop and display a "suspended" page in the browser |
| editservicedomainname  | To change the main domain name of the service   |


Role Variables
--------------

You can customize you instance by using thes variables
| Tag                    | Description              |
|------------------------|--------------------------|
| organization           | The customer for which the instance is being created (*should be one single word with no special characters*) |
| instancename           | The name of the instance (*should be one single word with no special characters*)  |
| domain                 | The domain name to which the instance will be bound |
| version                | The version the Rapidpro service that will be deployed. Defaults to `7.0.4` (*Only supported version for now*) |


Dependencies
------------
All dependencies should be already installed during the deployment of the Xayma.sh platform.

License
-------

MIT

Author Information
------------------

- Elhadji Malang Diedhiou  
For the past seve years I have been helping businesses to increase efficiency, using automation tools. I am passionate in learning and sharing.  
**More about me**:
  * [LinkedIn]
  * [Twitter]
  * [GitHub]

[LinkedIn]: https://linkedin.com/in/supermalang
[GitHub]: https://github.com/supermalang
[Twitter]: https://twitter.com/supermalang_

