Role Name
=========

Installs Math Kernel library along with the minimum GCC version required on RedHat/Centos 6 machines.

Requirements
------------

You must use ansible 2.0.0 and have a RedHat/Centos 6 computer

Role Variables
--------------

MKL_PACKAGE_PATH: the path will be default to a url but if you wish you can provide your own package.
GCC_PACKAGE_PATH: the path will be default to a url but if you wish you can provide your own package.


Example Playbook
----------------

If you wish to provide your own GCC and MKL package 
too:

    - hosts: servers
      become: yes
      become_user: root
      roles:
         - { role: install-mkl, MKL_PACKAGE_PATH: '{{mkl_package}}', GCC_PACKAGE_PATH: '{{gcc_package}}'  }
         
Not providing GCC and MKL will also work 
too:

    - hosts: servers
      become: yes
      become_user: root
      roles:
         - { role: install-mkl, MKL_PACKAGE_PATH: '{{mkl_package}}', GCC_PACKAGE_PATH: '{{gcc_package}}'  }

License
-------
Outbound licenses
- GCC - https://gcc.gnu.org/onlinedocs/gcc-4.8.5/gcc/Copying.html#Copying 
- MKL - https://software.intel.com/sites/default/files/managed/67/99/Master_EULA_for_Intel_Sw_Development_Products_March_2016.pdf 



