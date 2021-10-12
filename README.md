# Infrastructure for Radiomics via Ansible

This is the home for the deployment scripts used to setup the site `https://data.radiomics.io`,
a Radiomics platform intended to be a publicly available computational radiomics platform for the
automated extraction of quantitative imaging features.

It deploys a default girder installation along with the `xtk_demo`, `cornerstone_demo` and `oauth` plugins enabled
and is expected to be associated with an EC2 instance and a S3 asset store.

## Funding

This work was supported in part by the US National Cancer Institute grant 5U24CA194354, Quantitative Radiomics System Decoding the Tumor Phenotype.

## History

Created in 2015, this project was originally hosted at `https://github.com/crad/infrastructure`.

In late 2015, the team refocused its effort to develop the `pyradiomics` python package, the `SlicerRadiomics`
Slicer extension and the site [radiomics.github.io][radiomics-github-io] hosted at https://github.com/Radiomics.

In early 2021, the `pyradiomics` and the `SlicerRadiomics` projects were transferred to https://github.com/AIM-Harvard.

Finally, in August 2021, this project was renamed from `infrastructure` to `data-radiomics-io-infrastructure` and transferred
to https://github.com/Kitware and the `crad` GitHub organization was removed.

[radiomics-github-io]: https://web.archive.org/web/20210813041540/https://radiomics.github.io/

# Guides

## Shell into the instance as ubuntu

    ssh -i radiomics-girder.pem ubuntu@data.radiomics.io

## To provision

    ansible-playbook -i plugins/inventory/ec2.py provision.yml -u ubuntu \
        --private-key=radiomics-girder.pem -e girder_admin_password=<insert password here>
