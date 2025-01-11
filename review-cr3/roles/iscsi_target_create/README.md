iscsi_target_create
===================

This role creates an iSCSI target.


Requirements
------------

A block device must be available so that the role can share it as an iSCSI target.


Role Variables
--------------

The role accepts the following variables:

* `iscsi_target_create_disk`: The name of the block device to share (without the `/dev/` part).
  `vdb` by default.
* `iscsi_target_create_block_name`: The name associated to the block device in target.
  `<short_hostname>.disk1` by default.
* `iscsi_target_create_iqn`: The IQN for the shared device.
  `iqn.2021-04.com.example:<short_hostname>` by default.


Dependencies
------------

None


Example Playbook
----------------

```yaml
---
- name: Creating the iSCSI target
  hosts: storage
  become: true
  gather_facts: false

  tasks:
    - include_role:
        name: iscsi_target_create
      vars:
        iscsi_target_create_iqn: iqn.2021-04.com.example:disk1
        iscsi_target_create_disk: vdb
...
```

The `tests/` directory provides an additional example.


License
-------

GPL 3.0 or later.
