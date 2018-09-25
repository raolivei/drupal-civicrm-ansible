-- # drupal-civicrm-ansible
-- Drupal - CiviCRM Ansible Demo installation to AWS

Automated Drupal and CiviCRM secure cloud installation with SSL certificate using https://letsencrypt.org/

Automates the creation of a new server with Drupal 7 and CiviCRM using Ansible. 

The server uses Nginx on an AWS micro instance

The automation installs Drupal 7 and CiviCRM on the server in a secure fashion with SSL certificate from https://letsencrypt.org/. 
CiviCRM and Drupal are installed in different databases as this is considered best practice.

Use this as starting point for your own setups.


To be able to use the AWS via Ansible we are going to use boto library. To install it you just need to run this command.

$ sudo apt install -y python-pip
$ pip install boto

Once boto is installed you need to setup your AWS credentials into the home folder (~/.boto)

[Credentials]
AWS_ACCESS_KEY_ID=...
AWS_SECRET_ACCESS_KEY=…

Update that to match your credentials.
Once that step is completed you can run the installation playbook.

Change directory to the directory holding the ansible yml files.

$ ansible-playbook site.yml

For a more verbose output use -vvv

$ ansible-playbook -vvv site.yml 

Of course you might wanna do own configs within the files.

Like it? -> Enjoy it ! -> Star. 

Thanks.

## sources of research ##
https://docs.nginx.com/nginx/deployment-guides/amazon-ec2-instances-for-nginx/
https://letsencrypt.org/getting-started/
https://github.com/certbot/certbot
https://boto3.amazonaws.com/v1/documentation/api/latest/guide/configuration.html
http://docs.pythonboto.org/en/latest/boto_config_tut.html#credentials