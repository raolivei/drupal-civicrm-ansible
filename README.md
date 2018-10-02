# ansible-aws_drupal_civicrm

Drupal - CiviCRM Ansible Demo installation to AWS

- Cloud installation of Drupal 7 and CiviCRM in a secure fashion with SSL certificates from https://letsencrypt.org/ using Ansible.
- The target server is an EC2 instance configured with a new security group.
- A Route 53 Record Set is created in a registered domain so access to the app over the internet is possible (using SSL).
- The server uses Nginx on an AWS micro instance.
- CiviCRM and Drupal are installed in different databases as this is considered best practice.
- Nginx secure configurations made for both Drupal and CiviCRM.
- Drupal configured to have a private files folder. This is secure within the NGINX configuration.
- CiviCRM settings modified so that CiviCRM extension directory is set using settings files variables
- The playbook is to be aimed for use on a Debian based OS. It was tested running on Ubuntu 18.04 LTS.
- Drush is installed to the server for the appropriate user.
- Git is installed in the server for the appropriate user.



## Prerequisites:

* python 2.7
* boto
* boto3
* ansible 2.6.4

To be able to use the AWS via Ansible we are going to use boto and boto3 libraries.



## Install

1. Leverage your privileges

`$ sudo su`

2. Install prerequisites

`$ apt install -y python-pip`

`$ pip install boto`

`$ pip install boto3`

`$ apt install -y ansible`


3. A keypair and a keypair path must be given as values for 'keypair' and 'keypair_path variables in site.yml.

4. AWS credentials need to be given. There are many different ways to do it, I suggest storing the creds in environment variables:

`$ export AWS_ACCESS_KEY_ID="<Key_value_here>"`

`$ export AWS_SECRET_ACCESS_KEY="<key_value_here>"`

5. Update `<key_value_here>` to match your credentials.

6. Change to the directory containing the ansible files:

`$ ansible-playbook site.yml`

For verbose output, use -vvv

`$ ansible-playbook -vvv site.yml`


Wait for the deployment to be completed.



## DRUPAL
https://site.raolivei.net<br>
site: Demo Site<br>
account name: admin<br>
account pass: admin
db name: drupal
db user: drupal_user
db pass: DrupalSecretPassword


## CiviCRM
db name: civicrm
user: civicrm_user
pass: CiviCrmSecretPassword



Thank you.
Rafael Oliveira
2 Oct 2018


## References
https://docs.nginx.com/nginx/deployment-guides/amazon-ec2-instances-for-nginx/
https://letsencrypt.org/getting-started/
https://github.com/certbot/certbot
https://boto3.amazonaws.com/v1/documentation/api/latest/guide/configuration.html
http://docs.pythonboto.org/en/latest/boto_config_tut.html#credentials
http://stackoverflow.com/
