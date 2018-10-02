-- # drupal-civicrm-ansible
-- Drupal - CiviCRM Ansible Demo installation to AWS

Cloud installation of Drupal 7 and CiviCRM in a secure fashion with SSL certificates from https://letsencrypt.org/ using Ansible.
The target server is an EC2 instance configured with a new security group.

The server uses Nginx on an AWS micro instance.

CiviCRM and Drupal are installed in different databases as this is considered best practice.



## Prerequisites:

* boto3
* ansible 2.6.4
* python 2.7

To be able to use the AWS via Ansible we are going to use boto library. To install it you just need to run this command.

# Install

Leverage your privileges
`$ sudo su`

Install prerequisites
`$ apt install -y python-pip
$ pip install boto3`

Point PYTHONPATH variable to your python installation directory

`$ export PYTHONPATH=/usr/local/lib/python2.7/dist-packages`


Once boto3 is installed, AWS credentials need to be setup. There are many different ways to do it, I suggest storing the creds in environment variables:

`$ export AWS_ACCESS_KEY_ID="<Key_value_here>"`
`$ export AWS_SECRET_ACCESS_KEY="<key_value_here>"`

Update `<key_value_here>` to match your credentials.

Once that step is completed you can run the installation playbook.

Change directory to the directory holding the ansible yml files.

$ ansible-playbook site.yml

For verbose output, use -vvv

$ ansible-playbook -vvv site.yml

Of course you might wanna do own configs within the files.

Like it? -> Enjoy it ! -> Star.

Thanks.

=== DRUPAL ===
https://{ec2_instance}:443
User: admin
Pass: admin

Screenshots:
https://www.dropbox.com/s/nk6r3xrn3e54cko/Screenshot%202018-09-26%2001.14.35.png?dl=0


## sources of research ##
https://docs.nginx.com/nginx/deployment-guides/amazon-ec2-instances-for-nginx/
https://letsencrypt.org/getting-started/
https://github.com/certbot/certbot
https://boto3.amazonaws.com/v1/documentation/api/latest/guide/configuration.html
http://docs.pythonboto.org/en/latest/boto_config_tut.html#credentials


---- to setup before deploying:

export PYTHONPATH=/usr/local/lib/python2.7/dist-packages

export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
