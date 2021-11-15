
# hypervm-ovirt-ui-custom-branding
OUTDATED, Moved to ovirt-engine(https://github.com/tmax-cloud/ovirt-engine) and ovirt-web-ui(https://github.com/tmax-cloud/ovirt-web-ui)

ovirt ui custom branding repo.

## Purpose
1. ovirt webadmin UI branding
2. ovirt VM portal UI branding

## Prepare Installation
prepare branding install files and clean original brand directory and symlink

- Command:
```sh
git clone https://github.com/tmax-cloud/hypervm-ovirt-ui-custom-branding.git

# remove symlink
rm -rf /etc/ovirt-engine/branding/00-ovirt.brand/

# backup and remove original branding directory
rm -rf /usr/share/ovirt-engine/brands/ovirt.brand/
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

    cd ${TARGET_VERSION_DIR}

    # run install ovirt-web-ui-script
    sudo sh ./ovirt-web-ui-install.sh
    ```

## After install

Please restart ovirt-engine

- Command:

```sh
sudo systemctl restart ovirt-engine

# and check ovirt-engine status
sudo systemctl status ovirt-engine
```
