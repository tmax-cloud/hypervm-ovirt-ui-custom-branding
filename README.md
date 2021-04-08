# hypervm-ovirt-ui-custom-branding
ovirt ui custom branding repo.

## Purpose
1. ovirt webadmin UI branding
2. ovirt VM portal UI branding

## Prepare Installation
prepare branding install files

- Command:
```sh
git clone https://github.com/tmax-cloud/hypervm-ovirt-ui-custom-branding.git
```

## How to install - ovirt webadmin UI branding

### Copy Target Branding Directory and Create a link

Copy hypervm branding files to ovirt engine installed directory.
Select your ovirt engine version properly.

- Command Exmaple:
    ```sh
    cd <git cloned directory>

    TARGET_VERSION_DIR=./<ovirt version>/ # example: TARGET_VERSION_DIR=./ovirt-4.4.3.11/
    BRANDING_DIR=${TARGET_VERSION_DIR}hypervm.brand/

    sudo cp -r ${BRANDING_DIR} /usr/share/ovirt-engine/brands/

    sudo ln -s /usr/share/ovirt-engine/brands/hypervm.brand/ /etc/ovirt-engine/branding/21-hypervm.brand
    ```

## How to install - ovirt VM portal UI branding

### Copy Target Branding files

- Command Exmaple:
    ```sh
    cd <git cloned directory>

    TARGET_VERSION_DIR=./<ovirt version>/ # example: TARGET_VERSION_DIR=./ovirt-4.4.3.11/

    # run install ovirt-web-ui-script
    sudo sh ${TARGET_VERSION_DIR}ovirt-web-ui-install.sh
    ```