silent-sysadmin.logical_volume
=========

Resize filesystems on Enterprise Linux hosts.

Requirements
------------

N/A

Role Variables
--------------
define dict `locallvs` with properties as shown below. 
```
locallvs:
  - lv_name: "defaultlv"
    vg_name: "defaultvg"
    lv_size: "100%FREE"
    lv_allow_shrink: false
    target_disk: /dev/vdb
    fstype: xfs
    state: mounted
    automount: true
    mount_path: /mnt
```
Dependencies
------------

N/A

Example Playbook
----------------

```
    - hosts: server
      roles:
        - role: silent-sysadmin.logical_volumes
          vars:
           locallvs:
             - lv_name: "defaultlv"
               vg_name: "defaultvg"
               lv_size: "100%FREE"
               lv_allow_shrink: false
               target_disk: /dev/vdb
               fstype: xfs
               state: mounted
               automount: true
               mount_path: /mnt
```

License
-------

MIT

Author Information
------------------

- wmcd 
