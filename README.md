# Configure JEA for vScope with Ansible

This is an example playbook for configuring Just Enough Administration (JEA) on Windows servers in order to connect to them from vScope (https://www.vscope.net/)

## Prereqs
You need an Ansible host to run the playbook from. It has to be configured with the necessary Python packages to use WinRM and Kerberos.
- pywinrm
- pykerberos

You need to configure /etc/krb5.conf for your environment. See [docs](https://docs.ansible.com/ansible/latest/os_guide/windows_winrm.html#configuring-host-kerberos).

All your Windows servers needs to have WinRM enabled over HTTP. If HTTPS is to be used, adjustments must me made. JEA requires Windows Server 2016 or higher, or an older OS with WMF 5.1 installed

## Inventory
Copy the example inventory from the repository

`cp inventory_example.yaml my_inventory.yaml`

Add your own hosts and credentials. You can add multiple hosts under `hosts:`.

## Run
Execute the playbook by running `ansible-playbook configure_vscope_jea.yaml -i my_inventory.yaml`
