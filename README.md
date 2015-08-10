# Infrastructure for Radiomics via Ansible

## Shell into the instance as ubuntu

    ssh -i radiomics-girder.pem ubuntu@data.radiomics.io

## To provision

    ansible-playbook -i plugins/inventory/ec2.py provision.yml -u ubuntu \
        --private-key=radiomics-girder.pem -e girder_admin_password=<insert password here>
