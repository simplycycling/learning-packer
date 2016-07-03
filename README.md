# Learning-Packer

Just a simple repo to help me see how packer and ansible work together.

To run packer with the included Ansible playbook, run the following:

    packer build -var 'aws_access_key=AKIA...' -var 'aws_secret_key=...' example.json
    
Obviously, substitute your own aws_access_key and aws_secret_key.

You'll probably also want to substitute your own password and public key
in local.yml.

### Vars

In the local.yml file, there are 3 variables:

- user
- password
- key

User is your user name, the one you'd like available to you on the host 
that you spin up from the AMI that this creates. Password is...your 
password. Key is your public ssh key. You'll see that mine is listed in
a github URL. If you've uploaded your public ssh key to github (for the
purpose of interacting with github via ssh), then github has made your
key publicly available. Just swap my username out for yours.

A note about passwords - do not plug your password in the password field
in plain text. Read this to learn how to encrypt your password in a way
that works with Ansible:

https://docs.ansible.com/ansible/faq.html#how-do-i-generate-crypted-passwords-for-the-user-module

Do that, take the outputted string that it gives you, and use that as
your password variable.