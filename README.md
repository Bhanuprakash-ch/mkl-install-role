Role Name
=========

Installs Math Kernel library along with the minimum GCC(4.8.5) version required on RedHat/Centos 6 machines. MKL and GCC have been precompiled.

Requirements
------------

You must use ansible 1.9.0.1 and have a RedHat/Centos 6 computer
CDH 5.5.x cluster
You need to add the following values to YARN's "NodeManager Environment Advanced Configuration Snippet (Safety Valve)" in CDH.
LD_LIBRARY_PATH=/usr/local/gcc-4.8.5/lib64/:/opt/intel/mkl/lib/intel64:$LD_LIBRARY_PATH
LD_RUN_PATH=/usr/local/gcc-4.8.5/lib64/:/opt/intel/mkl/lib/intel64:$LD_RUN_PATH
	

Example Playbook
----------------

If you wish to provide your own GCC and MKL package 
too:

    - hosts: servers
      become: yes
      become_user: root
      roles:
         - { role: install-mkl, MKL_PACKAGE_PATH: '{{SOME_PATH/VAR}}', GCC_PACKAGE_PATH: '{{SOME_PATH/VAR}}'  }
         
Not providing GCC and MKL will also work 
too:

    - hosts: servers
      become: yes
      become_user: root
      roles:
         - { role: install-mkl  }

License
-------
Outbound licenses
- GCC - https://gcc.gnu.org/onlinedocs/gcc-4.8.5/gcc/Copying.html#Copying 
  - [GCC source](https://s3.amazonaws.com/trustedanalytics/mkl-install-role/release/v0.1.0/gcc-4.8.5.tar.gz)
- MKL - https://software.intel.com/sites/default/files/managed/67/99/Master_EULA_for_Intel_Sw_Development_Products_March_2016.pdf 



