Role Name
=========

This role adjusts the default GRUB timeout. When GRUB has a timeout of 0 (the default when using a cloud image), users might have difficultly troubleshooting boot problems because they cannot boot to an alternate kernel and they cannnot pass additional parameters to GRUB.

Role Variables
--------------

* `grub_timeout`: An integer used to set the GRUB timeout (in seconds). If a user does not interrupt the boot process within this timeout, then the system uses the default kernel with the default boot options. Defaults to a value of `0`.

* `grub_persistent`: A boolean that controls whether a change to the GRUB timeout is persistent or temporary. A persistent change also updates the `/etc/default/grub` file so that the new timeout will be applied, even if students install a new kernel. Defaults to a value of `true`.

Example Playbook
----------------

     
    - name: sets the GRUB timeout
      hosts: all
      become: true
      roles:
        - role: test
          grub_timeout: 15
          grub_persistent: true

License
-------

BSD
