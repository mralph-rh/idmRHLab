Role Name
=========

This is a combination of roles to build out an IdM demo/PoC environment.

Requirements
------------

There are a few collections/packages that are required to run this.
  - redhat.rhel_idm (console.redhat.com)
  - redhat.rhel_system_roles (console.redhat.com)
    - To install these collections you will need to log in to console.redhat.com and run:
      ansible-galaxy collection install redhat.rhel_idm
      ansible-galaxy collection install redhat.rhel_system_roles
  - ansible.windows
  - microsoft.ad collections
    - To Install run the following on the machine you are running Ansible on:
      ansible-galaxy collection install ansible.windows
      ansible-galaxy collection install microsoft.ad

If you are using WinRM to connect to your Windows server, you must also run the WinRM Memory Hotfix and WinRM Setup scripts on the Window server to allow WinRM to accept connections from Ansible.
The file is here: https://github.com/AlbanAndrieu/ansible-windows/blob/master/files/ConfigureRemotingForAnsible.ps1

Earlier versions of Windows server might need to upgrade PowerShell and .NET Framework. You can find instructions here: https://docs.ansible.com/ansible/latest/os_guide/windows_winrm.html

NOTE:
This playbook has been provided by Red Hat, but is outside the scope of the posted Service Level Agreements and support procedures (https://access.redhat.com/support/offerings/production/). 

The information is provided as-is and any configuration settings or installed applications made from the information in this playbook could make the Operating System unsupported by Red Hat Global Support Services. The intent of this article is to provide information to accomplish the system's needs. Use of the information in this article at the user's own risk.


Role Variables
--------------

All variables are listed in the inventory file.

Dependencies
------------

secret.yml will need to be updated with your secrets and encrypted. The password for your vault will need to be added to .passwordStore for decrypting secret.yml when the playbook is ran. Finally the .gitignore will need need to have the to be updated to not add secret.yml and .passwordStore added to your git repos.

License
-------

GPL-3.0

Author Information
------------------

Mike Ralph is a Principal Technical Account Manager for NAPS.
