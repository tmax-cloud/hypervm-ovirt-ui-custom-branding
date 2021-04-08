# hypervm-ovirt-ui-custom-branding
ovirt ui custom branding repo

## How to install

### Step1 - Prepare files
```sh
git clone https://github.com/tmax-cloud/hypervm-ovirt-ui-custom-branding.git
```

### Step2 - Copy Target Branding Directory and Create a link

Copy hypervm branding files to ovirt engine installed directory.
Select your ovirt engine version properly.

- Command Exmaple:
    ```sh
    cd <git cloned directory>

    BRANDING_DIR=/<ovirt version>/hypervm.brand/
    # Example: BRANDING_DIR=/ovirt-4.4.3.11/hypervm.brand, check if the target directory is already exists, then backup and clear it.

    sudo cp BRANDING_DIR /usr/share/ovirt-engine/brands

    sudo ln -s /usr/share/ovirt-engine/brands/hypervm.brand/ /etc/ovirt-engine/branding/21-hypervm.brand
    ```