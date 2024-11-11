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

The Satellite registration role (subscribe-sat) is for Satellite 6.15 and below.

Role Variables
--------------

All variables are listed in the inventory file.

Dependencies
------------

See Requirements.

License
-------

GPL-3.0

Author Information
------------------

Mike Ralph is a Senior Technical Account Manager for NAPS.
