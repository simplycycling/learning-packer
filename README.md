Just a simple repo to help me see how packer and ansible work together.

To run packer with the included Ansible playbook, run the following:

    packer build -var 'aws_access_key=AKIA...' -var 'aws_secret_key=...' example.json
    
Obviously, substitute your own aws_access_key and aws_secret_key.

You'll probably also want to substitute your own password and public key
in local.yml.